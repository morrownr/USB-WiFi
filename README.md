2021-01-09

## USB WiFi Adapter Information for Linux

USB WiFi adapters provide flexibility in that they are easily moved from one location to another and can even be taken on the road. They come in models for USB 2 and USB 3. Some of the larger adapters work well for desktop use and the smaller adapters, including "nano" adapters work week for travel. While Linux enjoys very good in-kernel hardware support in many areas, USB WiFi adapters is not one of the those areas. The support is there and it is slowly improving but the lack of some major chipset makers, such as Intel, in the market have not forced some of the remaining chipset makers to support drivers in the kernel. Most people will be very happy with the current in-kernel support if they know what to buy and buying adapters with in-kernel support should encourage more drivers to be supported in the kernel. This document is educational in nature with the hope that it is of benefit to Linux users, experienced and new.

Warning: It is common for online retailers to post "Linux" support. It is best to ignore this information from the retailers as much of it is misleading at best and false as worst.  


### Dual Band USB WiFi Adapters (2.4GHz and 5GHz) that are supported with Linux in-kernel drivers 

Note: In-kernel means that the driver is supported in the Linux kernel which means that you do not need to install a driver. Simply plug the adapter in and it will work. Many people find this solution to be better than buying an adapter that requires drivers to be found, compiled and installed. Prices currently range from under $10 USD to $40 USD.

###### chipset mt7612u - AC1200
[Alfa Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD)

[Alfa Long-Range Dual-Band AC1200 Wireless USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Alfa-Long-Range-Dual-Band-Wireless-External/dp/B00MX57AO4)

###### chipset rt5572 - N600
[Panda Wireless PAU09 N600 Dual Band (2.4GHz and 5GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU09-Adapter-Antennas/dp/B01LY35HGO)

-----

### Single Band USB WiFi Adapters (2.4GHz only) that are supported with Linux in-kernel drivers

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can save a lot of trouble as it will allow you to have a termporary connection to download and install system updates and drivers for other adapters.  

###### chipset rt5372 - N300
[Panda Wireless PAU06 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU06-300Mbps-Adapter/dp/B00JDVRCI0)

[Panda Wireless PAU05 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-300Mbps-Wireless-USB-Adapter/dp/B00EQT0YK2)

###### chipset ar9271 - N150
[AR9271 802.11n 150Mbps Wireless USB WiFi Adapter](https://www.amazon.com/802-11n-150Mbps-Wireless-Adapter-Network/dp/B07FVRKCZJ)

[Alfa AWUS036NHA - Wireless B/G/N USB Adaptor](https://www.amazon.com/Alfa-AWUS036NHA-Wireless-USB-Adaptor/dp/B004Y6MIXS)

###### chipset rt5370 - N150
[CanaKit Raspberry Pi WiFi Wireless Adapter](https://www.amazon.com/dp/B00GFAN498)

[Panda Ultra WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG)

[WiFi for Raspberry Pi](https://www.amazon.com/dp/B00H95C0A2)

[USB WiFi Adapter Ralink RT5370](https://www.amazon.com/Adapter-Raspberry-OlinuXino-OpenSUSE-Injection/dp/B08B3B15CD)

[EASTECH Ralink RT5370 Raspberry PI WiFi Adapter](https://www.amazon.com/Ralink-RT5370-Raspberry-Adapter-Function/dp/B019XUDHFC)

-----
### Linux out-of-kernel drivers for Dual Band USB WiFi Adapters (ranked by quality)

Note: Out-of-kernel drivers require you to download, compile and install the driver source code. The below links to drivers provide a lot of information to include information about supported adapters.

###### chipset rtl8812au - AC1200 (excellent driver in managed mode) (outstanding driver in AP mode - 80211ac, 867 Mb/s, channel width 80)
[Linux Driver for USB WiFi Adapters that use the RTL8812AU Chipset](https://github.com/morrownr/8812au)

###### chipset rtl8821au - AC 600 (very good driver in managed mode) (excellent driver in AP mode - 80211ac, 434 Mb/s, channel width 80)
[Linux Driver for USB WiFi Adapters that use the RTL8811AU and RTL8821AU Chipsets](https://github.com/morrownr/8821au)

######  chipset rtl88x2bu - AC1200 (very good driver in managed mode) (AP mode testing in progress)
[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

###### chipset rtl8821cu - AC 600 (very good driver in managed mode)  (AP mode testing in progress)
[Linux Driver for USB WiFi Adapters that use the RTL8821CU and RTL8831AU Chipsets](https://github.com/morrownr/8821cu)

###### chipset rtl8814au - AC1900 (fair driver in managed mode) (bad driver in AP mode)
[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

-----

The plan for this site is to collect information and provide links regarding the use of USB WiFi adapters with Linux.

Any information and links you can provide are welcome. Submit the information and links by clicking on Issues...or if you are a Github user, submit a Pull Request.

Regards,

Nick.
