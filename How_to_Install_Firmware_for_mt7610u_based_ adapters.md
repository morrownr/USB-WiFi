2022-04-21

How to Install Firmware for mt7610u based adapters

Purpose: Provide the steps to Install Firmware for mt7610u based adapters.

Info: Some Linux distros have mistakenly not installed the firmware for mt7610u
adapters and some distros, such as Debian, do not include firmware is their flagship
distros which makes it look like a driver needs to be installed.

-----

To install the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `mt7610u.bin`

Click on `plain`

Save file

Create the needed directory:
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
