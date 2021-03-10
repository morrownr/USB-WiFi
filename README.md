2021-03-10

Disclaimer: The authors and contributors to this site cannot be responsible for your use of the information contained in or linked from this site. A best faith effort has been made to provide accurate information but many factors can contribute to less than expected results. You are responsible for ensuring the accuracy and applicability of any information you use to make a decision.

## USB WiFi Adapter Information for Linux

Foreword for emphasis: There are many USB WiFi adapters that work without the need to install a driver in Linux. These adapters use drivers that are already in the kernel and are maintained in the kernel. The term ```in-kernel``` is used in this document when referring to drivers that are already in the kernel. With adapters that use in-kernel drivers, simply plug the adapter in and it will work. Some might call this plug and play. Many people find using adapters with in-kernel drivers to be better than buying an adapter that requires drivers to be found, downloaded, compiled and installed.

USB WiFi adapters provide flexibility as they are easily moved from one location to another and from one computer to another and can even be taken on the road. They come in models for USB 2 and USB 3. Some of the larger adapters work well for desktop use and the smaller adapters, including "nano" adapters, work well for laptops and travel. While Linux enjoys very good in-kernel hardware support in many areas, USB WiFi adapters is an area where there is limited in-kernel support. However, the support is there and it is improving. The biggest problem most Linux users have when looking to purchase a USB WiFi adapter is being able to reliably identify which adapters have in-kernel support.

This document attempts to identify currently available adapters with in-kernel driver support. Links are provided to online products. Information regarding out-of-kernel drivers and their quality is also provided. The hope is that this information is of benefit to Linux users, experienced and new. Links to products from a wide variety of retailers are provided and we welcome you to send additional links that can be included. The chipsets are shown in each category and if you are able to find an adapter with the listed chipset, even if it is not an adapter that is specifically listed, it should work.

Warning: It is common for online retailers to post "Linux support." It is best to ignore "Linux support" in online ads as this statement is often misleading at best and false as worst. Most retailers and inexperienced users do not understand that the Linux kernel is under constant development which makes it necessary for out-of-kernel drivers to be regularly updated in order to work on newer kernels. Rule of thumb: Never attempt to install a Linux driver from a CD. Another rule of thumb: Don't take hardware advice from Windows and MAC users. All major Linux distributions have active forums with users ready to give advice. Don't take advice from a single user but seek advice from several users and always ask if the adapter uses in-kernel drivers.

Warning: Beware of "multi-state" USB WiFi adapters. Some USB WiFi adapters have proprietary Windows drivers onboard. When plugged in, they act like a flash drive or CDROM and on Windows will attempt to start installing the Windows driver. That won't work on Linux or MAC or any other non-Windows OS so the adapter sits there in flash drive or CDROM mode. The problem is that the state of the adapter has to be changed for the adapter to show up as the device that you expect, in this case, a WiFi adapter. Most modern Linux distributions ship with a utility called "usb-modeswitch" that will handle this issue for you if it has the correct information for your adapter. It is a good utility but if you buy adapters that are "multi-state," that is one more potential headache you may have to deal with when something goes wrong. Often you can indentify adapters that are "multi-state" as they are advertised as "free driver" or "free installation driver." If you are looking to buy a USB WiFi adapter for use on Linux, MAC OS, *NIX or anything besides Windows, it is a good idea to seek out single-state adapters.

Note: I will not list any products made by TP-Link. TP-Link regularly changes chipsets while keeping the same model number on their products. This makes it very difficult for Linux users to buy a product with a specific chipset with any certainty. Their Linux support is very poor as their product support sites generally only contain very old Linux drivers that won't work with modern distros... if they post any drivers at all. We know that Linux cannot be properly supported like that. This is sad because TP-Link has made a lot of money from Linux by using it inside many of their products, yet they do not return the support. My recommendation is to avoid TP-Link products.

