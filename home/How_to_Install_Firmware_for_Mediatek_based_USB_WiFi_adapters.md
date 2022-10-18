2022-10-16

Maintained by @morrownr

How to Install Firmware for Mediatek based USB WiFi adapters

Purpose: Provide the steps to Install or Upgrade Firmware for Mediatek
based USB WiFi adapters. Some Linux distros do not include the firmware
necessary to support USB WiFi adapters. Debian is a good example. Other
distros make mistakes and leave the firmware out of their distro and sometimes
you may need to update the firmware. Hopefully the following is helpful.

Instructions for the mt7921u, mt7612u and mt7610u are currently available.

-----

mt7921u (mt7921au chipset)

Note: if installing to OpenWRT, there is another section specific to OpenWRT
below this section.

To install or update the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `WIFI_MT7961_patch_mcu_1_2_hdr.bin`

Click on `plain`

Save file

Click on `WIFI_RAM_CODE_MT7961_1.bin`

Click on `plain`

Save file

If your adapter has Bluetooth support and you
want to activate it:

Click on `BT_RAM_CODE_MT7961_1_2_hdr.bin`

Click on `plain`

Save file

Create the needed directory (if necessary):
```
$ sudo mkdir /lib/firmware/mediatek
```
Copy the files to the following locations:

```
$ sudo cp WIFI_MT7961_patch_mcu_1_2_hdr.bin /lib/firmware/mediatek
$ sudo cp WIFI_RAM_CODE_MT7961_1.bin /lib/firmware/mediatek
$ sudo cp BT_RAM_CODE_MT7961_1_2_hdr.bin /lib/firmware/mediatek
```
Reboot:

```
$ sudo reboot
```

-----

How to Install mt7921au firmware files on OpenWRT

Note: As of OpenWRT 22.03.2, the mt7921au firmware
is still included in the mt7921e driver file instead
of a common package. Therefore, loading the mt7921u
driver does not load the firmware.

Download firmware files to Linux PC

Go to the following site:

```
https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek
```

Click on WIFI_MT7961_patch_mcu_1_2_hdr.bin

Click on plain

Save file

Click on WIFI_RAM_CODE_MT7961_1.bin

Click on plain

Save file


ssh to OpenWRT router (Putty or other) (make sure a non null password was previously set)

cd /lib/firmware

mkdir mediatek

On Linux PC:

```
$ scp WIFI_RAM_CODE_MT7961_1.bin root@192.168.1.1:/lib/firmware/mediatek
$ scp WIFI_MT7961_patch_mcu_1_2_hdr.bin root@192.168.1.1:/lib/firmware/mediatek
```

Reboot:

```
# reboot
```

-----

mt7612u

To install or update the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `mt7662u.bin`

Click on `plain`

Save file

Click on `mt7662u_rom_patch.bin`

Click on `plain`

Save file

Create the needed directory (if necessary):
```
$ sudo mkdir /lib/firmware/mediatek
```
Copy the files to the following locations:
```
$ sudo cp mt7662u.bin /lib/firmware/mediatek
$ sudo cp mt7662u_rom_patch.bin /lib/firmware/mediatek
```
Reboot:
```
$ sudo reboot
```
-----

mt7610u

To install or update the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `mt7610u.bin`

Click on `plain`

Save file

Create the needed directory (if necessary):
```
$ sudo mkdir /lib/firmware/mediatek
```
Copy the file to the following location:
```
$ sudo cp mt7610u.bin /lib/firmware/mediatek
```
Reboot:
```
$ sudo reboot

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
