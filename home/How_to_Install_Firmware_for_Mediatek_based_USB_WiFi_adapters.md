## How to install firmware for Mediatek-based USB WiFi adapters

Maintained by @morrownr

Purpose: Provide the steps to install or upgrade firmware for Mediatek-based
USB WiFi adapters. Some Linux distros do not include the firmware that is
necessary to support USB WiFi adapters. Debian prior to Debian 12 is a good
example. Other distros make mistakes and leave the firmware out of their
distro and sometimes you may need to update the firmware. Then there are the
numerous server distros where wifi support may not be included because the
maintainers think wifi is not used in server applications. Hopefully the
following is helpful.

The following sections are available:

1. MT7925 - mt7925 chipset (WiFi 7)
2. MT7922 - mt7922 (AMD RZ616) chipsets (WiFi 6e)
3. MT7921 - mt7921au, mt7921k and mt7921 (AMD RZ608) chipsets (WiFi 6e except for the mt7921)
4. MT7921 - mt7921au, mt7921k and mt7921 (AMD RZ608) chipsets (instructions are specific to OpenWRT)
5. mt7612u chipset (WiFi 5)
6. mt7610u chipset (WiFi 5)

Note: The instructions in sections 1, 2 and 3 apply to PCIe cards as well as USB adapters.

Note: Realtek rtw88 firmware is located [here](https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/rtw88). Copy the appropriate file to `/lib/firmware/rtw88`.

-----

How do I check the firmware version in my system?

```
ethtool -i <interface name> 
```

 Note: You may need to install the `ethtool` and `iw` packages depending on your distro.


-----

`1. MT7925 - mt7925 chipset`

To install or update the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek/mt7925

Click on `	WIFI_MT7925_PATCH_MCU_1_1_hdr.bin`

Click on `plain`

Save file

Click on `WIFI_RAM_CODE_MT7925_1_1.bin`

Click on `plain`

Save file

If your card has Bluetooth support:

Click on `BT_RAM_CODE_MT7925_1_1_hdr.bin`

Click on `plain`

Save file

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the files to the following locations:

```
sudo cp WIFI_MT7925_PATCH_MCU_1_1_hdr.bin /lib/firmware/mediatek
```

```
sudo cp WIFI_RAM_CODE_MT7925_1_1.bin /lib/firmware/mediatek
```

```
sudo cp BT_RAM_CODE_MT7925_1_1_hdr.bin /lib/firmware/mediatek
```

Reboot:

```
sudo reboot
```

-----

`2. MT7922 - mt7922 (AMD RZ616) chipsets`

To install or update the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `WIFI_MT7922_patch_mcu_1_1_hdr.bin`

Click on `plain`

Save file

Click on `WIFI_RAM_CODE_MT7922_1.bin`

Click on `plain`

Save file

If your adapter/card has Bluetooth support:

Click on `BT_RAM_CODE_MT7922_1_1_hdr.bin`

Click on `plain`

Save file

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the files to the following locations:

```
sudo cp WIFI_MT7922_patch_mcu_1_1_hdr.bin /lib/firmware/mediatek
```

```
sudo cp WIFI_RAM_CODE_MT7922_1.bin /lib/firmware/mediatek
```

```
sudo cp BT_RAM_CODE_MT7922_1_1_hdr.bin /lib/firmware/mediatek
```

Reboot:

```
sudo reboot
```

-----

`3. MT7921 - mt7921au, mt7921, and mt7921k (AMD RZ608) chipsets`

To install or update the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `WIFI_MT7961_patch_mcu_1_2_hdr.bin`

Click on `plain`

Save file

Click on `WIFI_RAM_CODE_MT7961_1.bin`

Click on `plain`

Save file

If your adapter/card has Bluetooth support:

Click on `BT_RAM_CODE_MT7961_1_2_hdr.bin`

Click on `plain`

Save file

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the files to the following locations:

```
sudo cp WIFI_MT7961_patch_mcu_1_2_hdr.bin /lib/firmware/mediatek
```

```
sudo cp WIFI_RAM_CODE_MT7961_1.bin /lib/firmware/mediatek
```

```
sudo cp BT_RAM_CODE_MT7961_1_2_hdr.bin /lib/firmware/mediatek
```

Reboot:

```
sudo reboot
```

Note: To fully remove bluetooth detection:

```
sudo rm /lib/firmware/mediatek/BT_RAM_CODE_MT7961_1_2_hdr.bin
```

-----

`4. MT7921 - mt7921au, mt7921, and mt7921k (AMD RZ608) chipsets (specific to OpenWRT)`

Note: With OpenWRT 22.03.3 or later, to install the mt7921u driver
(for adapters based on the mt7921au chipset) and the 2 requested
firmware files, simply install the following package:

kmod-mt7921u

Previously, the kmod-mt7921e package also had to be installed as
it installed the firmware files. This is no longer necessary.

Download firmware files to Linux PC

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

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
scp WIFI_RAM_CODE_MT7961_1.bin root@192.168.1.1:/lib/firmware/mediatek
```

```
scp WIFI_MT7961_patch_mcu_1_2_hdr.bin root@192.168.1.1:/lib/firmware/mediatek
```

Reboot:

```
# reboot
```

-----

`5. mt7612u chipset`

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
sudo mkdir /lib/firmware/mediatek
```

Copy the files to the following locations:

```
sudo cp mt7662u.bin /lib/firmware/mediatek
```

```
sudo cp mt7662u_rom_patch.bin /lib/firmware/mediatek
```
Reboot:

```
sudo reboot
```

-----

`6. mt7610u chipset`

To install or update the firmware:

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `mt7610u.bin`

Click on `plain`

Save file

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the file to the following location:

```
sudo cp mt7610u.bin /lib/firmware/mediatek
```

Reboot:

```
sudo reboot
```

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
