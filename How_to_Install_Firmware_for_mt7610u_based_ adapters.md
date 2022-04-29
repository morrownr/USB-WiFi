2022-04-26

How to Install Firmware for Mediatek based USB WiFi adapters

<<<<<<< HEAD
Purpose: Provide the steps to Install Firmware for Mediatek based USB
WiFi adapters. Some Linux distros do not include the firmware necessary
to support USB WiFi adapters. Debian is a good example. Other distros
make mistakes and leave the profer firmware out of their distro and
sometimes you may need to update the firmware. Hopefully the following
is helpful.
=======
Purpose: Provide the steps to Install Firmware for mt7610u based adapters.

Info: Some Linux distros have mistakenly not installed the firmware for mt7610u
adapters and some distros, such as Debian, do not include firmware is their flagship
distros which makes it look like a driver needs to be installed.
>>>>>>> 94e0da05b1caf5958197437064a4aab9e24c1145

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
Copy the file to the new directory:
```
$ sudo cp mt7610u.bin /lib/firmware/mediatek
```
Reboot:
```
$ sudo reboot
```

-----

mt7921u

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
Copy the files to the new directory:
```
$ sudo cp BT_RAM_CODE_MT7961_1_2_hdr.bin /lib/firmware/mediatek
$ sudo cp WIFI_MT7961_patch_mcu_1_2_hdr.bin /lib/firmware/mediatek
$ sudo cp WIFI_RAM_CODE_MT7961_1.bin /lib/firmware/mediatek
```
Reboot:
```
$ sudo reboot
```
	

