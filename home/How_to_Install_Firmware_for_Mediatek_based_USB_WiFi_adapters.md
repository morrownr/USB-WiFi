## How to install or update firmware for Mediatek-based USB WiFi adapters
(also Realtek rtw88 firmware)

Maintained by @morrownr
Updated: 2025-03-10

Purpose: Provide the steps to install or upgrade firmware for Mediatek
or rtw88 based USB WiFi adapters. Some Linux distros do not include the
firmware that is necessary to support USB WiFi adapters. Debian prior to
Debian 12 is a good example. Other distros make mistakes and leave the
firmware out of their distro and sometimes you may need to update the
firmware to a newer version. Then there are the numerous server distros
where wifi support, to include the firmware, may not be included because
the maintainers think wifi is not used in server applications.

Information: In-kernel drivers in Linux come in 2 or more parts. There
is what is normally called the driver, which is part of the kernel, and
there is the firmware (binary blob), which may be 1 or more files, and
is not part of the kernel. Firmware files are part of the distro and
have to be installed and updated by the maintainers of your distros or
by you. Some distros do not install firmware, therefore you may to need
to install the firmware yourself depending on your Linux distro. You can
check the firmware, see appropriate section, to see if firmware needs to
be installed or upgraded. Keep in mind that firmware file names do not
change so you have to compare file sizes, dates or version to determine
if you have the latest version. The symptom of a missing firmware is
that the adapter does not show up on boot... just like if there is no
driver in your kernel. To repeat, adapters that use in-kernel drivers,
to function properly, the driver (module) is required AND the firmware
is required. The absence of either will cause the adapter to not show up
on boot. All of the more popular mainstream distros have everything in
place. This includes but is not limited to current releases of Ubuntu
(and all of its puppies), Debian, Mint, fedora, Manjaro, Raspberry Pi OS
and many more.

Note: Many Mediatek firmware files go in `/lib/firmware/mediatek` but not all so you need to pay attention to the instructions below.

The following sections are available:

1. MT7925 - mt7925e/u chipsets (AMD RZ717) (WiFi 7)
2. MT7922 - mt7922e chipset (AMD RZ616) (WiFi 6e)
3. MT7921 - mt7921au, mt7921k and mt7921e chipsets (AMD RZ608) (WiFi 6e except for the mt7921 which is WiFi 6)
4. MT7921 - mt7921au, mt7921k and mt7921e chipsets (AMD RZ608) (instructions are specific to OpenWRT)
5. MT7920 - mt7920e (WiFi 6)
6. MT7612 - mt7612u chipset (WiFi 5)
7. MT7610 - mt7610u chipset (WiFi 5)
8. MT7601 - mt7601u (WiFi 4)

Note: The instructions in sections 1, 2 and 3 apply to PCIe and M.2 cards as well as USB adapters and modules.

Note: Realtek rtw88 firmware is located [here](https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/rtw88). Copy the appropriate file(s) to `/lib/firmware/rtw88`

Note: Some distros compress firmware files. The compressed firmware files will have the same filename but will end with `.zst`. `.xz` or `.gz`. Instructions for how to handle this are in each section below.

Note: Make sure the firmware files are owned by root after moving them to the correct directory before rebooting.

-----

How do I check the firmware version in my system?

```
ethtool -i <interface name> 
```

 Note: You may need to install the `ethtool` and `iw` packages depending on your distro.


-----

`1. MT7925 - mt7925 chipset`

To install or update the firmware:

Create a folder/directory to hold the downloaded firmware files. Example:

$ mkdir -p ~/firmware

Move to your newly created firmware folder/directory:

$ cd ~/firmware

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek/mt7925

Click on `WIFI_MT7925_PATCH_MCU_1_1_hdr.bin`

Click on `plain`

Save the file to ~/firmware

Click on `WIFI_RAM_CODE_MT7925_1_1.bin`

Click on `plain`

Save the file to ~/firmware

If your card has Bluetooth support:

Click on `BT_RAM_CODE_MT7925_1_1_hdr.bin`

Click on `plain`

Save the file to ~/firmware

Check that your files downloaded properly:

$ ls -l ~/firmware

