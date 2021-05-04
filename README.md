2021-05-04

Disclaimer: The authors and contributors to this site cannot be responsible for the results of your use of the information contained in or linked from this site. We attempt to provide accurate information but many factors can contribute to less than expected results. You are responsible for ensuring the accuracy and applicability of any information you use to make a decision.

Foreword: There are many USB WiFi adapters that work without the need to install a driver in Linux. These adapters use drivers that are already in the kernel and are maintained in the kernel. The term `in-kernel` is used in this document when referring to drivers that are already in the kernel. With adapters that use in-kernel drivers, simply plug the adapter in and it will work. Some might call this plug and play. Many people find using adapters with in-kernel drivers to be better than buying an adapter that requires drivers to be found, downloaded, compiled and installed.

## USB WiFi Adapter Information for Linux

USB WiFi adapters provide flexibility as they are easily moved from one location to another and from one computer to another and can even be taken on the road. They come in models for USB 2 and USB 3. Some of the larger adapters work well for desktop use and the smaller adapters, including "nano" adapters, work well for laptops and travel. It is important that you pick an adapter to match the expected usage. If you are going to be traveling with the adapter, the adapters with long antennas may not not work well as the adapter may be broken. On the other hand, if you need an adapter for a desktop system that is on the other end of the house from your AP/Router, you probably need the better signal capability of the larger antennas. Researching the issue before buying is a good idea.

Linux enjoys very good in-kernel hardware support in many areas but support is somewhat limited when it comes to USB WiFi adapters. The main reason for the limited support is that there are only 2 companies supplying chipsets for USB Wifi adapters - Mediatek and Realtek. Intel is not supplying USB capable chipsets and Atheros is not supplying modern USB capable chipsets. Of the two suppliers that do provide USB Wifi chipsets, Mediatek supports drivers for their chipsets the right way, in-kernel. Mediatek drivers are Linux Wireless standards compliant and are updated constantly without users having to worry about it. Realtek does not support their modern USB Wifi chipsets with in-kernel drivers. Realtek does make Linux drivers but does not publically release them or take problem reports. We have to search for them from some adapter vendors that may post them. These drivers are released in source code format and must be compiled to be used. The Realtek drivers do not keep up with the needed changes as new kernels are released. This job seems to rest with folks like myself in the community. Am I a fan of how the Realtek USB team supports the Linux community? No. What do I recommend? Buy adapters based on chipsets from the company that is doing it right - Mediatek. The biggest problem most Linux users have when looking to purchase a USB WiFi adapter is being able to reliably identify which adapters have in-kernel support and that is really the reason for this site. Spreading this information far and wide is key to having happy Linux users so please do spread this information.

This document attempts to identify currently available adapters that use in-kernel driver support. Links are provided to online products. Information regarding out-of-kernel drivers and their quality is also provided. The hope is that this information is of benefit to Linux users, experienced and new. Links to products from a wide variety of retailers are provided and we welcome you to send additional links that can be included. The chipsets are shown in each category and if you are able to find an adapter with the listed chipset, even if it is not an adapter that is specifically listed, it should work.