Note: Adapters by two companies need to be highlighted. Every single USB adapter that [Panda](http://www.pandawireless.com/) makes is supported by Linux in-kernel drivers. The quality and reliability of most Panda and [Alfa](https://www.alfa.com.tw/) adapters is good. Not all Alfa adapters use in-kernel drivers. Most of the Alfa adapters that do use in-kernel drivers are listed below. Products by both companies are widely available.

Important: Price and availability of listed adapters is subject to change.

-----

### Dual Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers 


#### AC1200 - USB 3 - 2.4 GHz and 5 GHz


##### chipset mt7612u - supported in-kernel since Linux kernel 4.19

Amazon - $37 - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD) [1]  "single-state"

Rokland - $35 - [ALFA AWUS036ACM 802.11ac Dual Band 2.4/5 GHz WiFi USB Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036acm-802-11ac-dual-band-2-4-5-ghz-wifi-usb-adapter) "single-state" - Info: Rokland advertises free shipping and no tax outside of Florida.

Amazon - $40 - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 Wireless USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Alfa-Long-Range-Dual-Band-Wireless-External/dp/B00MX57AO4) "single-state"

ebay - $35 - [Alfa AWUS036ACM 802.11ac 867 Mbps Long Range WiFi USB Adapter](https://www.ebay.com/itm/Alfa-AWUS036ACM-802-11ac-867-Mbps-Long-Range-WiFi-USB-Adapter-DUAL-BAND-Mediatek/112773755774) "single-state"

Note: The above 4 links are for the Alfa AWUS036ACM adapter. It is an excellent product. It is mid-priced, well made and works well in managed (client) mode, AP mode and monitor mode. This is a single-state adapter meaning that usb-modeswitch is not required. That is a very good thing! Highly recommended.

Amazon - $16 - [TEROW ROW02FD AC1200 USB 3 WiFi Adapter 5G/2.4G 802.11 AC](https://www.amazon.com/gp/product/B086L3D3NB) [1]  "multi-state"

Amazon - $16 - [TEROW ROW02FD USB WiFi Adapter 1200M USB 3.0 5DBI Wireless Network Adapter](https://www.amazon.com/dp/B08F9MXC8Q)  "multi-state"

Note: The above 2 links are for the TEROW ROW02FD. It is a multi-state adapter so it does require usb-modeswitch. Some operating systems, such as the Raspberry Pi OS, need a couple of files edited in order for this adapter to work automatically. I will post a "how-to" later in this document as I have time. If you need the information right now, post an "Issue". Overall performance is very good and the price is good.

Comfast - $28 - [COMFAST CF-WU782AC 5.8GHz USB 3.0 WiFi 1300Mbps 802.11ac Long Distance Adapter](https://comfastwifi.us/comfast-cf-wu782ac-5.8ghz-dual-antenna-usb3-wifi-adapter-1300m?search=CF-WU782AC)  "multi-state"

Note: The above link is for the COMFAST CF-WU782AC. It is a multi-state adapter so it does require usb-modeswitch. Some operating systems, such as the Raspberry Pi OS, need a couple of files edited in order for this adapter to work automatically. I will post a "how-to" later in this document as I have time. If you need the information right now, post an "Issue".

ebay - $17 - [Generic: 1200Mbps Long Range AC1200 Dual Band 5GHz Wireless USB 3.0 WiFi Adapter](https://www.ebay.com/itm/1200Mbps-Long-Range-AC1200-Dual-Band-5GHz-Wireless-USB-3-0-WiFi-Adapter-Antennas/323968481362)  " likely multi-state"

Amazon - $25 - [COMFAST WiFi Dongle CF-926AC 1200Mbps Wireless USB WiFi Adapter](https://www.amazon.com/GorNorriss-Electronics-Gadgets-CF-926AC-1200Mbps/dp/B07TLKDZLB)

Amazon - $37 - [NETGEAR AC1200 Wi-Fi USB Adapter High Gain Dual Band USB 3.0 (A6210)](https://www.amazon.com/NETGEAR-AC1200-Wi-Fi-Adapter-A6210-100PAS/dp/B00MRVJY1G)

AliExpress - $26 - [COMFAST usb wifi Adapter 1200m 2.4g 5g dual-band long distance usb wi-fi receiver 7612U chip](https://www.aliexpress.com/i/32809061461.html)


#### AC600 - USB 2 - 2.4 GHz and 5 GHz


##### chipset mt7610u - supported in-kernel since Linux kernel 4.19

[Mediatek MT7610U 11AC 600Mbps USB 2.0 Wireless Adapter Dual Band White](https://www.ebay.com/itm/363268018762)

[Mediatek 11AC USB Wireless Adapter, MT7610U](https://smartguyscomputers.com/product/mediatek-11ac-usb-wireless-adapter-mt7610u)

[Asus Dualband Wirel. AC600 USB, USB-AC51](https://www.amazon.com/Asus-Dualband-Wirel-AC600-USB-AC51/dp/B00T3DK154)

[ZyXEL NWD6505 IEEE 802.11ac - Wi-Fi Adapter](https://www.amazon.com/ZyXEL-NWD6505-IEEE-802-11ac-Computer/dp/B00D9F1SLI)

[Linksys AE6000 Wireless Mini USB Adapter](https://www.amazon.com/Linksys-Wireless-Mini-Adapter-AE6000/dp/B00BWT1IFE)

[Alfa - AWUS036ACHM - 802.11ac WiFi Range Boost USB Adapter](https://www.varia-store.com/en/produkt/102561-awus036achm-802-11ac-wifi-range-boost-usb-adapter.html)

[Mini Dual Band 802.11b/g/n 2.4ghz 150M Wifi Stick 5ghz 11AC 433M USB Wifi Adapter](https://www.amazon.com/802-11b-Adapter-802-11AC-Chipset-Wireless/dp/B01LY57UBS)

[Panda Pau0a AC600 Dual Band Wireless USB Adapter](https://www.ebay.com/p/27020163733)


#### N600 - USB 2 - 2.4 GHz and 5 GHz


##### chipset rt5572
[Panda Wireless PAU09 N600 Dual Band (2.4GHz and 5GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU09-Adapter-Antennas/dp/B01LY35HGO)

[Kali Linux compatible dual band WiFi sniffer & Packet injection based on RT5572](https://www.ebay.com/itm/Kali-Linux-compatible-dual-band-WiFi-sniffer-Packet-injection-based-on-RT5572/273538484636?hash=item3fb02a099c:g:-1kAAOSwNe9cG~S-)

Note: The above adapter says "Kali Linux compatible" which seems to imply it only works with Kali but that is not the case. This adapter should work with any mainstream Linux distro that is currently supported by its maker. 

[Socobeta RT5572 USB Dual-Band 5.8G/2.4G AC Wireless Network WiFi Adapter](https://www.amazon.com/Socobeta-Network-Dual-Band-Wireless-Adapter/dp/B08MKNH2PJ)

[Panda N600 Dual Band (2.4GHz & 5.0GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-2-4GHz-300Mbps-Wireless-Adapter/dp/B00U2SIS0O)

-----

### Single Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can save a lot of trouble as it will allow you to have a  temporary connection during installation of your Linux distribution if needed. It can also temporary internet access in case you have problems with a wired connection or you need to install the driver for an adapter that requires an out-of-kernel driver. I have a couple of single band adapters. One I keep at home and the other goes on the road with my laptop. These adapters have been handy.  


#### N300 - USB 2 - 2.4 GHz only


##### chipset rt5372
[Panda Wireless PAU06 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU06-300Mbps-Adapter/dp/B00JDVRCI0)

[Panda Wireless PAU05 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-300Mbps-Wireless-USB-Adapter/dp/B00EQT0YK2)

[ASHATA Wireless USB Adapter RT5372 N300](https://www.amazon.com/ASHATA-Wireless-Network-Adapter-DWA-140/dp/B07X264THJ)

[Wendry Wireless USB Adapter, 2.4GHz, DWA-140, RT5372 N300](https://www.amazon.com/Wendry-Wireless-Network-Frequency-Ethernet/dp/B07Y2VKDNJ)


#### N150 - USB 2 - 2.4 GHz only

##### chipset mt7601
[DM-Digital USB WiFi Dongle 2dBi MT7601](https://www.amazon.com/DM-Digital-USB-WiFi-Dongle-MediaTek/dp/B0783QRGFR)

##### chipset rt5370
[Panda Mid Range 150Mbps Wireless N USB Adapter w/ 2dBi Antenna](https://www.amazon.com/gp/product/B004AC0L4Y)

[CanaKit Raspberry Pi WiFi Wireless Adapter](https://www.amazon.com/dp/B00GFAN498)

[Panda Ultra WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG) [1]

[Raspberry Pi Pi 2 Pi 3 USB Wireless Adapter Mideatek RT5370N With 2 dBi Antenna 802.11 n g b USB 2.0](https://www.amazon.com/Connecting-Wireless-Adapter-150Mbps-Raspberry/dp/B073J3HXZH)

[WiFi for Raspberry Pi](https://www.amazon.com/dp/B00H95C0A2)

[USB WiFi Adapter Ralink RT5370](https://www.amazon.com/Adapter-Raspberry-OlinuXino-OpenSUSE-Injection/dp/B08B3B15CD)

[EASTECH Ralink RT5370 Raspberry PI WiFi Adapter](https://www.amazon.com/Ralink-RT5370-Raspberry-Adapter-Function/dp/B019XUDHFC)

[Wireless WiFi USB Dongle Stick Adapter RT5370 150Mbps](https://www.amazon.com/Wireless-Adapter-150Mbps-Set-Top-Raspberry/dp/B01KWQAQ00)


##### chipset ar9271 [2]
[AR9271 802.11n 150Mbps Wireless USB WiFi Adapter](https://www.amazon.com/802-11n-150Mbps-Wireless-Adapter-Network/dp/B07FVRKCZJ)

[ALFA AWUS036NHA 802.11n Wireless-N Wi-Fi USB Adapter High Speed Atheros AR9271](https://www.ebay.com/itm/ALFA-AWUS036NHA-802-11n-Wireless-N-Wi-Fi-USB-Adapter-High-Speed-Atheros-AR9271/380458349886?epid=1600491254&hash=item589515b53e:g:zW8AAOSwnCFaQ9Oe)

[Atheros High Gain Wireless USB Wifi Adapter Dongle 150Mbps Linux Kali AR9271](https://www.ebay.com/itm/Atheros-High-Gain-Wireless-USB-Wifi-Adapter-Dongle-150Mbps-Linux-Kali-AR9271/274638885360?hash=item3ff1c0d1f0:g:L3QAAOSwh6xfvdL5)

[Quickbuying New Atheros AR9271 150Mbps Wireless USB LAN Adapter](https://www.amazon.com/Quickbuying-Atheros-150Mbps-Wireless-Adapter/dp/B07H3T9W8J)

[Alfa AWUS036NHA - Wireless B/G/N USB Adaptor](https://www.amazon.com/Alfa-AWUS036NHA-Wireless-USB-Adaptor/dp/B004Y6MIXS)

[WiFi Nation USB WiFi Antenna 802.11n, Speed: 150Mbps, Freq. 2.4GHz and 5dBi Antenna, chipset: Atheros AR9271](https://www.amazon.com/WiFi-Nation-Antenna-802-11n-Speed/dp/B08D7S3GL9)


##### chipset rt3070
[Panda Mini WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Mini-150Mbps-Wireless-Adapter/dp/B003283M6Q)

[Deal4GO RT3070 802.11n 150Mbps Wireless USB WiFi Adapter for Kali Linux Ubuntu](https://www.amazon.com/Deal4GO-802-11n-150Mbps-Wireless-Archlinux/dp/B08QZDGWJC)

[INTELLINET IEEE 802.11b/g/n Wireless 150N High-Power USB Adapter](https://www.amazon.com/INTELLINET-802-11b-Wireless-High-Power-525152/dp/B005HF6H28)

[Deal4GO RT3070 802.11n 150Mbps Wireless USB WiFi Adapter WLAN w/ YP243433 Power Amplifier for Ralink RT3070L WiFi Module Kali Linux Ubuntu](https://www.amazon.com/Deal4GO-RT3070-Wireless-YP243433-Amplifier/dp/B086D72XR6)

[coolxan USB Rt3070 Chipset 802.11n 150m WiFi Wireless-n Adapter](https://www.amazon.com/Rt3070-Chipset-802-11n-Wireless-n-Adapter/dp/B00NAXX40C)

[Goliton Wireless Network Adapter RT3070 WiFi](https://www.amazon.com/Goliton-Wireless-Network-Transmitter-Receiver/dp/B016I6DJ5C)

[ALFA AWUS036NEH Long Range WIRELESS 802.11b/g/n Wi-Fi USB Adapter](https://www.amazon.com/AWUS036NEH-Range-WIRELESS-802-11b-USBAdapter/dp/B0035OCVO6)


-----
### Linux out-of-kernel drivers for Dual Band USB WiFi Adapters

Note: The list below is ranked by overall current performance, reliability and probable future performance and reliability - based on my experience working on the drivers, using the adapters and keeping up with information indicating how well the chipset will be supported in the future. The ranking is subject to change.

Note: Out-of-kernel drivers require you to find, download, compile and install the driver source code. The below links provide a lot of information, including information about supported adapters. Nine total chipsets are supported with the following five drivers.

-----

Recent changes below:

- 2021-01-24 - removed warnings about rtl8814au after considerable work on AP mode.
- 2021-01-24 - moved the rtl8812bu up to first place after work to correct problems in AP mode.

-----

##### 1. chipsets rtl8812bu [2] and rtl8822bu - AC1200 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

The rtl8812bu chipset may see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. This chipset tends to run cool, which is good, and Realtek currently provides updated out-of-kernel driver source code on a regular basis. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

The Good:

- fast in client mode (for an AC1200 chipset)
- runs cool
- good out-of-kernel driver support
- possible in-kernel driver support at some point
- readily available at low prices
- power saving works well

The Bad:

- the really bad quality of some adapters made with this chipset means you need to reseach before buying

-----

##### 2. chipsets rtl8811cu [2], rtl8821cu and rtl8831au - AC600  - USB 2
[Linux Driver for USB WiFi Adapters that use the RTL8811CU, RTL8821CU and RTL8831AU Chipsets](https://github.com/morrownr/8821cu)

The rtl8811cu chipset may see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. This chipset tends to run cool, which is good, and Realtek currently provides updated out-of-kernel driver source code on a regular basis. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

The Good:

- fast enough for most users
- runs cool
- good out-of-kernel driver support
- possible in-kernel driver support at some point
- readily available at low prices
- power saving works well

The Bad:

- the really bad quality of some adapters made with this chipset means you need to reseach before buying

-----

##### 3. chipset rtl8812au [2] - AC1200 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8812AU Chipset](https://github.com/morrownr/8812au)

The rtl8812au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8812bu chipset for adapters in the AC1200 class. Not many rtl8812au adapters remain available on the market. The above driver is a really good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset.

The Good:

- best out-of-kernel driver of the 5 listed here, very solid
- AP mode is outstanding
- power saving works well

The Bad:

- future Realtek support unknown
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8812bu

-----

##### 4. chipsets rtl8811au [2] and rtl8821au - AC600 - USB 2
[Linux Driver for USB WiFi Adapters that use the RTL8811AU and RTL8821AU Chipsets](https://github.com/morrownr/8821au)

The rtl8811au chipset, like the rtl8812au chipset, is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8811cu chipset for adapters in the AC600 class. Adapters that use the rtl8811au chipset are still available but availability is declining. The above driver is a good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset.

The Good:

- AP mode is excellent
- power saving works well

The Bad:

- future Realtek support unknown
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8811cu

-----

##### 5. chipset rtl8814au [2] - AC1900 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

The rtl8814au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. Adapters based on this chipset can really push data at high speed and are still available but are relatively expensive. They need a pretty good amount of current so use with a powered USB 3 hub may be a good idea. This chipset builds a lot of heat so look for adapters that have plenty of vent holes and search reviews to see if users are reporting heat problems. The above driver is a reasonaly good quality driver but the source is from 2019. We need Realtek to release an updated version of the driver source code as the code for this driver (2019) is showing some age. Will Realtek release a new version? I don't know.

The Good:

- fastest USB chipset available for Linux

The Bad:

- future Realtek support unknown
- uses a lot of current so using a powered hub may be a good idea depending on your setup
- produces a lot of heat, adapter needs a lot of vent holes
- expensive

-----
Adapter Reviews: 

2012-03-03

AC1200+ USB 3 WiFi Adapter Comparison
```
Adapter			Chipset			USB Capability
MaxPower		Device ID		Visible Antennas
iperf3 Test		Link Quality		Signal Level

(1)
Alfa AWUS036ACH         rtl8812au         	USB3
800mA			ID 0bda:8812		2
309 Mb/s		Link Quality=99/100  	Signal level=-43 dBm

(2)
Cudy WU1400             rtl8812bu               USB3
504mA                   ID 0bda:b812            1
291 Mb/s                Link Quality=84/100     Signal level=-51 dBm     

(3)
Alfa AWUS036ACM         mt7612u                 USB3
400mA                   ID 0e8d:7612            2
237 Mb/s                Link Quality=79/100     Signal level=-55 dBm

(4)
Generic (brown box)     rtl8812bu               USB3
504mA                   ID 0bda:b812            2      
216 Mb/s                Link Quality=70/100     Signal level=-61 dBm

(5)
Generic (brown box)     rtl8814au               USB3
864mA                   ID 0bda:8813            2
204 Mb/s                Link Quality=86/100     Signal level=-50 dBm
```

Test conditions:

Distance from adapters to AP was about 40 feet (2 walls).

iperf3 server is running on a Raspberry Pi 4b that is connected to the
network via CAT 6 ethernet cable.

Adapters were connected to a rear USB 3 port on a Dell Optiplex 9020
with an i7 processor running Linux Mint 20.1.

Utilities used include wavemon, iw and iperf3.

iperf3 test: $ iperf3 -c 192.168.1.40 -t 60

Analysis:

This is a limited test based on a user request. I'll plan on expanding
the test as time permits.

If I have to declare an overall winner from the current top 3 adapters,
it would be this adapter:
```
Alfa AWUS036ACM
```
The reason for picking the above adapter is that it did a good job in
all categories.

Here are the categories.

-----

If price is important:
```
Cudy WU1400       (low price)
Alfa AWUS036ACM   (mid price)
Alfa AWUS036ACH   (very high price)
```
-----

If a strong signal is important:
```
Alfa AWUS036ACH   (astoundingly good)
Cudy WU1400       (very good)
Alfa AWUS036ACM   (very good)
```
-----

If having the adapter supported in the Linux kernel is
important, so that it is not necessary to find, download,
and compile a driver, of the ones tested, this is your only
option:
```
Alfa AWUS036ACM		(it is a very good driver)
```
-----

If AP mode is important:
```
Alfa AWUS036ACM
Alfa AWUS036ACH
```
-----

If fast managed (client) mode is important:
```
Cudy WU1400
Alfa AWUS036ACH
Alfa AWUS036ACM
```
-----

If monitor mode is important:
```
Alfa AWUS036ACM
Alfa AWUS036ACH
```
-----

If low power usage is important, such as if you are
going to use it with a Raspberry Pi 4b:
```
Alfa AWUS036ACM
Cudy WU1400
```
-----

If not having to worry about future driver support
is important:
```
Alfa AWUS036ACM
Cudy WU1400
```
-----

If having the the device driver support current Linux
Wireless standards is important:
```
Alfa AWUS036ACM
```
-----

If having a clear path to report driver problems is
important:
```
Alfa AWUS036ACM
```
-----

Link to MT76 driver in the Linux kernel:

https://github.com/torvalds/linux/tree/master/drivers/net/wireless/mediatek/mt76

-----

Link to RTL88X2B driver in the Linux kernel:

https://github.com/torvalds/linux/tree/master/drivers/net/wireless/realtek/rtw88

Note: This driver does not support usb adapters yet but there is hope.

-----

Link to RTL8812AU driver in the Linux kernel:

It does not exist and likely will never exist. My opinion is that we will never
see a fully Linux Wireless standards compliant driver for the rtl8812au chipset.

-----

Hopefully this document is of help to Linux users that want or need USB 3 WiFi
adapter support. I will look to expand this document in the future.

-----

The mission of this site is to collect information and provide links regarding the purchase and use of USB WiFi adapters with Linux.

Any information and links you can provide are welcome. Submit the information and links by clicking on Issues...or if you are a Github user, submit a Pull Request.

Regards,

morrownr

[1] I have and use this adapter

[2] I have an adapter that uses this chipset