Note that the downloaded files will end with `.bin`. You now need to check what type, if any, compression is used for firmware files in your system:

$ ls -l /lib/firmware/mediatek

Check to see the endings of the files. If your firmware files are uncompressed, you will see an ending of `.bin`. If your firmware files are compressed you will see an ending of `.zst`. `.xz` or `.gz`.

For compressed files, you will first need to compress your downloaded files before copying them to their final destination. Make sure you are in the firmware folder/directory we created earlier (or the location that you decided to create to hold the firmware files):

$ cd ~/firmware

For .zst files, run:

$ zstd -fq --rm *.bin

For .xz files, run:

$ xz -f -C crc32 *.bin

For .gz files, run:

gzip -f *.bin

Check to ensure your new firmware files have the proper filename ending for your system:

$ ls -l ~/firmware

You are now ready to copy the new firmware files to their destination folder/directory.

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek/mt7925
```

Copy the files to the following locations:

```
sudo cp WIFI_MT7925_PATCH_MCU_1_1_hdr.* /lib/firmware/mediatek/mt7925
```

```
sudo cp WIFI_RAM_CODE_MT7925_1_1.* /lib/firmware/mediatek/mt7925
```

```
sudo cp BT_RAM_CODE_MT7925_1_1_hdr.* /lib/firmware/mediatek/mt7925
```

Reboot:

```
sudo reboot
```

-----

`2. MT7922 - mt7922 (AMD RZ616) chipsets`

To install or update the firmware:

Create a folder/directory to hold the downloaded firmware files. Example:

$ mkdir -p ~/firmware

Move to your newly created firmware folder/directory:

$ cd ~/firmware

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `WIFI_MT7922_patch_mcu_1_1_hdr.bin`

Click on `plain`

Save the file to ~/firmware 

Click on `WIFI_RAM_CODE_MT7922_1.bin`

Click on `plain`

Save the file to ~/firmware

If your adapter/card has Bluetooth support:

Click on `BT_RAM_CODE_MT7922_1_1_hdr.bin`

Click on `plain`

Save the file to ~/firmware

Check that your files downloaded properly:

$ ls -l ~/firmware

Note that the downloaded files will end with `.bin`. You now need to check what type, if any, compression is used for firmware files in your system:

$ ls -l /lib/firmware/mediatek

Check to see the endings of the files. If your firmware files are uncompressed, you will see an ending of `.bin`. If your firmware files are compressed you will see an ending of `.zst`. `.xz` or `.gz`.

For compressed files, you will first need to compress your downloaded files before copying them to their final destination. Make sure you are in the firmware folder/directory we created earlier (or the location that you decided to create to hold the firmware files):

$ cd ~/firmware

For .zst files, run:

$ zstd -fq --rm *.bin

For .xz files, run:

$ xz -f -C crc32 *.bin

For .gz files, run:

gzip -f *.bin

Check to ensure your new firmware files have the proper filename ending for your system:

$ ls -l ~/firmware

You are now ready to copy the new firmware files to their destination folder/directory.

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the files to the following locations:

```
sudo cp WIFI_MT7922_patch_mcu_1_1_hdr.* /lib/firmware/mediatek
```

```
sudo cp WIFI_RAM_CODE_MT7922_1.* /lib/firmware/mediatek
```

```
sudo cp BT_RAM_CODE_MT7922_1_1_hdr.* /lib/firmware/mediatek
```

Reboot:

```
sudo reboot
```

-----

`3. MT7921 - mt7921au, mt7921, and mt7921k (AMD RZ608) chipsets`

To install or update the firmware:

Create a folder/directory to hold the downloaded firmware files. Example:

$ mkdir -p ~/firmware

Move to your newly created firmware folder/directory:

$ cd ~/firmware

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `WIFI_MT7961_patch_mcu_1_2_hdr.bin`

Click on `plain`

Save the file to ~/firmware

Click on `WIFI_RAM_CODE_MT7961_1.bin`

Click on `plain`

Save the file to ~/firmware

If your adapter/card has Bluetooth support:

Click on `BT_RAM_CODE_MT7961_1_2_hdr.bin`

Click on `plain`

Save the file to ~/firmware

Check that your files downloaded properly:

$ ls -l ~/firmware

Note that the downloaded files will end with `.bin`. You now need to check what type, if any, compression is used for firmware files in your system:

$ ls -l /lib/firmware/mediatek

Check to see the endings of the files. If your firmware files are uncompressed, you will see an ending of `.bin`. If your firmware files are compressed you will see an ending of `.zst`. `.xz` or `.gz`.

For compressed files, you will first need to compress your downloaded files before copying them to their final destination. Make sure you are in the firmware folder/directory we created earlier (or the location that you decided to create to hold the firmware files):

$ cd ~/firmware

For .zst files, run:

$ zstd -fq --rm *.bin

For .xz files, run:

$ xz -f -C crc32 *.bin

For .gz files, run:

gzip -f *.bin

Check to ensure your new firmware files have the proper filename ending for your system:

$ ls -l ~/firmware

You are now ready to copy the new firmware files to their destination folder/directory.

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the files to the following locations:

```
sudo cp WIFI_MT7961_patch_mcu_1_2_hdr.* /lib/firmware/mediatek
```

```
sudo cp WIFI_RAM_CODE_MT7961_1.* /lib/firmware/mediatek
```

```
sudo cp BT_RAM_CODE_MT7961_1_2_hdr.* /lib/firmware/mediatek
```

Reboot:

```
sudo reboot
```

Note: To fully remove bluetooth detection, delete the bluetooth firmware file:

```
sudo rm /lib/firmware/mediatek/BT_RAM_CODE_MT7961_1_2_hdr.*
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

