2021-01-24

Disclaimer: The authors and contributors to the information on this site cannot be responsible for your use of the information contained in or linked from this site. A best faith effort has been made to provide accurate information but many factors can contribute to less than expected results. You are responsible for ensuring the accuracy of any information you use to make a decision.

## USB WiFi Adapter Information for Linux

USB WiFi adapters provide flexibility as they are easily moved from one location to another and from one computer to another and can even be taken on the road. They come in models for USB 2 and USB 3. Some of the larger adapters work well for desktop use and the smaller adapters, including "nano" adapters, work well for laptops and travel. While Linux enjoys very good in-kernel hardware support in many areas, USB WiFi adapters is an area where there is limited in-kernel support. The support is there and it is slowly improving. The biggest problem most Linux users have when looking to purchase a USB WiFi adapter is being able to reliably identify which adapters have in-kernel support.

This document is informational in nature with the hope that it is of benefit to Linux users, experienced and new. This document does not advocate the purchase of any specific adapter from any specific retailer. Links to products from a wide variety of retailers are welcome. The chipsets are shown in each category and if you are able to find an adapter with the listed chipset, even if it is not one that is specifically listed, it should work. Please double check the chipset with the seller before buying to make sure you are getting what you think you are getting. Also, be aware that the quality of many adapters that are on the market are poor so do your research before buying.

Warning: It is common for online retailers to post "Linux" support. It is best to ignore this statement from most retailers as it is often misleading at best and false as worst. Most retailers and inexperienced users do not understand that the Linux kernel is under constant development which makes it necessary for drivers to be regularly updated in order to work.

### Dual Band USB WiFi Adapters (2.4GHz and 5GHz) that are supported with Linux in-kernel drivers 

Note: In-kernel means that the driver is supported in the Linux kernel which means that you do not need to install a driver. Simply plug the adapter in and it will work. Many people find this solution to be better than buying an adapter that requires drivers to be found, downloaded, compiled and installed.

#### AC1200