[Linux Wireless - Mediatek](https://wireless.wiki.kernel.org/en/users/drivers/mediatek) is a good place to get an idea of the various Mediatek wifi chipsets that are supported in the Linux kernel. If you want to look in the kernel to see the drivers, [look here](https://github.com/torvalds/linux/tree/master/drivers/net/wireless/mediatek).

Warning: It is common for online retailers to post "Linux support." It is best to ignore "Linux support" in online ads as this statement is often misleading at best and false at worst. Most inexperienced users do not understand that the Linux kernel is under constant development which makes it necessary for out-of-kernel drivers to be regularly updated in order to work on newer kernels. Rule of thumb: Never attempt to install a Linux driver from a CD. The driver will be old and will likely do nothing more than make a mess of your system. Remember that `sudo` is a weapon of mass destruction if used without knowing what you are doing. Another rule of thumb: Don't take hardware advice from Windows and MAC users. All major Linux distributions have active forums with users ready to give advice. Don't take advice from a single user but seek advice from several users and always ask if the adapter uses in-kernel drivers.

Warning: Beware of "multi-state" USB WiFi adapters. Some USB WiFi adapters have proprietary Windows drivers onboard. When plugged in, they act like a flash drive or CDROM and on Windows will attempt to start installing the Windows driver. That won't work on Linux or MAC or any other non-Windows OS so the adapter sits there in flash drive or CDROM mode. The problem is that the state of the adapter has to be changed for the adapter to show up as the device that you expect, in this case, a WiFi adapter. Most modern Linux distributions ship with a utility called "usb-modeswitch" that will handle this issue for you if it has the correct information for your adapter. It is a good utility but if you buy adapters that are "multi-state," that is one more potential headache you may have to deal with when something goes wrong. Often you can indentify adapters that are "multi-state" as they are advertised as "free driver" or "free installation driver." If you are looking to buy a USB WiFi adapter for use on Linux, MAC OS, *NIX or anything besides Windows, it is a good idea to seek out single-state adapters.

Note: I will not list any products made by TP-Link and D-Link. Both companies regularly change chipsets while keeping the same model number on their products. This makes it very difficult for Linux users to buy a product with a specific chipset with any degree of certainty. Their Linux support is very poor as their product support sites generally only contain very old Linux drivers that won't work with modern distros... if they post any drivers at all. We know that Linux cannot be properly supported like that. This is sad because both companies have made a lot of money from Linux by using it inside many of their products, yet they do not return the support. My recommendation is to avoid TP-Link and D-Link products.

Note: Adapters made by two companies need to be highlighted. Every single USB adapter that Panda makes is supported by Linux in-kernel drivers. The quality and reliability of most [Panda](http://www.pandawireless.com/) and [Alfa](https://www.alfa.com.tw/) adapters is good... really good. Not all Alfa adapters use in-kernel drivers. Most of the Alfa adapters that do use in-kernel drivers are listed below. Products by both companies are widely available.

WPA-3 SAE support: I completed extensive testing of several adapters today (2120-04-27). I tested adapters ranging from N150 to AC1200. Chipsets tested include mt7612u, mt7610u and rt2870. The client system was running Ubuntu 21.04. The access point was a Raspberry Pi 4b running the current version of the RasPiOS and hostapd. The RasPi internal wifi capability was turned off and I used two usb WiFi adapters. One based on the mt7612u chipset for 5 GHZ and one based on the rt2870 chipset for the 2 Ghz support. All tests showed good results with WPA-3 SAE and WPA-3 Transition mode. It appears that the in-kernel Mediatek/Ralink drivers support WPA-3 all the way back to the old days when N150 was king. Good stuff.

Important: Price and availability of listed adapters is subject to change. Updating the list of adapters does take a considerable amount of time. I try to complete a review of the links at least every 2 weeks. This site has increased in popularity to the point that readers of this site may cause inventory problems for some sellers at times so you may need to wait for inventory to be refreshed. To help with this problem, I have listed multiple links from multiple sellers for some products. If you see any problems, please post in `Issues.`

Market Conditions: I have been seeing a lot of variability in pricing, mostly to the up side. The global shortage of chips caused by fab plants being shut down for periods during 2020 has led to tight markets and very high and rising prices for some products. This may continue for some time. If you are on a budget, you might want to search for used adapters.

-----

### Dual Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers 

-----

#### AC1200 / AC1300 - USB 3 - 2.4 GHz and 5 GHz (WIFI 5)


##### ```chipset - Mediatek mt7612u - supported in-kernel since Linux kernel 4.19``` - [mt7612u information](https://github.com/morrownr/7612u)

--- Alfa AWUS036ACM ---

Rokland - $35 USD - [ALFA AWUS036ACM 802.11ac Dual Band USB WiFi Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036acm-802-11ac-dual-band-2-4-5-ghz-wifi-usb-adapter) - Info: free shipping and no tax outside of Florida.

ebay - $35 USD - [Alfa AWUS036ACM 802.11ac 867 Mbps Long Range WiFi USB Adapter](https://www.ebay.com/itm/Alfa-AWUS036ACM-802-11ac-867-Mbps-Long-Range-WiFi-USB-Adapter-DUAL-BAND-Mediatek/112773755774)

Amazon - $37 USD - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD) [1]

Google Shopping - $35-$41 USD - [ALFA AWUS036ACM Dual-Band Network Adapter](https://www.google.com/shopping/product/1997251945503725000)

Amazon - $40 USD - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 Wireless USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Alfa-Long-Range-Dual-Band-Wireless-External/dp/B00MX57AO4)

```
Alfa AWUS036ACM Technical information
- Supported interface modes:
	-- IBSS
	-- managed
	-- AP
	-- AP/VLAN
	-- monitor
	-- mesh point
	-- P2P-client
	-- P2P-GO
- Supported interface combinations:
  -- #{ managed } <= 1, #{ P2P-device } <= 1, #{ P2P-client, P2P-GO } <= 1, total <= 3, #channels <= 2 
  -- #{ managed } <= 1, #{ AP } <= 1, #{ P2P-client } <= 1, #{ P2P-device } <= 1, total <= 4, #channels <= 1
- hostapd.conf:
  -- ht_capab=[LDPC][HT40+][HT40-][GF][SHORT-GI-20][SHORT-GI-40][TX-STBC][RX-STBC1]
  -- vht_capab=[RXLDPC][SHORT-GI-80][TX-STBC-2BY1][RX-STBC-1][MAX-A-MPDU-LEN-EXP3][RX-ANTENNA-PATTERN][TX-ANTENNA-PATTERN]
- Device ID: 0e8d:7612
- usb-modeswitch not required. This is a single state device.
- WPA-3 SAE: supported (your operating system and wifi router/access point must also support WPA-3 for it work)
- Power requirements: Heavy load: ~380 mA, light load: ~180 mA
```
Review by Nick - The Alfa AWUS036ACM is an excellent product. It is mid-priced, well made and works well in managed mode, master mode and monitor mode. It can sustain 400+ Mb/s in AP mode. It runs cool and uses a maximum of only about 380 mA power when under heavy load (that is not much.) Works so well with the Raspberry Pi 4B, 3B+ and 3B, it is almost like it was designed specifically for that hardware. Highly recommended.

--- Netgear A6210 ---

ebay - $27 USD - [NETGEAR AC1200 USB 3.0 Wi-Fi Adapter - A6210-10000S](https://www.ebay.com/p/18021987463) "single-state"

Walmart - $30 USD - [NETGEAR AC1200 Dual Band Wifi USB Adapter (A6210-100PAS)](https://www.walmart.com/ip/NETGEAR-AC1200-Dual-Band-Wifi-USB-Adapter-A6210-100PAS/40164604) "single-state"

Amazon - $32-$74 USD - [NETGEAR AC1200 Wi-Fi USB Adapter High Gain Dual Band USB 3.0 (A6210)](https://www.amazon.com/NETGEAR-AC1200-Wi-Fi-Adapter-A6210-100PAS/dp/B00MRVJY1G) "single-state"

Best Buy - $55 USD - [NETGEAR - AC1200 Dual-Band WiFi USB 3.0 Adapter - Black](https://www.bestbuy.com/site/netgear-ac1200-dual-band-wifi-usb-3-0-adapter-black/8860004.p?skuId=8860004) "single-state"

Review - No reviews available at this time. It appears to be a more compact adapter that would travel better than the larger dual antenna devices. If you own one, we would appreciate a product review.

--- TEROW ROW02FD ---

Amazon - $16 USD - [TEROW ROW02FD AC1200 USB 3 WiFi Adapter 5G/2.4G 802.11 AC](https://www.amazon.com/gp/product/B086L3D3NB) [1] ID 0e8d:7612 MediaTek Inc. Wireless - "multi-state"

Amazon - $14 USD - [TEROW ROW02FD USB WiFi Adapter 1200M USB 3.0 5DBI Wireless Network Adapter](https://www.amazon.com/dp/B08F9MXC8Q) "multi-state"

ebay - $23 USD - [TEROW ROW02FD AC1200M USB WiFi Adapter for PC/Desktop/Laptop 5.8G/2.4G](https://www.ebay.com/itm/353467500844) "multi-state"

Review by Nick - The TEROW ROW02FD is a multi-state adapter so it does require usb-modeswitch. WPA3 works. Supports interface combinations - `#{ IBSS } <= 1, #{ managed, AP, mesh point } <= 2, total <= 2, #channels <= 1, STA/AP BI must match` Works very well with the Raspberry Pi 4B, 3B+ and 3B. The cost of this adapter is very low. The performance and quality of the materials used and capabilities of this adapter are not quite as good as the Alfa AWUS036ACM but that is to be expected since the Alfa AWUS036ACM is a more expensive adapter. My experience is that this adapter does provide good performance. In fact, during my testing, it outperformed in link quality and signal level vs. a similar adapter based on a rtl8812bu chipset when plugged into the same USB3 port and connected to the same wifi router.

Additional information about the TEROW ROW02FD - 2021-04-04 - The Raspberry Pi OS, Kali and the current stable version of Debian, as of this date, need a couple of files edited in order for this adapter to work automatically. For more information, see the following section below - `How to Modeswitch`. To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the above adapter will "just work." The only modern Linux distros that I am aware of that have this problem with this spectifc adapter are the Raspberry Pi OS, Kali and Debian stable and that is due to some parts of the OS being somewhat dated at this point. As the OS is updated this problem will go away.

--- COMFAST CF-WU782AC ---

AliExpress - $20 USD - [Comfast USB 3.0 Wireless Wifi Adapter Dual Band 2.4+5 GHz 150 -1300 Mbps 802.11AC 802.11 a/b/n/g/ac with 2*6dbi Antennas](https://www.aliexpress.com/item/32902591576.html)

Comfast - $28 USD - [COMFAST CF-WU782AC 5.8GHz USB 3.0 WiFi 1300Mbps 802.11ac Long Distance Adapter](https://comfastwifi.us/comfast-cf-wu782ac-5.8ghz-dual-antenna-usb3-wifi-adapter-1300m?search=CF-WU782AC)

Walmart - $29 USD - [COMFAST CF-WU782AC](https://www.walmart.com/ip/COMFAST-CF-WU782AC-Wireless-Network-Card-Dual-Antenna-High-Power-WIFI-Signal-Extender-1300Mbps-Wireless-Routing-AP/728697397)

Review by soyersoyer - The COMFAST CF-WU782AC works well with my RasPi4b (and hostapd). I had to use the disable_usb_sg=1 parameter. I like this setup because it can route near gigabit speeds. My mobile devices have 300-500mbit/s download speed too, it has guest wifi, and I can easily switch to a newer wifi adapter later. The rpi runs kodi, a shairport server and a bluetooth sound receiver server too. I bought the wifi adapter from AliExpress.

Additional information about the COMFAST CF-WU782AC - it is a multi-state adapter so it does require usb-modeswitch. 2021-04-04 - The Raspberry Pi OS, Kali and the current stable version of Debian, as of this date, need a couple of files edited in order for this adapter to work automatically. For more information, see the following section below - `How to Modeswitch`. To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the above adapter will "just work." The only modern Linux distros that I am aware of that have this problem with this spectifc adapter are the Raspberry Pi OS, Kali and Debian stable and that is due to some parts of the OS being somewhat dated at this point. As the OS is updated this problem will go away.

--- Various links ---

Important: The following links are for adapters where I have limited information but either the ad or driver download indicates the adapter is based on the mt7612u or mt7612un chipsets. Take your time and research each with care before buying and make sure you can return the adapter if it is not the right product. Please report success or failure so that the information can be included here.

--- COMFAST CF-WU785AC ---

ebay - $25 USD - [1300Mbps 2.4G/5G Dual Band USB 3.0 WiFi Adapter w/Antenna for Desktop/Mac/Laptop](https://www.ebay.com/itm/1300Mbps-2-4G-5G-Dual-Band-USB-3-0-WiFi-Adapter-w-Antenna-for-Desktop-Mac-Laptop-/393109714195)

AliExpress - $22 USD - [Comfast 1300Mbps WI-FI Receiver 4*6dBi Dual Band Antenna Driver-Free Long Range Network Card 2.4&5GHz Desktop Adapter CF-WU785AC](https://www.aliexpress.com/item/1005002533185743.html)

--- COMFAST CF-926AC ---

Amazon - $25 USD - [COMFAST WiFi Dongle CF-926AC 1200Mbps Wireless USB WiFi Adapter](https://www.amazon.com/GorNorriss-Electronics-Gadgets-CF-926AC-1200Mbps/dp/B07TLKDZLB) "multi-state" Use caution: it appears there is a v2 of the CF-926AC that uses a non-Mediatek chipset. The ad for this link specifically says that it uses a Mediatek mt7612u chipset.

AliExpress - $26 USD - [COMFAST usb wifi Adapter 1200m 2.4g 5g dual-band long distance usb wi-fi receiver 7612U chip](https://www.aliexpress.com/i/32809061461.html) "multi-state" Use caution: it appears there is a v2 of the CF-926AC that uses a non-Mediatek chipset. The ad for this link specifically says that it uses a Mediatek mt7612u chipset.

--- TEROW ROW12CD ---

Amazon - $14 USD - [TEROW ROW12CD Wireless USB WiFi Adapter for PC, AC1200Mbps 5G/2.4G Dual Band 5dBi High Gain Antenna WiFi Wireless Adapter](https://www.amazon.com/dp/B086L86NG1)

--- TEROW ROW02CD ---

Amazon - $14 USD - [TEROW ROW02CD AC1200M USB WiFi Adapter for PC/Desktop/Laptop 5.8G/2.4G 5dBi Dual Band Wireless Network Adapter USB 3.0](https://www.amazon.com/dp/B086L6TR6G)

--- Generic ---

Walmart - $29 USD - [Dual Band USB 3.0 WiFi Receiver 1200M MT7612U Gigabit Wireless Network Card](https://www.walmart.com/ip/Dual-Band-USB-3-0-WiFi-Receiver-1200M-MT7612U-Gigabit-Wireless-Network-Card/153105771)

ebay - $17 USD - [1200Mbps Long Range AC1200 Dual Band 5GHz Wireless USB 3.0 WiFi Adapter](https://www.ebay.com/itm/1200Mbps-Long-Range-AC1200-Dual-Band-5GHz-Wireless-USB-3-0-WiFi-Adapter-Antennas/323968481362)

Request: If you own or are aware of other adapters that use the mt7612u chipset, please let me know by posting in ```Issues```.

-----

Note: Indications are that all adapters below this line are "single-state"

-----

#### AC600 - USB 2 - 2.4 GHz and 5 GHz (WIFI 5)


##### ```chipset - Mediatek mt7610u - supported in-kernel since Linux kernel 4.19```
Note: As of 04-24-2021, Raspberry Pi OS, Debian stable and Kali Linux do not ship with the firmware for the mt7610u chipset. It is an oversite. It has been reported to Debian and has been fixed but the fix will not show up until the next Debian stable is released. In the meantime, users can download the firmware file called `mt7610u.bin` from...

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek
```
Create the needed directory: $ sudo mkdir /lib/firmware/mediatek
Copy the file to the new directory: $ sudo cp mt7610u.bin /lib/firmware/mediatek
Reboot: $ sudo reboot
```
--- Alfa AWUS036ACHM --

Rokland - $40 USD - [ALFA AWUS036ACHM 802.11ac Dual Band High Power Mediatek MT7610U WiFi USB Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036achm-802-11ac-dual-band-high-power-ac1200-mediatek-wifi-usb-adapter) [1] ID 0e8d:7610 MediaTek Inc. - "single-state"

Amazon - $50 USD - [Alfa AWUS036ACHM 802.11ac WiFi Range Boost USB Adapter](https://www.amazon.com/AWUS036ACHM-802-11ac-Range-Boost-Adapter/dp/B08SJBV1N3) ID 0e8d:7610 MediaTek Inc. - "single-state"

Varia - $36 EUR - [Alfa - AWUS036ACHM - 802.11ac WiFi Range Boost USB Adapter](https://www.varia-store.com/en/produkt/102561-awus036achm-802-11ac-wifi-range-boost-usb-adapter.html) ID 0e8d:7610 MediaTek Inc. - "single-state"

Note: The above 3 links are for the Alfa AWUS036ACHM adapter. It is a good product. It is mid-priced, well made and works well in managed mode, master mode and monitor mode. This is a single-state adapter meaning that usb-modeswitch is not required. WPA3 works. Supports interface combinations - `#{ IBSS } <= 1, #{ managed, AP, mesh point } <= 2, total <= 2, #channels <= 1, STA/AP BI must match` Device ID - `ID 0e8d:7610 MediaTek Inc. WiFi` Recommended.

--- Various links ---

ebay - $15 USD - [TOTOLINK A1000UA 11AC 600Mbps Dual Band Mini USB WiFi Network Adapter w/ SoftAP](https://www.ebay.com/itm/223121099969)

Amazon - $8 USD - [Cable Matters AC600 Dual-Band USB Wireless Adapter (Wireless AC Adapter, WiFi Adapter)](https://www.amazon.com/Cable-Matters-Dual-Band-Wireless-Adapter/dp/B00ZQ0C4KI)

ebay - $15 USD - [Mediatek MT7610U 11AC 600Mbps USB 2.0 Wireless Adapter Dual Band White](https://www.ebay.com/itm/363268018762)

SmartGuys - $20 USD - [Mediatek 11AC USB Wireless Adapter, MT7610U](https://smartguyscomputers.com/product/mediatek-11ac-usb-wireless-adapter-mt7610u)

ebay - $20 USD - [Panda Pau0a AC600 Dual Band Wireless USB Adapter](https://www.ebay.com/p/27020163733)

Amazon - $28 USD - [ASUS USB-AC51 AC600 Dual-Band Wifi Wireless Adapter](https://www.amazon.com/dp/B00HM0K61Y)

Amazon - $36 USD - [Asus Dualband Wirel. AC600 USB, USB-AC51](https://www.amazon.com/Asus-Dualband-Wirel-AC600-USB-AC51/dp/B00T3DK154)

Amazon - $30 USD - [ZyXEL NWD6505 IEEE 802.11ac - Wi-Fi Adapter](https://www.amazon.com/ZyXEL-NWD6505-IEEE-802-11ac-Computer/dp/B00D9F1SLI)

Amazon - $31 USD - [Linksys AE6000 Wireless Mini USB Adapter](https://www.amazon.com/Linksys-Wireless-Mini-Adapter-AE6000/dp/B00BWT1IFE)

hp - $57 USD - [LINKSYS AE6000 IEEE 802.11AC - WI-FI ADAPTER](https://www.hp.com/us-en/shop/pdp/linksys-ae6000-ieee-80211ac---wi-fi-adapter-for-desktop-computer-notebook)

Amazon - $13 - [Mini Dual Band - 2.4ghz 150M - 5ghz 11AC 433M USB Wifi Adapter](https://www.amazon.com/802-11b-Adapter-802-11AC-Chipset-Wireless/dp/B01LY57UBS)

-----

#### N600 - USB 2 - 2.4 GHz and 5 GHz (Dual Band) (WIFI 4)


##### ```chipset - Mediatek/Ralink rt5572 (Mediatek bought Ralink a few years ago)```
Amazon - $40 USD -[Panda Wireless PAU09 N600 Dual Band (2.4GHz and 5GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU09-Adapter-Antennas/dp/B01LY35HGO) - I have read many positive comments from Linux users about this adapter.

Amazon - $25 USD - [Panda N600 Dual Band (2.4GHz & 5.0GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-2-4GHz-300Mbps-Wireless-Adapter/dp/B00U2SIS0O)

ebay - $22 USD - [Kali Linux compatible dual band WiFi sniffer & Packet injection based on RT5572](https://www.ebay.com/itm/Kali-Linux-compatible-dual-band-WiFi-sniffer-Packet-injection-based-on-RT5572/273538484636?hash=item3fb02a099c:g:-1kAAOSwNe9cG~S-)

Note: The above adapter says "Kali Linux compatible" which seems to imply it only works with Kali but that is not the case. This adapter should work with any mainstream Linux distro that is currently supported by its maker. 

Amazon - $13 USD - [Socobeta RT5572 USB Dual-Band 5.8G/2.4G AC Wireless Network WiFi Adapter](https://www.amazon.com/Socobeta-Network-Dual-Band-Wireless-Adapter/dp/B08MKNH2PJ)

-----

### Single Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can save a lot of trouble as it will allow you to have a  temporary connection during installation of your Linux distribution. It can also provide temporary internet access in case you have problems with a wired connection or you need to install the driver for an adapter that requires an out-of-kernel driver. I have a couple of single band adapters. One I keep at home and the other goes on the road with my laptop. These adapters are handy.  

-----

#### N300 - USB 2 - 2.4 GHz (WIFI 4)


##### ```chipset - Mediatek/Ralink rt5372 (Mediatek bought Ralink a few years ago)```
[Panda Wireless PAU06 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU06-300Mbps-Adapter/dp/B00JDVRCI0) - I have read many positive comments from Linux users about this adapter.

[Panda Wireless PAU05 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-300Mbps-Wireless-USB-Adapter/dp/B00EQT0YK2)

[ASHATA Wireless USB Adapter RT5372 N300](https://www.amazon.com/ASHATA-Wireless-Network-Adapter-DWA-140/dp/B07X264THJ)

[Wendry Wireless USB Adapter, 2.4GHz, DWA-140, RT5372 N300](https://www.amazon.com/Wendry-Wireless-Network-Frequency-Ethernet/dp/B07Y2VKDNJ)

-----

#### N150 - USB 2 - 2.4 GHz (WIFI 4)

Note: Several of the below adapters say "Raspberry Pi" which seems to imply they only works with the Raspberry Pi OS but that is not the case. These adapters will work with any mainstream Linux distro that is currently supported by its maker. Another point to make is while N150 adapters are not the latest toy available, they are still very capable, very solid and will certainly allow users to watch youtube videos, listen to online music and support heavy web surfing without slowdown. Some are cheap enough to justify keeping one around as a backup if for no other reason. My wife's computer uses an adapter with a ar9271 chipset. It just works. In case you are wondering, she uses Linux Mint 20.


##### ```chipset -  Mediatek mt7601u```  Note: driver only supports managed and monitor modes.
Amazon - $7 USD - [EDUP USB WiFi Adapter for PC - High Gain 6dBi Antenna](https://www.amazon.com/gp/product/B0827LG8L2) - I have read many positive comments from Linux users about this adapter.

Amazon - $9 USD - [DM-Digital USB WiFi Dongle 2dBi MT7601](https://www.amazon.com/DM-Digital-USB-WiFi-Dongle-MediaTek/dp/B0783QRGFR) [1]

Amazon -$5 USD - [Zibo Mini USB Wifi Wireless Adapter, 150Mbps](https://www.amazon.com/Zibo-Wireless-Adapter-150Mbps-Supports/dp/B00RBBUQLE)

Amazon - $20 USD - [Electronic Accessories Mt7601U USB WiFi Dongle WiFi Stick Adapter 150Mbps Antenna](https://www.amazon.com/Mt7601U-Dongle-Adapter-150Mbps-Antenna/dp/B075PNBB8L)


##### ```chipset - Mediatek rt5370 (Mediatek bought Ralink a few years ago)```
[Panda Mid Range 150Mbps Wireless N USB Adapter w/ 2dBi Antenna](https://www.amazon.com/gp/product/B004AC0L4Y)

[CanaKit Raspberry Pi WiFi Wireless Adapter](https://www.amazon.com/dp/B00GFAN498)

[Panda Ultra WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG) [1]

[Raspberry Pi Pi 2 Pi 3 USB Wireless Adapter Mideatek RT5370N With 2 dBi Antenna 802.11 n g b USB 2.0](https://www.amazon.com/Connecting-Wireless-Adapter-150Mbps-Raspberry/dp/B073J3HXZH)

[WiFi for Raspberry Pi](https://www.amazon.com/dp/B00H95C0A2)

[USB WiFi Adapter Ralink RT5370](https://www.amazon.com/Adapter-Raspberry-OlinuXino-OpenSUSE-Injection/dp/B08B3B15CD)

[EASTECH Ralink RT5370 Raspberry PI WiFi Adapter](https://www.amazon.com/Ralink-RT5370-Raspberry-Adapter-Function/dp/B019XUDHFC)

[Wireless WiFi USB Dongle Stick Adapter RT5370 150Mbps](https://www.amazon.com/Wireless-Adapter-150Mbps-Set-Top-Raspberry/dp/B01KWQAQ00)


##### ```chipset - Atheros ar9271 [2]```
[ALFA AWUS036NHA Atheros AR9271 802.11n WIRELESS-N USB Wi-Fi adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036nha-802-11n-wireless-n-usb-wi-fi-adapter-2-watt) - I have read many positive comments from Linux users about this adapter.

[AR9271 802.11n 150Mbps Wireless USB WiFi Adapter](https://www.amazon.com/802-11n-150Mbps-Wireless-Adapter-Network/dp/B07FVRKCZJ)

[ALFA AWUS036NHA 802.11n Wireless-N Wi-Fi USB Adapter High Speed Atheros AR9271](https://www.ebay.com/itm/ALFA-AWUS036NHA-802-11n-Wireless-N-Wi-Fi-USB-Adapter-High-Speed-Atheros-AR9271/380458349886?epid=1600491254&hash=item589515b53e:g:zW8AAOSwnCFaQ9Oe)

[Quickbuying New Atheros AR9271 150Mbps Wireless USB LAN Adapter](https://www.amazon.com/Quickbuying-Atheros-150Mbps-Wireless-Adapter/dp/B07H3T9W8J)

[Alfa AWUS036NHA - Wireless B/G/N USB Adaptor](https://www.amazon.com/Alfa-AWUS036NHA-Wireless-USB-Adaptor/dp/B004Y6MIXS)

[WiFi Nation USB WiFi Antenna 802.11n, Speed: 150Mbps, Freq. 2.4GHz and 5dBi Antenna, chipset: Atheros AR9271](https://www.amazon.com/WiFi-Nation-Antenna-802-11n-Speed/dp/B08D7S3GL9)


##### ```chipset - Mediatek/Ralink rt3070 (Mediatek bought Ralink a few years ago)```
[Panda Mini WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Mini-150Mbps-Wireless-Adapter/dp/B003283M6Q)

[Deal4GO RT3070 802.11n 150Mbps Wireless USB WiFi Adapter for Kali Linux Ubuntu](https://www.amazon.com/Deal4GO-802-11n-150Mbps-Wireless-Archlinux/dp/B08QZDGWJC)

[INTELLINET IEEE 802.11b/g/n Wireless 150N High-Power USB Adapter](https://www.amazon.com/INTELLINET-802-11b-Wireless-High-Power-525152/dp/B005HF6H28)

[Deal4GO RT3070 802.11n 150Mbps Wireless USB WiFi Adapter WLAN w/ YP243433 Power Amplifier for Ralink RT3070L WiFi Module Kali Linux Ubuntu](https://www.amazon.com/Deal4GO-RT3070-Wireless-YP243433-Amplifier/dp/B086D72XR6)

[coolxan USB Rt3070 Chipset 802.11n 150m WiFi Wireless-n Adapter](https://www.amazon.com/Rt3070-Chipset-802-11n-Wireless-n-Adapter/dp/B00NAXX40C)

[ALFA AWUS036NEH Long Range WIRELESS 802.11b/g/n Wi-Fi USB Adapter](https://www.amazon.com/AWUS036NEH-Range-WIRELESS-802-11b-USBAdapter/dp/B0035OCVO6)


##### ```chipset - Mediatek/Ralink rt2870 (Mediatek bought Ralink a few years ago) [2]```

I can't find any new adapters with the rt2870 chipset for sale. My adapter with this chipset is many years old but still snaps to life and works very well when plugged in so if you see adapters, even used adapters with the rt2870 chipset, know that it is still supported in modern distros of Linux and likely will be supported for a long time. If you are wondering if this adapter is slow... it is an 11n adapter and I do not consider it to be slow. You can stream video, surf the net, and listen to online radio without buffering or slowdown (as long as you have good internet service.) I don't list chipsets and adapters here unless I am confident they will meet today's use cases for the WiFi bands that they support. 

-----
### Linux out-of-kernel drivers (Realtek) for Dual Band USB WiFi Adapters

Note: The list is not ranked in order by any specfic measure of performance. Performance and reliability varies. The best overall driver is the 8812au. It performs reasonably well in managed mode, master mode and monitor mode. The fastest driver in managed mode is the 88x2bu. My advice, if you need good performance in master mode or monitor mode, is sell your Realtek chipset based adapter and get one of the adapters based on in-kernel drivers as shown earlier in this document. None of these out-of-kernel drivers are fully Linux Wireless standards compliant.

Note: Out-of-kernel drivers require you to find, download, compile and install the driver source code. The below links provide a lot of information, including information about supported adapters. Nine total chipsets are supported with the following five drivers.

Note: None of the Realtek out-of-kernel drivers test good for WPA3 support. If you need WPA3 support, head back up to the list of adapters with in-kernel support. I have tested multiple adapters with `mt7612u` chipsets and WPA3 is working fine with Ubuntu 20.04 and later, Linux Mint 20.1 and the Raspberry PI OS.

Note:  None of the Realtek out-of-kernel drivers support interface combinations. If you need support for interface combinations, head back up to the list of adapters with in-kernel support. I have tested multiple adapters with `mt7612u` and `mt7610u` chipsets and multiple interface combinations are supported with the current Linux in-kernel drivers.

-----

Recent changes:

- 2012-04-28 - minor changes above and below to reflect the latest testing.

-----

##### chipsets - rtl8812bu [2] and rtl8822bu - AC1200 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

The rtl8812bu chipset may see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. This chipset tends to run cool, which is good, and Realtek currently provides updated out-of-kernel driver source code on a semi-regular basis. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

The Good:

- fast in managed (client) mode (for an AC1200 chipset)
- runs cool
- possible in-kernel driver support at some point
- readily available at low prices
- power saving works well

The Bad:

- WPA3 does not work
- no support for interface combinations
- the really bad quality of some adapters made with this chipset means you need to reseach before buying
- not a good choice for master mode or monitor mode (with the current out-of-kernel driver)

-----

##### chipsets - rtl8811cu [2], rtl8821cu and rtl8831au - AC600  - USB 2
[Linux Driver for USB WiFi Adapters that use the RTL8811CU, RTL8821CU and RTL8831AU Chipsets](https://github.com/morrownr/8821cu)

The rtl8811cu chipset may see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. This chipset tends to run cool, which is good, and Realtek currently provides updated out-of-kernel driver source code on a regular basis. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

The Good:

- fast enough for most users
- runs cool
- possible in-kernel driver support at some point
- readily available at low prices
- power saving works well

The Bad:

- WPA3 does not work
- no support for interface combinations
- the really bad quality of some adapters made with this chipset means you need to reseach before buying
- not a good choice for master mode or monitor mode (with the current out-of-kernel driver)
 
-----

##### chipset - rtl8812au [2] - AC1200 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8812AU Chipset](https://github.com/morrownr/8812au)

The rtl8812au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8812bu chipset for adapters in the AC1200 class. Not many rtl8812au adapters remain available on the market. The above driver is a really good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset.

The Good:

- best out-of-kernel driver of the 5 listed here, very solid
- master (AP) mode is outstanding
- monitor mode is reported to be pretty good, even on 5g
- power saving works well

The Bad:

- WPA3 does not work
- no support for interface combinations
- future Realtek support unknown
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8812bu

Recommendation: While this is currently the best supported of the Realtek chipsets, the chipset doesn't provide any significant advantages over the mt7612u chipset and the driver for the mt7612u chipset is far superior and is professionally maintained in the Linux kernel. Your long term happiness is probably best served by buying and adapter with a mt7612u chipset.

-----

##### chipsets - rtl8811au [2] and rtl8821au - AC600 - USB 2
[Linux Driver for USB WiFi Adapters that use the RTL8811AU and RTL8821AU Chipsets](https://github.com/morrownr/8821au)

The rtl8811au chipset, like the rtl8812au chipset, is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8811cu chipset for adapters in the AC600 class. Adapters that use the rtl8811au chipset are still available but availability is declining. The above driver is a decent quality driver but is somewhat dated and is hard to maintain much like the driver for the rtl8814au. The question is, how long will Realtek continue to release out-of-kernel source code for this chipset.

The Good:

- managed mode is reasonably good
- master (AP) mode is good
- power saving works well

The Bad:

- WPA3 does not work
- no support for interface combinations
- no mesh support
- future Realtek support unknown
- it has been over a year since the last source code release
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8811cu

Recommendation: Do not buy adapters based on this chipset. Better options are available. You will likely be happier in the long run with an adapter that uses the mt7610u chipset.

-----

##### chipset - rtl8814au [2] - AC1900 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

The rtl8814au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. Adapters based on this chipset can really push data at high speed and are still available but are relatively expensive. They need a pretty good amount of power so a powered USB 3 hub may be a good idea. This chipset builds a lot of heat so look for adapters that have plenty of vent holes and search reviews to see if users are reporting heat problems. The above driver is not very good but it is based on the latest source we have available. The source is from 2019. We need Realtek to release an updated, modernized version of the driver source code as the code for this driver is showing some age and is hard to maintain. Will Realtek release a new, improved version? I don't know.

The Good:

- fastest USB chipset available
- managed mode is reasonably good

The Bad:

- WPA3 does not work
- no DFS channels support
- no support for interface combinations
- no mesh support
- no AP/VLAN support
- no P2P-client support
- no P2P-GO support
- master (AP) mode can crash your system
- monitor mode support is bad
- future Realtek support unknown
- no new source code releases since 2019, and that 2019 release was not a good driver
- uses a lot of power so using a powered hub may be a good idea
- produces a lot of heat, adapter needs a lot of vent holes or space
- expensive

Recommendation: Do not buy adapters based on this chipset. You will be disappointed. Better options are available. You will likely be happier in the long run with an adapter that uses the mt7612u chipset or in the short run with an adapter that uses the rtl8812au chipset. The reason I say "short run" for the rtl8812au chipset is because we do not know if Realtek will release source code for the rtl8812au in the future.

-----

How to Modeswitch ( https://www.draisberghof.de/usb_modeswitch )

Note: this document was tested on a Raspberry Pi 4b with the current version
of the Raspberry Pi OS.

Note: To clarify, almost all recent distros such as Ubuntu 20.04 and later,
Linux Mint 20 and later and the current version Manjaro do not require you
to do anything. usb-modeswitch is installed and set up and works automatically.

Note: As of the date of this document, I am aware of 3 operating systems that
require the changes as outlined below:
```
- Raspberry Pi OS
- Kali Linux
- Debian stable
```
2021-04-20

TEROW_ROW02FD USB WiFi adapter

COMFAST CF-WU782AC USB WiFi adapter

"multi-state" adapters will initially show up as a CDROM or flash drive.
If you run Windows, there will an attempt to install a driver. In any OS
besides Windows, the adapter will continue to be seen as a CDROM or flash
drive and no driver will be installed. For the WiFi adapter to show up,
the adapter has to be told to switch state.

Most mainsteam distros of Linux include a utility call 'usb-modeswitch". It
will execute the switch for you if it has the information about your adapter
in its data files. If it is not installed or the data for your adapter is
not in its data files then:

```
Ensure usb-modeswitch is installed

$ sudo apt install usb-modeswitch usb-modeswitch-data


Execute usb-modeswitch in a terminal to see if it works

$ sudo usb_modeswitch -K -W -v 0e8d -p 2870


If successful, set it up to run automatically

edit the following file

$ sudo nano  /lib/udev/rules.d/40-usb_modeswitch.rules

below the following line

SUBSYSTEM!="usb", ACTION!="add",, GOTO="modeswitch_rules_end"

add two lines

# COMFAST CF-WU782AC WiFi Dongle, TEROW ROW02FD WiFi Dongle
ATTR{idVendor}=="0e8d", ATTR{idProduct}=="2870", RUN+="usb_modeswitch '/%k'"


create the file /usr/share/usb_modeswitch/0e8d:2870

$ sudo nano /usr/share/usb_modeswitch/0e8d:2870

put the following inside:

# COMFAST CF-WU782AC WiFi Dongle, TEROW ROW02FD WiFi Dongle
TargetVendor=0x0e8d
TargetProductList="7612"
StandardEject=1

save the file and reboot
```

-----
Adapter Reviews: 

2021-03-03

AC1200+ USB 3 WiFi Adapter Comparison
```
Adapter			Chipset			USB Capability
MaxPower		Device ID		Visible Antennas
iperf3 Test		Link Quality		Signal Level

Alfa AWUS036ACH         rtl8812au         	USB3
800mA			ID 0bda:8812		2
309 Mb/s		Link Quality=99/100  	Signal level=-43 dBm

Cudy WU1400             rtl8812bu               USB3
504mA                   ID 0bda:b812            1
291 Mb/s                Link Quality=84/100     Signal level=-51 dBm     

Alfa AWUS036ACM         mt7612u                 USB3
400mA                   ID 0e8d:7612            2
237 Mb/s                Link Quality=79/100     Signal level=-55 dBm

Generic (brown box)     rtl8812bu               USB3
504mA                   ID 0bda:b812            2      
216 Mb/s                Link Quality=70/100     Signal level=-61 dBm

Generic (brown box)     rtl8814au               USB3
864mA                   ID 0bda:8813            2
204 Mb/s                Link Quality=86/100     Signal level=-50 dBm
```

Test conditions:

Distance from adapters to AP was about 45 feet (2 walls).

iperf3 server is running on a Raspberry Pi 4b that is connected to the
network via CAT 6 ethernet cable.

Adapters were connected to a rear USB 3 port on a Dell Optiplex 9020
with an i7 processor running Linux Mint 20.1.

Utilities used include wavemon, iw and iperf3.

iperf3 test: $ iperf3 -c 192.168.1.40 -t 120

Analysis:

This is a limited test based on a user request. I'll plan on expanding
the test as time permits.

If I have to declare an overall winner from the tested adapters, it
would be this adapter:
```
Alfa AWUS036ACM
```
The reason for picking the above adapter is that it did a good job in
all categories. Some adapters may beat it in some categories but this
is the only adapter that performed well in all catagories. It was solid
in managed mode, master mode and monitor mode. The only tested adapter 
that came close is the Alfa AWUS036ACH (rtl8812au chipset) but it used
close to 800 mA when pushed hard which is about twice the amount of
current used by the Alfa AWUS036ACM (mt7612u chipset). This low current
usage by the Alfa AWUS036ACM is very good for use with Raspberry Pi 
hardware or any other use where low power useage and cool operating
temps are needed. The Alfa AWUS036ACM can be plugged directly into a 
RasPi 4b USB 3 port and there is plenty capacity left over for other
things. I have a USB 3 500gb SSD and a Alfa AWUS036ACM plugged into my
RasPi 4b and it is very stable. I couldn't do this with most other AC1200 
class adapters as they pull too much current. The RasPi 4b USB subsystem
is limited to 1200 mA.

Here are the categories.

-----

If price is important:
```
Cudy WU1400       (low price)
Alfa AWUS036ACM   (mid price)
Alfa AWUS036ACH   (very high price)
```
-----

If quality construction is important:
```
Alfa AWUS036ACM
Alfa AWUS036ACH
Cudy WU1400
```
-----

If a strong signal is important:
```
Alfa AWUS036ACH   (astoundingly good)
Cudy WU1400       (very good)
Alfa AWUS036ACM   (very good)
```
-----

If an in-kernel driver is important:
```
Alfa AWUS036ACM		(it is a very good driver)
```
-----

If master (AP) mode is important:
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
Cudy WU1400       (maybe)
```
-----

If having the the device driver support current Linux
Wireless standards is important:
```
Alfa AWUS036ACM
```
-----

If having a clear path to report driver problems is important:
```
Alfa AWUS036ACM
```
-----

Link to MT76 driver in the Linux kernel: (mt7663u, mt7612u and mt7610u chipsets)

https://github.com/torvalds/linux/tree/master/drivers/net/wireless/mediatek/mt76

-----

Link to RTW88 driver in the Linux kernel: (possible future 8812bu chipset support)

https://github.com/torvalds/linux/tree/master/drivers/net/wireless/realtek/rtw88

Note: This driver does not support usb adapters yet but there is hope.

-----

Link to RTL8812AU driver in the Linux kernel:

It does not exist and likely will never exist. My opinion is that we will never
see a fully Linux Wireless standards compliant driver for the rtl8812au chipset.
The same is true for the 8811au and 8814au chipsets.

-----

Hopefully this document is of help to Linux users that want or need USB WiFi
adapter support. I will look to expand and improve this document in the future.

-----

The mission of this site is to collect information and provide links regarding the purchase and use of USB WiFi adapters with Linux.

Any information and links you can provide are welcome. Submit the information and links by clicking on Issues...or if you are a Github user, submit a Pull Request.

Regards,

morrownr

[1] I have and use this adapter

[2] I have an adapter that uses this chipset