`5. MT7921 - mt7921au, mt7921k and mt7921e (AMD RZ608) chipsets`

To install or update the firmware:

Create a folder/directory to hold the downloaded firmware files. Example:

$ mkdir -p ~/firmware

Move to your newly created firmware folder/directory:

$ cd ~/firmware

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `WIFI_MT7961_patch_mcu_1a_2_hdr.bin`

Click on `plain`

Save the file to ~/firmware

Click on `WIFI_RAM_CODE_MT7961_1a.bin`

Click on `plain`

Save the file to ~/firmware

If your adapter/card has Bluetooth support:

Click on `BT_RAM_CODE_MT7961_1a_2_hdr.bin`

Click on `plain`

Save the file to ~/firmware

Check that your files downloaded properly:

$ ls -l ~/firmware

Note that the downloaded files will end with `.bin`. You now need to check what type, if any, compression is used for firmware files in your system:

$ ls -l /lib/firmware/mediatek

Check to see the endings of the files. If your firmware files are uncompressed, you will see an ending of `.bin`. If your firmware files are compressed you will see an ending of `.zst`. `.xz` or `.gz`.

For compressed files, you will first need to compress your downloaded files before copying them to their final destination. Make sure you are in the firmware folder/directory we created earlier (or the location that you decided to create to hold the firmware files):

$ cd ~/firmware

For .zst files, run:

$ zstd -fq --rm *.bin

For .xz files, run:

$ xz -f -C crc32 *.bin

For .gz files, run:

gzip -f *.bin

Check to ensure your new firmware files have the proper filename ending for your system:

$ ls -l ~/firmware

You are now ready to copy the new firmware files to their destination folder/directory.

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the files to the following locations:

```
sudo cp WIFI_MT7961_patch_mcu_1a_2_hdr.* /lib/firmware/mediatek
```

```
sudo cp WIFI_RAM_CODE_MT7961_1a.* /lib/firmware/mediatek
```

```
sudo cp BT_RAM_CODE_MT7961_1a_2_hdr.* /lib/firmware/mediatek
```

Reboot:

```
sudo reboot
```

Note: To fully remove bluetooth detection, delete the bluetooth firmware file:

```
sudo rm /lib/firmware/mediatek/BT_RAM_CODE_MT7961_1a_2_hdr.*
```

-----

`6. MT7612 - mt7612u chipset`

To install or update the firmware:

Create a folder/directory to hold the downloaded firmware files. Example:

$ mkdir -p ~/firmware

Move to your newly created firmware folder/directory:

$ cd ~/firmware

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `mt7662u.bin`

Click on `plain`

Save the file to ~/firmware

Click on `mt7662u_rom_patch.bin`

Click on `plain`