##### chipset mt7612u - supported in-kernel since Linux kernel 4.19
[Alfa AWUS036ACM 802.11ac 867 Mbps Long Range WiFi USB Adapter](https://www.ebay.com/itm/Alfa-AWUS036ACM-802-11ac-867-Mbps-Long-Range-WiFi-USB-Adapter-DUAL-BAND-Mediatek/112773755774)

[Alfa Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD) [1]

[NETGEAR AC1200 Wi-Fi USB Adapter High Gain Dual Band USB 3.0 (A6210)](https://www.amazon.com/NETGEAR-AC1200-Wi-Fi-Adapter-A6210-100PAS/dp/B00MRVJY1G)

[Alfa Long-Range Dual-Band AC1200 Wireless USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Alfa-Long-Range-Dual-Band-Wireless-External/dp/B00MX57AO4)

[1200M USB WiFi Adapter 5.8G/866Mbps 2.4G/300Mbps 802.11 AC USB 3.0 Wireless Network Adapter](https://www.amazon.com/Adapter-866Mbps-300Mbps-Wireless-Linx2-6X/dp/B086L3D3NB)

Note: The ad for the above adapter says it uses an mtk7612u chipset but I recommend you check to confirm.

[1200Mbps 5Ghz 2.4Ghz USB Wifi Adapter USB3 Dual Band MT7612U](https://www.newegg.com/p/0XM-02WF-008A5)

Note: The above Comfast adapter appears to be readily available internationally from various online resellers at very good prices so searching the internet for a reseller you trust may be a good idea. It appears that Comfast makes a similar adapter that uses a Realtek chipset so double check to make you are getting the Mediatek MT7612u chipset.)

#### AC600

##### chipset mt7610u - supported in-kernel since Linux kernel 4.19
[Mediatek 11AC USB Wireless Adapter, MT7610U](https://smartguyscomputers.com/product/mediatek-11ac-usb-wireless-adapter-mt7610u)

[Panda Pau0a AC600 Dual Band Wireless USB Adapter](https://www.ebay.com/p/27020163733)

[Asus Dualband Wirel. AC600 USB, USB-AC51](https://www.amazon.com/Asus-Dualband-Wirel-AC600-USB-AC51/dp/B00T3DK154)

[ZyXEL NWD6505 IEEE 802.11ac - Wi-Fi Adapter](https://www.amazon.com/ZyXEL-NWD6505-IEEE-802-11ac-Computer/dp/B00D9F1SLI)

[Linksys AE6000 Wireless Mini USB Adapter](https://www.amazon.com/Linksys-Wireless-Mini-Adapter-AE6000/dp/B00BWT1IFE)

[Alfa - AWUS036ACHM - 802.11ac WiFi Range Boost USB Adapter](https://www.varia-store.com/en/produkt/102561-awus036achm-802-11ac-wifi-range-boost-usb-adapter.html)

[Mini Dual Band 802.11b/g/n 2.4ghz 150M Wifi Stick 5ghz 11AC 433M USB Wifi Adapter](https://www.amazon.com/802-11b-Adapter-802-11AC-Chipset-Wireless/dp/B01LY57UBS)

#### N600

##### chipset rt5572
[Panda Wireless PAU09 N600 Dual Band (2.4GHz and 5GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU09-Adapter-Antennas/dp/B01LY35HGO)

-----

### Single Band USB WiFi Adapters (2.4GHz only) that are supported with Linux in-kernel drivers

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can save a lot of trouble as it will allow you to have a termporary connection to download and install system updates and drivers for other adapters.  

#### N300

##### chipset rt5372
[Panda Wireless PAU06 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU06-300Mbps-Adapter/dp/B00JDVRCI0)

[Panda Wireless PAU05 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-300Mbps-Wireless-USB-Adapter/dp/B00EQT0YK2)

#### N150

##### chipset ar9271 [2]
[AR9271 802.11n 150Mbps Wireless USB WiFi Adapter](https://www.amazon.com/802-11n-150Mbps-Wireless-Adapter-Network/dp/B07FVRKCZJ)

[Quickbuying New Atheros AR9271 150Mbps Wireless USB LAN Adapter](https://www.amazon.com/Quickbuying-Atheros-150Mbps-Wireless-Adapter/dp/B07H3T9W8J)

[Alfa AWUS036NHA - Wireless B/G/N USB Adaptor](https://www.amazon.com/Alfa-AWUS036NHA-Wireless-USB-Adaptor/dp/B004Y6MIXS)

[WiFi Nation USB WiFi Antenna 802.11n, Speed: 150Mbps, Freq. 2.4GHz and 5dBi Antenna, chipset: Atheros AR9271](https://www.amazon.com/WiFi-Nation-Antenna-802-11n-Speed/dp/B08D7S3GL9)

##### chipset rt5370
[CanaKit Raspberry Pi WiFi Wireless Adapter](https://www.amazon.com/dp/B00GFAN498)

[Panda Ultra WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG) [1]

[WiFi for Raspberry Pi](https://www.amazon.com/dp/B00H95C0A2)

[USB WiFi Adapter Ralink RT5370](https://www.amazon.com/Adapter-Raspberry-OlinuXino-OpenSUSE-Injection/dp/B08B3B15CD)

[EASTECH Ralink RT5370 Raspberry PI WiFi Adapter](https://www.amazon.com/Ralink-RT5370-Raspberry-Adapter-Function/dp/B019XUDHFC)

##### chipset rt3070
[ALFA AWUS036NEH Long Range WIRELESS 802.11b/g/n Wi-Fi USB Adapter](https://www.amazon.com/AWUS036NEH-Range-WIRELESS-802-11b-USBAdapter/dp/B0035OCVO6)

##### chipset rt2870 [2]

-----
### Linux out-of-kernel drivers for Dual Band USB WiFi Adapters

Note: The list below is ranked by overall current performance and reliability and probable future performance and reliability - based on my experience working on the drivers, using the adapters and keeping up with information indicating how well the chipset will be supported in the future. The ranking is subject to change.

Note: Out-of-kernel drivers require you to find, download, compile and install the driver source code. The below links provide a lot of information, including information about supported adapters. Nine total chipsets are supported with the following five drivers.

-----

Recent changes below:

- 2021-01-24 - removed warnings about rtl8814au after considerable work on AP mode.
- 2021-01-24 - moved the rtl8812bu up to first place after work to correct problems in AP mode.

-----

##### 1. chipsets rtl8812bu [2] and rtl8822bu - AC1200 (outstanding in client mode) (outstanding in AP mode)
[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

The rtl8812bu chipset will likely see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. That should future proof your investment in adapters based on this chipset. This chipset tends to run cool, which is good, and Realtek currently provides updated driver source code on a regular basis. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

The Good:

- fast in client mode (for an AC1200 chipset)
- runs cool
- good out-of-kernel driver support
- likely in-kernel driver support at some point
- readily available at low prices
- power saving works well

The Bad:

- the really bad quality of some adapters made with this chipset means you need to reseach before buying

-----

##### 2. chipsets rtl8811cu [2], rtl8821cu and rtl8831au - AC600 (excellent in client mode) (outstanding in AP mode)
[Linux Driver for USB WiFi Adapters that use the RTL8811CU, RTL8821CU and RTL8831AU Chipsets](https://github.com/morrownr/8821cu)

The rtl8811cu chipset will likely see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. That should future proof your investment in adapters based on this chipset. This chipset tends to run cool, which is good, and Realtek currently provides updated driver source code on a regular basis. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

-----

##### 3. chipset rtl8812au [2] - AC1200 (excellent in client mode) (outstanding in AP mode)
[Linux Driver for USB WiFi Adapters that use the RTL8812AU Chipset](https://github.com/morrownr/8812au)

The rtl8812au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8812bu chipset for adapters in the AC1200 class. Not many rtl8812au adapters remain available on the market. The above driver is a really good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset.

-----

##### 4. chipsets rtl8811au [2] and rtl8821au - AC600 (very good in client mode) (excellent in AP mode)
[Linux Driver for USB WiFi Adapters that use the RTL8811AU and RTL8821AU Chipsets](https://github.com/morrownr/8821au)

The rtl8811au chipset, like the rtl8812au chipset, is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8811cu chipset for adapters in the AC600 class. Adapters that use the rtl8811au chipset are still available but availability is declining. The above driver is a good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset.

-----

##### 5. chipset rtl8814au [2] - AC1900 (good in client mode) (good in AP mode)
[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

The rtl8814au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. Adapters based on this chipset can really push data at high speed and are still available but are relatively expensive. They need a pretty good amount of current so use with a powered USB 3 hub is recommended. The above driver is a reasonaly good quality driver but we need Realtek to release an updated version of the driver source code as the code for this driver is showing some age. Will Realtek release a new version? I don't know.

The Good:

- fastest USB chipset available for Linux

The Bad:

- future Realtek support unknown

-----

The plan for this site is to collect information and provide links regarding the purchase and use of USB WiFi adapters with Linux.

Any information and links you can provide are welcome. Submit the information and links by clicking on Issues...or if you are a Github user, submit a Pull Request.

Regards,

morrownr

[1] I have and use this adapter

[2] I have an adapter that uses this chipset
