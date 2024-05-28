2024-01-26

## Compile and Install New RasPiOS Kernel

Purpose: Upgrade the RasPiOS kernel to support new usb WiFi adapters that are not new enough for the driver to be included.
An example would be to include the new usb WiFi adapters in the rtw88 driver series.
USB WiFi adapter support was added for several WiFi 5 adapters with kernel 6.2, but the RasPiOS is usually only upgrade to a new kernel after a new LTS kernel is available.
As of this writing, RasPiOS uses kernel 6.1 and kernel 6.2 or later is required for this new rtw88 support for adapters that use chipsets such as the rtl8812bu, rtl8811cu and more.

This guide uses 64-bit RasPiOS (2023-12-05) kernel on a Rasberry Pi 4B.
If you are using a different model of Pi, refer to the [upstream documentation](https://www.raspberrypi.com/documentation/computers/linux_kernel.html#building) for any potential differences.

> [!WARNING]
> The prep time needed to compile a new kernel is minimal (well under an hour).
> However, due to the Pi's hardware limitations the actual compilation can take multiple hours.
> Be prepared for a long wait for the Pi completes the actual compilation.

### Step 1: Prepare and Install RasPiOS

> [!IMPORTANT]
> Before beginning, make sure that you have internet access.
> I plug an ethernet cable into my Pi4B.

1. Use the Raspberry Pi Imager:
   1. Erase (reformat) the SD card
   1. If running headless (i.e. without a monitor connected):
      Set Advanced Options so that SSH is available on first boot.
   1. If you do not have an ethernet cable to provide Internet access during setup, set a WiFi interface to start on first boot .
   1. Select and Burn Raspberry Pi OS (64 bit).
1. Boot SD in RasPi4B.
1. Determine the IP address of Pi4B.

   I run OpenWRT on my main router.
   On OpenWRT, `Status > Overview` will show the IP address of the Pi4B.
   Many other routers have similar capability.

1. Start Putty or SSH using the command line and enter the login ID and IP address of your Pi.

   The IP address (`192.168.1.45` in the below example) should be the address discovered from your router.
   The login ID (`smith` in the below example) and password are as set with Imager Advanced Options

   ``` shell
   ssh smith@192.168.1.45
   ```

1. Enable VNC.

   1. Run `sudo raspi-config`.
   1. Interface Options > VNC > Yes (if you want to use VNC to go headless)

   We should now be able to reboot and continue with intial setup with VNC.

1. Set your WLAN country.

   1. Log into the RasPi4B with VNC.
   1. Preferences > Raspberry Pi Configuration
   1. In Localization, set the WLAN Country to your country code.
   1. Optionally, set any other relevant configurations.

1. Update the Pi's operating system packages by running the following commands in order.

   1. `sudo apt update`
   1. `sudo apt upgrade`
   1. `sudo apt autoremove`
   1. `sudo reboot`

### Step 2: Install Git and Build Dependencies

Run the following command to install the tools you will need to compile the Linux kernel.

``` shell
sudo apt install git bc bison flex libssl-dev make libncurses5-dev
```

The command is safe to run even if any or all of the packages are already installed.
`libncurses5-dev` is included for `menuconfig`, which will be used later in this guide.

### Step 3: Download the Source Code

Run the following command, changing "rpi-6.6.y" the branch you want.

``` shell
git clone --depth=1 --branch rpi-6.6.y https://github.com/raspberrypi/linux
```

Omitting `--depth=1` will download the entire repository, including the full history of all branches.
This takes much longer and occupies much more storage.

Refer to the original GitHub repository, [raspberrypi/linux](https://github.com/raspberrypi/linux), for information about the available branches.

### Step 4: Prepare the Kernel Configuration

Prepare the default configuration by running the following commands.

1. Move into the Linux subdirectory.

   ``` shell
   cd linux
   ```

   Stay in this directory for all of the remaining steps in this section.

1. Set the `KERNEL` environment variable.

   ``` shell
   export KERNEL=kernel8
   ```

1. Create the initial configuration.

   ``` shell
   make bcm2711_defconfig
   ```

1. Optionally, enable any additional features you desire.

   For example, to turn on support for the RTW88 8822BU USB module (available in kernel 6.2+):

   1. Run `make menuconfig`.
   1. You will see a text screen with something close to the following at the top:

      ``` text
      .config - Linux/arm64 6.6.11 Kernel Configuration
      ```

   1. Enable support for 8822BU USB.

      1. Scroll with the down arrow key until you are on "Device Drivers", then presss Enter.
      1. Scroll down until you are on `<*> Network device support`, then press Enter.
      1. Scroll down until you are on `<*> Wireless LAN`, then press Enter.
      1. Scroll down until you are on `< > Realtek802.11ac wireless chips support`.
         Once there:
         1. Press Space Bar to add M.
         1. Press Enter.
      1. Scroll down until you are on `< > Realtek 8822BU USB wireless netwwork adapter`.
         Once there:
         1. Press Space Bar to add M.
         1. Press Tab until `<Save>` is selected, then press Enter.
         1. Press Enter one more time.
      1. To exit, press Esc and again press Esc.

1. If you need to modify or patch the kernel source in any way, do so now.

### Step 5: Build the Kernel

Run the following command to perform the full compilation.
Note that this may take multiple hours to complete.

``` shell
make -j4 Image.gz modules dtbs
```

### Step 6: Install the Kernel, Modules and Device Tree Blobs

Run the following commands.

1. `sudo make modules_install`
1. `sudo cp arch/arm64/boot/dts/broadcom/*.dtb /boot/firmware/`
1. `sudo cp arch/arm64/boot/dts/overlays/\*.dtb\* /boot/firmware/overlays/`
1. `sudo cp arch/arm64/boot/dts/overlays/README /boot/firmware/overlays/`
1. `sudo cp arch/arm64/boot/Image.gz /boot/firmware/$KERNEL.img`

> [!NOTE]
> If you have not already deactivated the internal WiFi, now would be a good time to do it before you reboot.

### Step 7: Reboot

Reboot your Pi by running the following command.

``` shell
sudo reboot
```

Once it comes back up, your Pi should now be running your freshly-compiled kernel!

### Step 8: Confirm Settings

1. Confirm that `uname -r` shows your new kernel version.

   For example:

   ``` console
   $ uname -r
   6.6.11-v8+
   ```

1. Confirm that `iw dev` reports your wireless interface.

   For example:

   ``` console
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

You should be finished at this point!