Save the file to ~/firmware

Check that your files downloaded properly:

$ ls -l ~/firmware

Note that the downloaded files will end with `.bin`. You now need to check what type, if any, compression is used for firmware files in your system:

$ ls -l /lib/firmware/mediatek

Check to see the endings of the files. If your firmware files are uncompressed, you will see an ending of `.bin`. If your firmware files are compressed you will see an ending of `.zst`. `.xz` or `.gz`.

For compressed files, you will first need to compress your downloaded files before copying them to their final destination. Make sure you are in the firmware folder/directory we created earlier (or the location that you decided to create to hold the firmware files):

$ cd ~/firmware

For .zst files, run:

$ zstd -fq --rm *.bin

For .xz files, run:

$ xz -f -C crc32 *.bin

For .gz files, run:

gzip -f *.bin

Check to ensure your new firmware files have the proper filename ending for your system:

$ ls -l ~/firmware

You are now ready to copy the new firmware files to their destination folder/directory.

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the files to the following locations:

```
sudo cp mt7662u.* /lib/firmware/mediatek
```

```
sudo cp mt7662u_rom_patch.* /lib/firmware/mediatek
```
Reboot:

```
sudo reboot
```

-----

`7. MT7610 - mt7610u chipset`

To install or update the firmware:

Create a folder/directory to hold the downloaded firmware files. Example:

$ mkdir -p ~/firmware

Move to your newly created firmware folder/directory:

$ cd ~/firmware

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `mt7610u.bin`

Click on `plain`

Save the file to ~/firmware

Check that your files downloaded properly:

$ ls -l ~/firmware

Note that the downloaded files will end with `.bin`. You now need to check what type, if any, compression is used for firmware files in your system:

$ ls -l /lib/firmware/mediatek

Check to see the endings of the files. If your firmware files are uncompressed, you will see an ending of `.bin`. If your firmware files are compressed you will see an ending of `.zst`. `.xz` or `.gz`.

For compressed files, you will first need to compress your downloaded files before copying them to their final destination. Make sure you are in the firmware folder/directory we created earlier (or the location that you decided to create to hold the firmware files):

$ cd ~/firmware

For .zst files, run:

$ zstd -fq --rm *.bin

For .xz files, run:

$ xz -f -C crc32 *.bin

For .gz files, run:

gzip -f *.bin

Check to ensure your new firmware files have the proper filename ending for your system:

$ ls -l ~/firmware

You are now ready to copy the new firmware files to their destination folder/directory.

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware/mediatek
```

Copy the file to the following location:

```
sudo cp mt7610u.* /lib/firmware/mediatek
```

Reboot:

```
sudo reboot
```

-----

`8. MT7601 - mt7601u chipset`

To install or update the firmware:

Create a folder/directory to hold the downloaded firmware files. Example:

$ mkdir -p ~/firmware

Move to your newly created firmware folder/directory:

$ cd ~/firmware

Go to the following site:

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek

Click on `mt7601u.bin`

Click on `plain`

Save the file to ~/firmware

Check that your files downloaded properly:

$ ls -l ~/firmware

Note that the downloaded files will end with `.bin`. You now need to check what type, if any, compression is used for firmware files in your system:

$ ls -l /lib/firmware/mediatek

Check to see the endings of the files. If your firmware files are uncompressed, you will see an ending of `.bin`. If your firmware files are compressed you will see an ending of `.zst`. `.xz` or `.gz`.

For compressed files, you will first need to compress your downloaded files before copying them to their final destination. Make sure you are in the firmware folder/directory we created earlier (or the location that you decided to create to hold the firmware files):

$ cd ~/firmware

For .zst files, run:

$ zstd -fq --rm *.bin

For .xz files, run:

$ xz -f -C crc32 *.bin

For .gz files, run:

gzip -f *.bin

Check to ensure your new firmware files have the proper filename ending for your system:

$ ls -l ~/firmware

You are now ready to copy the new firmware files to their destination folder/directory.

Create the needed directory (if necessary):

```
sudo mkdir /lib/firmware
```

Copy the file to the following location:

```
sudo cp mt7601u.* /lib/firmware
```

Reboot:

```
sudo reboot
```

-----
