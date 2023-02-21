Compiling_the_Linux_Mainline_Kernel

Purpose: Facilitate Testing or Patching Drivers

Maintained by @morrownr

2023-02-20

Prerequisites:

A system running Linux (only Ubuntu is tested).

Access to the terminal/command line.

A user account with sudo/root privileges.

12GB of available space on the hard drive.

-----

Note: This checklist has only been tested on Ubuntu 22.10 but will likely work,
possibly with minor modifications, on numerous distros, however you should
check with your distro documentation or user support forums to confirm.

-----

Download the Source Code tarball from:

https://www.kernel.org/

linux-6.2.tar.xz

Note: The above name will change depending on the version of the kernel you
decide to compile. Adjust accordingly.

Note: I make a directory called `src` in my home directory and that is what I
download the file to. Anywhere in your home directory should work.

```
mkdir ~/src
```

Download the Source Code tarball to `~/src` and move to the `~/src` directory:

```
cd ~/src
```

-----

Extract the Source Code:

```
tar xvf linux-6.2.tar.xz
```

-----

Install Required Packages:

```
sudo apt install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc flex libelf-dev bison
```

Note: The above line is specific to Debian based distros such
as Ubuntu.

-----

Configure Kernel:

Note: You may want to research this issue so as to have a better understanding
of what this short guide provides.

Navigate to the `linux-6.2` directory using the cd command:

```
cd linux-6.2
```

Copy the existing configuration file using the cp command:

```
cp -v /boot/config-$(uname -r) .config
```

To make changes to the configuration file:

Run make:

```
make menuconfig
```

The command launches several scripts that open the configuration menu.

The configuration menu includes options such as firmware, file system, network,
and memory settings. Use the arrows to make a selection or choose Help to learn
more about the options. When you finish making the changes, select Save, and
then exit the menu.

-----

Example: To turn on support for the rtl8822bu, rtl8812bu, rtl8821cu and
rtl8811cu chipsets, select 8822BU and 8821CU per the example below:

```
Device Drivers  --->

-*- Network device support  --->

[*]   Wireless LAN  --->

<M>     Realtek 802.11ac wireless chips support  --->

--- Realtek 802.11ac wireless chips support
         <M>   Realtek 8822BE PCI wireless network adapter
         < >   Realtek 8822BU USB wireless network adapter (NEW)
         <M>   Realtek 8822CE PCI wireless network adapter
         < >   Realtek 8822CU USB wireless network adapter (NEW)
         <M>   Realtek 8723DE PCI wireless network adapter
         < >   Realtek 8723DU USB wireless network adapter (NEW)
         <M>   Realtek 8821CE PCI wireless network adapter
         < >   Realtek 8821CU USB wireless network adapter (NEW)
```

In the section above, there are 4 new drivers that will not compile unless you
select them. Once finished, select Save, and then exit the menu.

-----

Example: To turn on support for the mt7921au chipset, select MT7921U in the
example below:

```
Device Drivers  --->

-*- Network device support  --->

[*]   Wireless LAN  --->

[*]   MediaTek devices
         <M>     MediaTek MT7601U (USB) support
         <M>     MediaTek MT76x0U (USB) support
         <M>     MediaTek MT76x0E (PCIe) support
         <M>     MediaTek MT76x2E (PCIe) support
         <M>     MediaTek MT76x2U (USB) support
         <M>     MediaTek MT7603E (PCIe) and MT76x8 WLAN support
         <M>     MediaTek MT7615E and MT7663E (PCIe) support
         <M>     MediaTek MT7663U (USB) support
         <M>     MediaTek MT7663S (SDIO) support
         <M>     MediaTek MT7915E (PCIe) support
         <M>     MediaTek MT7921E (PCIe) support
         <M>     MediaTek MT7921S (SDIO) support
         <M>     MediaTek MT7921U (USB) support
```

In the section above, the MT7921U driver is already selected. Once finished,
select Save, and then exit the menu.

-----

Prevent errors related to certs:

If you are compiling the kernel on Ubuntu or on any distros based on Ubuntu,
you may receive the following error that interrupts the building process:

`No rule to make target debian/canonical-certs.pem`

To prevent the above problem, disable the conflicting security certificates
by executing the two commands below:

```
scripts/config --disable SYSTEM_TRUSTED_KEYS
```

```
scripts/config --disable SYSTEM_REVOCATION_KEYS
```

-----

Now is the time to patch any files if you are going to test.

-----

Compile the kernel:

```
make -j$(nproc)
```

The process of compiling the Linux kernel takes some time to complete.

Note: If the compile stops, make selections or take the default and
hit Enter until compiling starts again (this is related new stuff and
the cert stuff above).

---

Install the required modules:

```
sudo make modules_install
```

---

Install the kernel:

```
sudo make install
```

---

Reboot and check kernel:

```
uname -r
```

-----

For uninstalling the kernel installed from source, run:

```
sudo rm -rf /lib/modules/kernel_version
```
Example: $ sudo rm -rf /lib/modules/6.2

```
sudo rm -f /boot/vmlinuz-kernel_version*
```
Example: $ sudo rm -f /boot/vmlinuz-6.2*

```
sudo rm -f /boot/initrd.img-kernel_version*
```
Example: $ sudo rm -f /boot/initrd.img-6.2*

```
sudo rm -f /boot/config-kernel_version*
```
Example: $ sudo rm -f /boot/config-6.2*

```
sudo rm -f /boot/System.map-kernel_version*
```
Example: $ sudo rm -f /boot/System.map-6.2*

Finally, after uninstalling the kernel, run:

```
sudo update-grub
```

to update the grub menu.

-----

Happy compiling!

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
