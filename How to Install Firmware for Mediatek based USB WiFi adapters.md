2022-05-02

Maintained by @morrownr

How to Install Firmware for Mediatek based USB WiFi adapters

Purpose: Provide the steps to Install Firmware for Mediatek based USB
WiFi adapters. Some Linux distros do not include the firmware necessary
to support USB WiFi adapters. Debian is a good example. Other distros
make mistakes and leave the firmware out of their distro and sometimes
you may need to update the firmware. Hopefully the following is helpful.

Instructions for the mt7610u, mt7612u and mt7921 are currently available.

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
$ sudo cp mt7662u.bin /lib/firmware
$ sudo cp mt7662u.bin /lib/firmware/mediatek
$ sudo cp mt7662u_rom_patch.bin /lib/firmware
$ sudo cp mt7662u_rom_patch.bin /lib/firmware/mediatek
```
Reboot:
```
$ sudo reboot
```
-----

mt7921

To install or update the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `BT_RAM_CODE_MT7961_1_2_hdr.bin`

Click on `plain`

Save file

Click on `WIFI_MT7961_patch_mcu_1_2_hdr.bin`

Click on `plain`

Save file

Click on `WIFI_RAM_CODE_MT7961_1.bin`

Click on `plain`

Save file

Create the needed directory (if necessary):
```
$ sudo mkdir /lib/firmware/mediatek
```
Copy the files to the following locations:
```
$ sudo cp BT_RAM_CODE_MT7961_1_2_hdr.bin /lib/firmware/mediatek
$ sudo cp WIFI_MT7961_patch_mcu_1_2_hdr.bin /lib/firmware/mediatek
$ sudo cp WIFI_RAM_CODE_MT7961_1.bin /lib/firmware/mediatek
```
Reboot:
```
$ sudo reboot
```
	

