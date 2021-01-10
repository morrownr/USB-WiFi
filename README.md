2021-01-09

## USB WiFi Adapter Information for Linux

USB WiFi adapters provide flexibility in that they are easily moved from one location to another and from one computer to another and can even be taken on the road. They come in models for USB 2 and USB 3. Some of the larger adapters work well for desktop use and the smaller adapters, including "nano" adapters, work well for travel. While Linux enjoys very good in-kernel hardware support in many areas, USB WiFi adapters is not one of the those areas. The support is there and it is slowly improving. The biggest problem most Linux users have is being able to reliably identify which adapters have in-kernel support. This document is educational in nature with the hope that it is of benefit to Linux users, experienced and new. I am not advocating the purchase of any adapter from any specific retailer and I welcome links to products from a wide variety of retailers. The chipsets are shown in each category and if you are able to find an adapter with the listed chipset, even if it is not one that is specifically listed, it should work. Please double the chipset with the seller before buying to make sure you are getting what you think you are getting.

Warning: It is common for online retailers to post "Linux" support. It is best to ignore information from most retailers as much of it is misleading at best and false as worst. Most retailesr and inexperienced users do not understand that the Linux kernel is under constant development which makes it necessary for drivers to be regularly updated in order to work.

### Dual Band USB WiFi Adapters (2.4GHz and 5GHz) that are supported with Linux in-kernel drivers 

Note: In-kernel means that the driver is supported in the Linux kernel which means that you do not need to install a driver. Simply plug the adapter in and it will work. Many people find this solution to be better than buying an adapter that requires drivers to be found, downloaded, compiled and installed.

###### chipset mt7612u - AC1200
[Alfa Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD)

[Alfa Long-Range Dual-Band AC1200 Wireless USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Alfa-Long-Range-Dual-Band-Wireless-External/dp/B00MX57AO4)

[1200M USB WiFi Adapter 5.8G/866Mbps 2.4G/300Mbps 802.11 AC USB 3.0 Wireless Network Adapter](https://www.amazon.com/Adapter-866Mbps-300Mbps-Wireless-Linx2-6X/dp/B086L6TR6G)

[1200Mbps 5Ghz 2.4Ghz USB Wifi Adapter USB3 Dual Band MT7612U](https://www.newegg.com/p/0XM-02WF-008A5)

Note: The above Comfast adapter appears to be readily available internationally from various online resellers at very good prices so searching the internet for a reseller you trust may be a good idea. It appears that Comfast makes a similar adapter that uses a Realtek chipset so double check to make you are getting the Mediatek MT7612u chipset.)

###### chipset mt7610u - AC600
[Mini Dual Band 802.11b/g/n 2.4ghz 150M Wifi Stick 5ghz 11AC 433M USB Wifi Adapter](https://www.amazon.com/802-11b-Adapter-802-11AC-Chipset-Wireless/dp/B01LY57UBS)

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

###### chipset mt7601u - N150
[Zibo Mini USB Wifi Wireless Adapter](https://www.amazon.com/Zibo-Wireless-Adapter-150Mbps-Supports/dp/B00RBBUQLE)

###### chipset rt5370 - N150
[CanaKit Raspberry Pi WiFi Wireless Adapter](https://www.amazon.com/dp/B00GFAN498)

[Panda Ultra WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG)

[WiFi for Raspberry Pi](https://www.amazon.com/dp/B00H95C0A2)

[USB WiFi Adapter Ralink RT5370](https://www.amazon.com/Adapter-Raspberry-OlinuXino-OpenSUSE-Injection/dp/B08B3B15CD)

[EASTECH Ralink RT5370 Raspberry PI WiFi Adapter](https://www.amazon.com/Ralink-RT5370-Raspberry-Adapter-Function/dp/B019XUDHFC)

###### chipset rt3070 - N150

[ALFA AWUS036NEH Long Range WIRELESS 802.11b/g/n Wi-Fi USB Adapter](https://www.amazon.com/AWUS036NEH-Range-WIRELESS-802-11b-USBAdapter/dp/B0035OCVO6)

-----
### Linux out-of-kernel drivers for Dual Band USB WiFi Adapters (ranked by quality)

Note: Out-of-kernel drivers require you to find, download, compile and install the driver source code. The below links provide a lot of information, including information about supported adapters.

###### chipset rtl8812au - AC1200 (excellent driver in managed mode) (outstanding driver in AP mode - 80211ac, 867 Mb/s, channel width 80)
[Linux Driver for USB WiFi Adapters that use the RTL8812AU Chipset](https://github.com/morrownr/8812au)

###### chipsets rtl8811au and rtl8821au - AC 600 (very good driver in managed mode) (excellent driver in AP mode - 80211ac, 434 Mb/s, channel width 80)
[Linux Driver for USB WiFi Adapters that use the RTL8811AU and RTL8821AU Chipsets](https://github.com/morrownr/8821au)

######  chipsets rtl8812bu and rtl8822bu - AC1200 (very good driver in managed mode) (AP mode testing in progress)
[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

###### chipsets rtl8811cu, rtl8821cu and rtl8831au - AC 600 (very good driver in managed mode)  (AP mode testing in progress)
[Linux Driver for USB WiFi Adapters that use the RTL8811CU, RTL8821CU and RTL8831AU Chipsets](https://github.com/morrownr/8821cu)

###### Adapters based on the below chipsets should be avoided as the quality of the driver available is poor

###### chipset rtl8814au - AC1900 (fair driver in managed mode) (bad driver in AP mode)
[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

-----

The plan for this site is to collect information and provide links regarding the use of USB WiFi adapters with Linux.

Any information and links you can provide are welcome. Submit the information and links by clicking on Issues...or if you are a Github user, submit a Pull Request.

Regards,

Nick
