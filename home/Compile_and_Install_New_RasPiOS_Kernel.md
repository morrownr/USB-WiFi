2024-01-26

Compile_and_Install_New_RasPiOS_Kernel

Purpose: Upgrade the RasPiOS kernel to support new usb wifi adapters
that are not new enough for the driver to be included. An example
would be to include the new usb wifi adapters in the rtw88 driver series.
USB WiFi adapter support was added for several WiFi 5 adapters with kernel
6.2 but the RasPiOS is usually only upgrade to a new kernel after a new LTS
kernel is available and, as of this writing, RasPiOS uses kernel 6.1 and
kernel 6.2 or later is required for this new rtw88 support for adapters
that use chipsets such as the rtl8812bu, rtl8811cu and more.

This guide uses: 64 bit RasPiOS (2023-12-05) kernel on a RasPi Pi4B

Original Guide: (you will need to refer to this guide if not using a RasPi4B)

https://www.raspberrypi.com/documentation/computers/linux_kernel.html#building

Note: Compiling the kernel on a RasPi can take a long time. It can takes hours.

Note: This guide is detailed and is specifically for a RasPi4B
using the Raspberry Pi OS (64 bit). You may need to modify it
based on your setup or desires.

-----

Step 1: Prepare and install the RasPiOS

Note: Make sure that you have internet access, I plug an ethernet
cable into my Pi4B.

Use the Raspberry Pi Imager:

Erase (reformat) the sd card

If running headless: Set Advanced Options so that SSH is available
on first boot. You may need to set a wifi interface to start on
first boot if you do not have an ethernet cable to provide internet
access during setup

Select and Burn Raspberry Pi OS (64 bit)

Boot sd in RasPi4B

Determine IP address of Pi4B. I run OpenWRT on my main router. On
OpenWRT: Status > Overview will show the IP address of the Pi4B.
Many other routers have similar capability.

Start Putty or SSH using the command line and enter login ID and
IP address as such:

$ ssh smith@192.168.1.45

The login ID and password are as set with Imager Advanced Options

Run:

$ sudo raspi-config

Interface Options > VNC > Yes (if you want to use VNC to go headless)

We should now be able to reboot and continue with intial setup with VNC.

Log into the RasPi4B with VNC and run:

Preferences > Raspberry Pi Configuration

You may configure other items but make sure to set the following:

Localization > Set WLAN Country to your country code

Remember to update, upgrade and autoremove before rebooting:

$ sudo apt update
$ sudo apt upgrade ($ sudo apt full-upgrade will get a firmware upgrade)
$ sudo apt autoremove (to clean house)
$ sudo reboot

-----

Step 2: Install git and the build dependencies

$ sudo apt install git bc bison flex libssl-dev make libncurses5-dev

Note: libncurses5-dev is required for menuconfig (not used in this guide yet.)

Note: git, bc and make will show as already installed for the RasPiOS version
that I am using in this guide but that is okay.

-----

Step 3: Download the sources

Note: change "rpi-6.6.y" to the branch you want in the command below.

$ git clone --depth=1 --branch rpi-6.6.y https://github.com/raspberrypi/linux

Note: Omitting --depth=1 will download the entire repository, including the
full history of all branches, but this takes much longer and occupies much
more storage.

Note: Refer to the original GitHub repository for information about the
available branches.

https://github.com/raspberrypi/linux

-----

Step 4: Prepare the kernel configuration

Prepare the default configuration by running the following commands.

Warning: Once you have moved into the linux subdirectory below, you
need to stay there until complete.

$ cd linux

$ KERNEL=kernel8

$ make bcm2711_defconfig

Example of change that can be made:

To turn on support for the RTW88 8822BU USB module: (available in kernel 6.2+)

$ make menuconfig

You will see a text screen with something close to the following at the
top:

 .config - Linux/arm64 6.6.11 Kernel Configuration
 
 You will now need to find and turn on compilation for 8822BU USB:
 
 Scroll with the down arrow key until you are on:
 
 Device Drivers (then press Enter)
 
 Scroll down until you are on:
 
 [*] Network device support (then press Enter)
 
 Scroll down until you are on:
  
 [*] Wireless LAN  (then press Enter)
 
 Scroll down until you are on:
 
 < > Realtek802.11ac wireless chips support (then press Space Bar to add M and then press Enter)
 
 Scroll down until you are on:
 
 < > Realtek 8822BU USB wireless netwwork adaptet (then press Space Bar to add M)
 
 Press Tab until <Save> is selected, then press Enter and again press Enter.
 
 To exit, press Esc and again press Esc.
 

Note: This is the point where you can modify or patch the kernel
source before compiling.

-----

Step 5: Build the Kernel

$ make -j4 Image.gz modules dtbs

-----

Step 6: Install the kernel, modules, and Device Tree blobs

$ sudo make modules_install

$ sudo cp arch/arm64/boot/dts/broadcom/*.dtb /boot/firmware/

$ sudo cp arch/arm64/boot/dts/overlays/\*.dtb\* /boot/firmware/overlays/

$ sudo cp arch/arm64/boot/dts/overlays/README /boot/firmware/overlays/

$ sudo cp arch/arm64/boot/Image.gz /boot/firmware/$KERNEL.img

Note: If you have not already deactivated the internal wifi, now would
be a good time to do it before you reboot.

Step 7:

$ sudo reboot

Your Raspberry Pi should now be running your freshly-compiled kernel!

```
$ uname -r
6.6.11-v8+

```

```
 $ iw dev
phy#0
	Interface wlan0
		ifindex 3
		wdev 0x1
		addr 00:c0:ca:ad:de:9e
		type managed
		txpower 30.00 dBm
		multicast TXQ:
			qsz-byt	qsz-pkt	flows	drops	marks	overlmt	hashcoltx-bytes	tx-packets
			0	0	0	0	0	0	0
```

You should be finished at this point.

-----
