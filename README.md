2022-03-27

-----
HOT! Need Your Help: We need to let Comfast and other adapter makers know what we think about multi-state adapters... Read #70

-----

Disclaimer: The authors and contributors to this site cannot be responsible for the results of your use of the information contained in or linked from this site. We attempt to provide accurate information but many factors that are beyond our control can contribute to less than expected results. You are responsible for ensuring the accuracy and applicability of any information you use to make a decision.

Foreword: There are many USB WiFi adapters that work without the need to install a driver in Linux. These adapters use drivers that are already in the Linux kernel. These drivers are maintained in the kernel without the need for user intervention, although, if you want to help with the code, you are welcome to do so. With adapters that use in-kernel drivers, simply plug the adapter in and it will work. Many people find that using adapters with in-kernel drivers is a better solution than using an adapter that requires drivers to be found (not easy to find the right driver), downloaded, compiled (confusing for those that are not developers), installed, fixed (not fun) and reinstalled.

-----
What's new section:

What is new? Some retailers are continuing to have inventory problems and prices of some adapters continue to climb. It appears that Mediatek is having a hard time keeping up with demand for the mt7612u chipset and that can be seen in both the increases in prices and out-of-stock situations for adapters based on this chipset. The increase in demand for adapters based on the mt7612u is not just coming from individual home users but also from corporate and government accounts. Linux is used in many locations and continues to increase in popularity and the mt7612u is the `go to` chipset for Linux users wanting the flexibity of USB WiFi adapters. On the other hand, we are seeing few availability problems with adapters based on the mt7610u chipset. In fact, I've seen a few price decreases. If an  AC600 adapter will meet your needs, maybe it is a good idea to take a look at adapters based on the mt7610u chipset. The ALFA AWUS036ACHM is based on the mt7610u and is still selling for the pre-pandemic price of $40 USD. Details in the mt7610u section later in this document.

What else is new? HOT! The 64 bit version of the Raspberry Pi OS was finally recently (21-01-28) released. That is the good news. The bad news is that the data file for `usbmodeswitch` is the old version. What this means is that many of the multi-state adapters shown later in this document will not automatically work. The driver is there but it cannot activate due to the adapter being stuck in CD-ROM or flash mode.  To correct this, click [here](https://github.com/morrownr/USB-WiFi/blob/main/How_to_Modeswitch.md). The 32 bit version works fine. Do not ask because I do not know. Edit: I am seeing numerous additional problems related to networking in the newly released 64 bit version of the Raspberry Pi OS. If you need a stable system, stay with the 32 bit version for now.

-----

## USB WiFi Adapter Information and Links for Linux

USB WiFi adapters provide flexibility as they are easily moved from one location to another and from one computer to another and can even be taken on the road. They come in models for USB 2 and USB 3. Some of the larger adapters work well for desktop use and the smaller adapters, including "nano" adapters, work well for laptops and travel. It is important that you pick an adapter to match the expected usage. If you are going to be traveling with the adapter, the adapters with long antennas may not not work well as the adapter may be broken. On the other hand, if you need an adapter for a desktop system that is on the other end of the house from your AP/Router, you probably need the better signal capability of the larger antennas. Researching the issue before buying is a good idea.

Linux enjoys very good in-kernel hardware support in many areas but in-kernel support is somewhat limited when it comes to USB WiFi adapters. The main reason for the limited support is that there are only 2 companies supplying chipsets for USB Wifi adapters - Mediatek and Realtek. Intel is not supplying USB capable chipsets and Atheros is not supplying modern USB capable chipsets. Of the two suppliers that do provide USB Wifi chipsets, Mediatek supports drivers for their chipsets the right way, in-kernel. Mediatek drivers are Linux Wireless standards compliant and are updated constantly without users having to worry about it. Realtek does not support their modern USB Wifi chipsets with in-kernel drivers. Realtek does make non-standards compliant Linux drivers but does not publically release them or take problem reports. A very limited number of vendors post Realtek USB WiFi drivers at very irregular intervals. These drivers are released in source code format and must be compiled to be used. The Realtek drivers do not keep up with the needed changes as new kernels are released. This job seems to rest with folks like myself in the community. Am I a fan of how the Realtek USB team supports the Linux community? No. What do I recommend? Buy adapters based on chipsets from the company that is doing it right - Mediatek. The biggest problem most Linux users have when looking to purchase a USB WiFi adapter is being able to reliably identify which adapters have in-kernel support and that is really the reason for this site. Spreading this information far and wide is key to having happy Linux users so please do spread this information.

This document attempts to identify currently available adapters that use in-kernel driver support. Links are provided to online products. Information regarding out-of-kernel drivers and their quality is also provided. The hope is that this information is of benefit to Linux users, experienced and new. Links to products from a wide variety of retailers are provided and we welcome you to send additional links that can be included. The chipsets are shown in each category and if you are able to find an adapter with the listed chipset, even if it is not an adapter that is specifically listed, it should work.

[Linux Wireless - Mediatek](https://wireless.wiki.kernel.org/en/users/drivers/mediatek) is a good place to get an idea of the various Mediatek wifi chipsets that are supported in the Linux kernel. If you want to look in the kernel to see the drivers, [look here](https://github.com/torvalds/linux/tree/master/drivers/net/wireless/mediatek). One of the biggest advantages of using adapters with in-kernel drivers is that any of us can report [bugs](https://wireless.wiki.kernel.org/en/users/documentation/reporting_bugs) and submit fixes. There is no way that I am aware of to report bugs to Realtek.

Warning: It is common for online retailers to post "Linux support." It is best to ignore "Linux support" in online ads as this statement is often misleading at best and false at worst. Most inexperienced users do not understand that the Linux kernel is under constant development which makes it necessary for drivers to be regularly updated in order to work on newer kernels. Out-of-kernel drivers sitting on a CD or on an adapter seller's web site do not get regular updates. Rule of thumb: Never attempt to install a Linux driver from a CD. Only consider downloading a Linux driver from an adapter seller's website if you confirm it supports the kernel you are using first. The out-of-kernel drivers on that CD or seller's webisite will likely be old and will likely do nothing more than make a mess of your system. Remember that `sudo` is a weapon of mass destruction if used without knowing what you are doing. Another rule of thumb: Don't take hardware advice from Windows and MAC users. All major Linux distributions have active forums with users ready to give advice. Don't take advice from a single user but seek advice from several users and always ask if the adapter uses in-kernel drivers.

Note: Some USB WiFi adapters have proprietary Windows drivers onboard. When plugged in, they act like a flash drive or CDROM and on Windows will attempt to start installing the Windows driver. That won't work on Linux or MAC or any other non-Windows OS so the adapter sits there in flash drive or CDROM mode. The problem is that the state of the adapter has to be changed for the adapter to show up as the device that you expect, in this case, a WiFi adapter. Most modern Linux distributions ship with a utility called "usb-modeswitch" that will handle this issue for you if it has the correct information for your adapter. It is a good utility but if you buy adapters that are "multi-state," that is one more potential headache you may have to deal with when something goes wrong. Often you can indentify adapters that are "multi-state" as they are advertised as "free driver" or "free installation driver." If you are looking to buy a USB WiFi adapter for use on Linux, MAC OS, NIX or anything besides Windows, it is a good idea to give preference to single-state adapters.

Note: I will not list any products made by TP-Link and D-Link. Both companies regularly change chipsets while keeping the same model number on their products. This makes it very difficult for Linux users to buy a product with a specific chipset with any degree of certainty. This also makes it difficult for me to post links and recommendations so I will not do so but that is okay because there are many good adapters available. TP-Link and D-Link's Linux support is very poor as their product support sites generally only contain very old Linux drivers that won't work with modern distros... if they post any drivers at all and neither company does a good job of supplying adapters that use in-kernel drivers. We know that Linux cannot be properly supported in the manner that both companies use. This is sad because both companies have made a lot of money from Linux by using it inside many of their products, yet they do not return the support. My recommendation is to avoid TP-Link and D-Link products.

Note: Adapters made by two companies need to be highlighted. Every single USB adapter that Panda makes is supported by Linux in-kernel drivers. The quality and reliability of most [Panda](http://www.pandawireless.com/) and almost all [Alfa](https://www.alfa.com.tw/) adapters is good... really good. Not all Alfa adapters use in-kernel drivers. The Alfa adapters that do use in-kernel drivers are listed below. Products by both companies are widely available.

WPA-3 SAE support: 2120-09-15 - My testing over the last few months has shown very positive results for WPA3 as far as in-kernel drivers are concerned. I have tested adapters ranging from N150 to AC1300. It appears that all of the adapters listed here that use Mediatek/Ralink and Atheros chipsets and in-kernel drivers are working well regarding WPA-3. Keep in mind that your Linux distro must support WPA-3 for WPA-3 to work. Based on upstream work and work on core distros, I expect that we will see WPA3 working well on the newest releases of almost all popular Linux distros by mid-2022. Many distros already work well.

USB extension cables with cradles can be very useful with USB WiFi adapters as they will allow you to position the adapter for best performance. Cables for USB2 and USB3 are available. The following cables are shown as  examples:

[StarTech.com 5ft USB 2.0 Extension Cable](https://www.amazon.com/5ft-Desktop-USB-Extension-Cable/dp/B001K9BFB8)

[Cablecc USB 3.0 Type-A Male to Female Extension Dock Station Docking Cable](https://www.amazon.com/Cablecc-Female-Extension-Station-Docking/dp/B07SH4RZ6S)

[WiFi Adapter Extension Cable with Pedestal](https://smile.amazon.com/gp/product/B08R2Y53QK?ref=em_1p_0_im&ref_=pe_3681270_598503160)

Note: Some adapters won't work with some extension cables and cradles. It is best to buy from retailers that will let you return their products as it seems the only way to know is trial and error.

Important: Price and availability of listed adapters is subject to change. Updating the list of adapters does take a considerable amount of time. I try to complete a review of the links at least once per month. This site has increased in popularity to the point that readers of this site may cause inventory problems for some sellers at times so you may need to wait for inventory to be refreshed. To help with this problem, I have listed multiple links from multiple sellers for some products. If you see any problems, please post in `Issues.`

Market Conditions: 2022-03-27 - Good adapters are available. The market seems to be stablizing but prices for some products are still higher than we would like to see. The global shortage of chips caused by fab plants being shut down for periods during 2020/2021 and the inadequate investment in new fab plants for many years has led to tight markets that have caused high and rising prices for some products and shortages of some products. This problem has recently been compounded by international shipping problems and continued outbreaks of COVID-19. This may continue for some time...possibly into 2023. If you are on a budget, you might want to consider "used" adapters as they are available.

The following link is simply a short list that might be handy to save on your computer for referrence. For much more detailed information, reviews and many additional links to additional adapters, continue on down the page.

[The Short List - Superstar USB WiFi Adapters for Linux](https://github.com/morrownr/USB-WiFi/blob/main/The_Short_List.md)

-----

### Dual Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers

-----

#### AX1800 - USB3 (WiFi 6)

-----

##### ```chipset - Mediatek mt7921u```

Status: 2022-03-15 - The mt7921u driver is going into the Linux kernel currently. No USB WiFi adapters are available yet. Available information appears to indicate that USB WiFi adapters based on the mt7921u will become available at some point during the second half of 2022. More to come...

-----

#### AC1200 / AC1300 - USB 3 - 2.4 GHz and 5 GHz (WIFI 5)

-----

##### ```chipset - Mediatek mt7612u - supported in-kernel since Linux kernel 4.19 (2018)``` - [mt7612u info](https://github.com/morrownr/7612u)
```
>=====>  ALFA AWUS036ACM  <=====<
```
Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/127750949-809364a6-65ed-4c7c-9abe-4a77cb73848e.png)

Rokland - 43 USD - [ALFA AWUS036ACM 802.11ac Dual Band USB WiFi Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036acm-802-11ac-dual-band-2-4-5-ghz-wifi-usb-adapter) - Info: free shipping and no tax outside of Florida. Ships to Canada and US.

ebay - 43 USD - [Alfa AWUS036ACM 802.11ac 867 Mbps Long Range WiFi USB Adapter](https://www.ebay.com/itm/Alfa-AWUS036ACM-802-11ac-867-Mbps-Long-Range-WiFi-USB-Adapter-DUAL-BAND-Mediatek/112773755774) - Ships Worldwide from US.

Varia - 42 EUR - Germany - [AWUS036ACM - 802.11ac Dualband-WLAN-USB-Adapter 2,4/5 GHz](https://www.varia-store.com/de/produkt/265294-awus036acm-802-11ac-mimo-dualband-wlan-usb-adapter-mit-2-4-5-ghz.html)

Amazon - 43 USD - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD) [1]

TUNG NETWORK TRADING - 220 RM - Malaysia - [Alfa AWUS036ACM 802.11ac Dual Band 2.4/5 GHz WiFi USB Adapter](https://www.alfa.net.my/webshaper/store/viewProd.asp?pkProductItem=70)

[ALFA AWUS036ACM Technical information](https://github.com/morrownr/USB-WiFi/blob/main/iw_list/ALFA_AWUS036ACM)

[ALFA Network Linux support for MT7612U based products](https://docs.alfa.com.tw/Support/Linux/MT7612U/)

Review by Nick - The Alfa AWUS036ACM is an excellent product. It is mid-priced, well made and works well in managed mode, master mode and monitor mode. It is a very solid, stable performer in 5 GHz AP mode. It supports 80 MHz channel width in AP mode and can sustain 400+ Mb/s as measured by iperf3. It runs cool and uses a maximum of only about 380 mA power when under heavy load. I use one in the wifi router/access point that I built. Works so well with the Raspberry Pi 4B, 3B+ and 3B, it is almost like it was designed specifically for that hardware. You really need to use it with a Raspberry Pi 4b so as to get the full througput capability. It works well with desktop systems (an extension cable is included in the packages most retailers of this product sell). It also works well with laptop systems. This adapter is a high quality product with good range and is plug and play in all of the modern distros of Linux. Highly recommended.

```
>=====>  TEROW ROW02CD and TEROW ROW02FD  <=====<
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/127751374-7a814003-6ff5-4da6-8534-bdc61ea5f249.png)

2022-03-27 - The link below is out of stock currently. You may be able to search and locate a TEROW ROW02CD.

Amazon - $16 USD - [TEROW ROW02CD AC1200 USB 3 WiFi Adapter 5G/2.4G 802.11 AC](https://www.amazon.com/gp/product/B086L3D3NB) [1]

Warning: TEROW sells a TEROW ROW12CD that is reported to be based on a rtl8812bu chipset. That is not what you want.

Review by Nick - The TEROW ROW02CD and TEROW ROW02FD work very well with the Raspberry Pi 4B, 3B+ and 3B. I have tested both with various desktop and laptop systems. The TEROW ROW02CD is a single state adapter and the TEROW ROW02FD is a multi-state adapter. You should give perferrence to single state adapters. The cost of these adapters is very low. The performance and quality of the materials used and capabilities of these adapters is not quite as good as the Alfa AWUS036ACM but that is to be expected since the Alfa AWUS036ACM is a more expensive, premium quality adapter. My experience is that these adapters do provide good stable performance and should meet the needs of most Linux users. In fact, during my testing, a TEROW ROW02FD outperformed in link quality and signal level vs. a similar adapter based on a rtl8812bu chipset when plugged into the same USB3 port and connected to the same wifi router.

Additional information about the TEROW ROW02FD (the multi-state version) - 2022-03-27 - The Raspberry Pi OS 64 bit release date 2022-01-28 ships with an old version of the data file for usb_modeswitch which will make it look like you need to install a driver. That is not the problem. For more information, see [How to Modeswitch](https://github.com/morrownr/USB-WiFi/blob/main/How_to_Modeswitch.md). To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the adapter will "just work." 
```
>=====>  COMFAST CF-WU782AC  <=====<
```

![image](https://user-images.githubusercontent.com/69053122/127756396-a5e425c7-0aa0-4593-a4d1-32ef442f58b3.png)

Note: [This is a multi-state adapter](https://github.com/morrownr/USB-WiFi/blob/main/How_to_Modeswitch.md).

AliExpress - $20 USD - [Comfast USB 3.0 Wireless Wifi Adapter Dual Band 2.4+5 GHz 150 -1300 Mbps 802.11AC 802.11 a/b/n/g/ac with 2*6dbi Antennas](https://www.aliexpress.com/item/32902591576.html)

Comfast - $28 USD - [COMFAST CF-WU782AC 5.8GHz USB 3.0 WiFi 1300Mbps 802.11ac Long Distance Adapter](https://comfastwifi.us/comfast-cf-wu782ac-5.8ghz-dual-antenna-usb3-wifi-adapter-1300m?search=CF-WU782AC)

Walmart - $24 - $32 USD - [COMFAST CF-WU782AC](https://www.walmart.com/search/?query=CF-WU782AC)

Review by soyersoyer - The COMFAST CF-WU782AC works well with my RasPi4b (and hostapd). I had to use the disable_usb_sg=1 parameter. I like this setup because it can route near gigabit speeds. My mobile devices have 300-500mbit/s download speed too, it has guest wifi, and I can easily switch to a newer wifi adapter later. The rpi runs kodi, a shairport server and a bluetooth sound receiver server too. I bought the wifi adapter from AliExpress.

Additional information about the COMFAST CF-WU782AC - 2022-03-27 - The Raspberry Pi OS 64 bit release date 2022-01-28 ships with an old version of the data file for usb_modeswitch which will make it look like you need to install a driver. That is not the problem. For more information, see [How to Modeswitch](https://github.com/morrownr/USB-WiFi/blob/main/How_to_Modeswitch.md). To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the adapter will "just work." 
```
>=====>  COMFAST CF-WU785AC  <=====<
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/128245876-c6944254-cf57-4134-92bb-6dd0d67d16bd.png)

Note: [This is a multi-state adapter](https://github.com/morrownr/USB-WiFi/blob/main/How_to_Modeswitch.md).

AliExpress - $22 USD - [Comfast 1300Mbps WI-FI Receiver 4*6dBi Dual Band Antenna Driver-Free Long Range Network Card 2.4&5GHz Desktop Adapter CF-WU785AC](https://www.aliexpress.com/item/1005002533185743.html)

Walmart - [Walmart has many sellers of this adapter](https://www.walmart.com/search?q=CF-WU785AC)

Review by Nick - Early testing is showing very good results. 

Managed (client) mode iperf3 results:
```
Bitrate         Retr
385 Mbits/sec    0             sender
385 Mbits/sec                  receiver
```
Note: The distance from adapter to access point was about 20 feet through 2 walls. I was using a clean DFS channel (104) and set iperf3 to run for 2 minutes so as to see if there were any abnormalities that would show up. No problems noted. This adapter can sustain high transfer rates and uses only about 380 mA during sustained high transfer rates. I have been using the adapter as my daily driver on my main workstattion for about 2 months now. I have not noticed any drops at all. It seems to be a very solid adapter and has pretty good range. Range is not what you see from an adapter like the ALFA AWUS036ACHM (further down) but the ALFA AWUS036ACHM is really hard to beat for range. Overall, this adapter is solid and comes with a faily low price tag. I'll test master and monitor modes as I have time but, quite frankly, I expect both to work as I have yet to test an adapter with a mt7612u chipset that has shown anything but rock solid, by the book performance. More information about the mt7612u chipset can be found [here](https://github.com/morrownr/7612u/blob/main/README.md). If you have questions, please post in Discussions or Issues.

Additional information about the COMFAST CF-WU785AC - 2022-03-27 - The Raspberry Pi OS 64 bit release date 2022-01-28 ships with an old version of the data file for usb_modeswitch which will make it look like you need to install a driver. That is not the problem. For more information, see [How to Modeswitch](https://github.com/morrownr/USB-WiFi/blob/main/How_to_Modeswitch.md). To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the adapter will "just work." 

```
>=====>  Netgear A6210  <=====<
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/127751480-4c34f5d7-3e7e-47ad-baab-aa5bad62c6bb.png)

ebay - $23 USD - [NETGEAR AC1200 USB 3.0 Wi-Fi Adapter - A6210-10000S](https://www.ebay.com/p/18021987463)

Walmart - $36 USD - [NETGEAR AC1200 Dual Band Wifi USB Adapter (A6210-100PAS)](https://www.walmart.com/ip/NETGEAR-AC1200-Dual-Band-Wifi-USB-Adapter-A6210-100PAS/40164604)

Amazon - $32-$74 USD - [NETGEAR AC1200 Wi-Fi USB Adapter High Gain Dual Band USB 3.0 (A6210)](https://www.amazon.com/NETGEAR-AC1200-Wi-Fi-Adapter-A6210-100PAS/dp/B00MRVJY1G)

Best Buy - $55 USD - [NETGEAR - AC1200 Dual-Band WiFi USB 3.0 Adapter - Black](https://www.bestbuy.com/site/netgear-ac1200-dual-band-wifi-usb-3-0-adapter-black/8860004.p?skuId=8860004)

Review by Nick - The Netgear A6210 is a good product. I enjoy using it. It is mid-priced and well made. It is an adapter that is designed to be portable and, as such, has a shorter range than adapters with larger antennas. It comes with a good quality USB3 extension cable plus cradle. It is a stable performer. I have noted that it runs a little warm but not so warm that it should cause problems with periodic use. Users looking for a portable AC1200 adapter that uses an in-kernel driver and has good performance over short to medium distances should be happy with this adapter. Note: Due to the somewhat limited range of this adapter, I do not recommend it for use in AP mode unless your requirement is only for same room connections. I also do not recommend this adapter for security analysis/pen testing for the same reason.

To be clear: This adapter can provide good throughput. Here is a sample from iperf3:

```
Bitrate
  366 Mbits/sec                  sender
  365 Mbits/sec                  receiver

```

This test was conducted in client mode at a distance of about 5 meters with 2 walls between the adapter and wifi router. The test was on 5 GHz on a clean DFS channel. This test shows that this adapter can certainly provide AC1200 performance and it is a good adapter to take on the road. It does not have long range so use as an AP should be limited to same room or short distance and monitor mode performance is not going to let you reach out long distances. It appears the twpower is fixed on this adapter at 18 dBm. I am posting this additional paragraph because a user expressed some displeasure at not being able to get this adapter to do what he wanted. My suggestion is that anyone that is not sure of what you need, go to `disccusions` or `issues` and ask.

```
>=====>  ANDDEAR - MTK7612U004  <=====<
```
![76-new](https://user-images.githubusercontent.com/69053122/132886023-58a44509-1d65-4de7-96fe-803064631301.jpg)

AliExpress - $20 USD - [ANDDEAR - MTK7612U004](https://www.aliexpress.com/item/4000048659616.html)

AliExpress - [AliExpress has many links to this adapter](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20210916082118&origin=y&SearchText=New+arrival+Black+MT7612U)

Review: [Interesting read from a group that changed over to this adapter](https://wlan-pi.github.io/wlanpi-documentation/admin/cf912_issues/)
```

>=====>  COMFAST CF-7500AC-V2  <=====<  (This adapter looks like a UFO!)
```

![image](https://user-images.githubusercontent.com/69053122/146787306-a29696b9-f3b3-41ac-97e2-6caaafa9ec21.png)

Note: [This is a multi-state adapter](https://github.com/morrownr/USB-WiFi/blob/main/How_to_Modeswitch.md).

Note: There is a V1 (COMFAST CF-7500AC) that is based on a Realtek chipset.
You want the more modern V2 model that is based on the mt7612u chipset.

AliExpress - $23 USD - [Comfast USB3.0 Wireless Network Wifi Card 1300Mbps Free Driver Dual Band 6dbi Antennas High Power Wifi Adapter CF-7500AC-V2](https://www.aliexpress.com/item/1005001391392407.html)

AliExpress - $23 USD - [Gigabit Wireless Wifi Adapter 2*6dbi Antenna 1300Mbps Dual Band 5Ghz Adapter 802.11ac MT7612U Dongle USB ](https://www.aliexpress.com/item/32975105005.html)

Additional information about the COMFAST CF-WU7500AC-V2 - 2022-03-27 - The Raspberry Pi OS 64 bit release date 2022-01-28 ships with an old version of the data file for usb_modeswitch which will make it look like you need to install a driver. That is not the problem. For more information, see [How to Modeswitch](https://github.com/morrownr/USB-WiFi/blob/main/How_to_Modeswitch.md). To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the adapter will "just work." 

```
>=====>  Walmart  <=====<
```

Important: The following link to Walmart will show various adapters that supposedly are based on the mt7612u or mt7612un chipsets. My opinion is that most of the ads that say the adapter uses a mt7612u chipset are correct but I've seen at least one ad (the ones with a single physical antenna are suspect) where I do not think that is the case, however, Walmart's return policy is legendary. Walmart will find a way to make you happy if you are not happy so there is a reduced risk in dealing with Walmart in this regard.

Walmart - [Walmart has many links to adapters based on the mt7612u chipset](https://www.walmart.com/search/?query=MT7612U)

2021-02-17 - As of this date, the one I would order is shown below. Why? It shows that it ships with a CD which may mean that it is a single-state adapter.

[Lomubue M-1200M Wireless Network Card](https://www.walmart.com/ip/Lomubue-M-1200M-Wireless-Network-Card-High-speed-Anti-interference-Driver-free-USB3-0-MT7612U-Dual-Band-WiFi-Transceiver-for-Router/731709450?athbdg=L1400)

-----

#### AC580 / AC600 - USB 2 - 2.4 GHz and 5 GHz (WIFI 5)

-----

##### ```chipset - Mediatek mt7610u - supported in-kernel since Linux kernel 4.19 (2018)```

Update: 08-25-21 - I installed current downloads of the Raspberry Pi OS and Kali Linux yesterday. Both now include the firmware for the mt7610u chipset. I am going to leave the below guidance for some time as there may be other Debian based distros that are not updated yet and this is a tricky issue because many users will think they need to install a driver... but the driver is there. It was the firmware that was missing.

Update: 08-14-21 - Debian 11 was released. As downstream distros rebase on this new release, this problem will go away.

Note: 04-24-2021 - Raspberry Pi OS and Kali Linux do not ship with the firmware for the mt7610u chipset. It is an oversite. It has been reported to Debian and has been fixed but the fix will not show up until the next Debian stable is released (expected 14 August 2021). In the meantime, users can download and install the firmware file called `mt7610u.bin`

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

```
=====> ALFA AWUS036ACHM <=====
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/129494292-e3e363ed-8119-4ab5-97cb-13018710a289.png)

Note: This adapter looks like a basic everday wifi adapter but it is not! I have tested many adapters and this adapter has the longest range of any modern dual band adapter that I have tested. If you need long range or an adapter that can run 24/7/365 and never miss a beat, this adapter is worth a look. Don't buy it for speed as it is a AC600 adapter, but if looking for range, great AP mode support, great monitor mode support and reliability, take a look.

Rokland - $40 USD - [ALFA AWUS036ACHM 802.11ac Dual Band High Power Mediatek MT7610U WiFi USB Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036achm-802-11ac-dual-band-high-power-ac1200-mediatek-wifi-usb-adapter) [1]

Varia - 44 EUR - Germany - [AWUS036ACHM - 802.11ac WiFi USB-Adapter](https://www.varia-store.com/de/produkt/265368-awus036achm-802-11ac-wifi-range-boost-usb-adapter.html)

ebay - $40 USD - [Alfa AWUS036ACHM 802.11ac dual band High Power Wi-Fi USB Adapter +RP-SMA antenna](https://www.ebay.com/itm/383907328953?epid=22045834288&hash=item5962a8f3b9:g:JiEAAOSwbatgBI-l)

TUNG NETWORK TRADING - 210 RM - Malaysia - [Alfa Network AWUS036ACHM 802.11ac WiFi USB Adapter](https://www.alfa.net.my/webshaper/store/viewProd.asp?pkProductItem=83)

Amazon - $45 USD - [Alfa AWUS036ACHM 802.11ac WiFi Range Boost USB Adapter](https://www.amazon.com/AWUS036ACHM-802-11ac-Range-Boost-Adapter/dp/B08SJBV1N3)

[ALFA AWUS036ACHM Technical information](https://github.com/morrownr/USB-WiFi/blob/main/iw_list/ALFA_AWUS036ACHM)

[ALFA Network Linux support for MT7610U based products](https://docs.alfa.com.tw/Support/Linux/MT7610U/)

Review by Nick - The Alfa AWUS036ACHM is a good product. It is mid-priced, well made, runs cool, has EXCEPTIONAL range and works well in managed mode, master mode and monitor mode. I have recently been testing master (AP) mode: This adapter is exceptional in 2.4 GHz AP mode and good in 5 GHZ AP mode. The range in both bands exceeds the wifi router that I tested it against and I consider that wifi router to have good range. One thing to consider regarding 5 GHz AP mode is that this is an AC600 device so maximum transfer rate is limited to 433 Mb/s. That is fast enough for most use cases and will be for a long time but it is not as fast as you can get from an AC1200 adapter. This adapter shows good link quality and signal level even in difficult situations where other adapters would drop the connection. My testing shows that this adapter has the longest range of any current dual band consumer grade adapter that Alfa sells and Alfa is known for their long range products. My opinion is that this adapter is the single best adapter available for use with Kali Linux or other distros used for pen testing and security analysis. Compared to the Alfa AWUS036ACH, the Alfa AWUS036ACHM has better range, costs less and is supported with in-kernel drivers making it the better choice for Linux users. It comes with the required USB2 cable and a clip that allows you to mount the adapter in various locations. Overall, the Alfa AWUS036ACHM is a solid performer. Highly recommended.
```
=====> Linksys AE6000 <=====
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/130810068-149bfebd-f93d-4bf3-af84-9a568806d93d.png)

Amazon - $25 USD - [Linksys AE6000 Wireless Mini USB Adapter](https://www.amazon.com/Linksys-Wireless-Mini-Adapter-AE6000/dp/B00BWT1IFE)

Walmart - $32 USD - [Linksys AE6000 Wireless-AC Mini USB Adapter](https://www.walmart.com/ip/Linksys-AE6000-Wireless-AC-Mini-USB-Adapter/24032271)

Amazon - $37 USD - [Linksys AE6000 Dual-Band Wireless Mini USB Adapter](https://www.amazon.com/Linksys-AE6000-Dual-Band-Wireless-Adapter/dp/B00BFW8KIG)

hp - $60 USD - [LINKSYS AE6000 IEEE 802.11AC - WI-FI ADAPTER](https://www.hp.com/us-en/shop/pdp/linksys-ae6000-ieee-80211ac---wi-fi-adapter-for-desktop-computer-notebook)

Review by Nick - The Linksys AE6000 is a good product. It has better range than most other small adapters that I have used. I am not saying that it is a long range adapter, just that it does pretty good for being a very small adapter. And it is a small adapter. The picture may make the adapter look larger than it is. It is not much bigger than a nano size adapter. Overall, it is a solid performer. Recommended.

--- Links to additional adapters that are based on the mt7610u chipset ---

AliExpress - $12 USD - [ANDDEAR - MT761003](https://www.aliexpress.com/item/4000079918154.html)

Walmart - $19 USD - [USB 5Ghz Wireless AC600M Dual Band 802.11ac Wifi Adapter Wi-fi Network](https://www.walmart.com/ip/USB-5Ghz-Wireless-AC600M-Dual-Band-802-11ac-Wifi-Adapter-Wi-fi-Network/112794071)

AliExpress - $14 USD - [COMFAST CF-923AC](https://www.aliexpress.com/i/32792689450.html)

ebay - $10 USD - [TOTOLINK A1000UA 11AC 600Mbps Dual Band Mini USB WiFi Network Adapter w/ SoftAP](https://www.ebay.com/itm/223121099969)

ebay - $20 USD - [ZyXEL Dual-Band Wireless AC600 USB Adapter, NWD6505](https://www.ebay.com/itm/293268959565)

Amazon - $32 USD - [ZyXEL NWD6505 IEEE 802.11ac - Wi-Fi Adapter](https://www.amazon.com/ZyXEL-NWD6505-IEEE-802-11ac-Computer/dp/B00D9F1SLI)

ebay - $15 USD - [Mediatek MT7610U 11AC 600Mbps USB 2.0 Wireless Adapter Dual Band White](https://www.ebay.com/itm/363268018762)

SmartGuys - $20 USD - [Mediatek 11AC USB Wireless Adapter, MT7610U](https://smartguyscomputers.com/product/mediatek-11ac-usb-wireless-adapter-mt7610u)

Amazon - $28 USD - [ASUS USB-AC51 AC600 Dual-Band Wifi Wireless Adapter](https://www.amazon.com/dp/B00HM0K61Y)

Amazon - $44 USD - [Asus Dualband Wirel. AC600 USB, USB-AC51](https://www.amazon.com/Asus-Dualband-Wirel-AC600-USB-AC51/dp/B00T3DK154)

ebay - $20 USD - [Panda Pau0a AC600 Dual Band Wireless USB Adapter](https://www.ebay.com/p/27020163733)

-----

#### N600 - USB 2 - 2.4 GHz and 5 GHz (Dual Band) (WIFI 4)
-----
##### ```chipset - Mediatek/Ralink rt5572 (Mediatek bought Ralink a few years ago)```

Amazon - $40 USD - [Panda Wireless PAU09 N600 Dual Band (2.4GHz and 5GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU09-Adapter-Antennas/dp/B01LY35HGO) - I have read many positive comments from Linux users about this adapter.

Amazon - $12 USD - [753 Mini USB WiFi Adapter,Dual Band 2.4G/5G](https://www.amazon.com/gp/product/B095KHCS6N)

Amazon - $13 USD - [Deal4GO RT5572 802.11n 300Mbps Dual Band USB WiFi Adapter - Ralink RT5572 - Kali Linux Raspberry Pi IPTV MAG322/324](https://www.amazon.com/Deal4GO-RT5572-802-11n-Wireless-Raspberry/dp/B08RDS32T3)

AliExpress - $14-$17 USD - [RT5572 Chipset Dual Frequency 2.4G/5G 300M Wireless Network Card Desktop Notebook Receiver Transmitter For Kali_Linux](https://www.aliexpress.com/item/1005002433670632.html?spm=a2g0o.productlist.0.0.65ac26cdQal3Ak&algo_pvid=74f67b04-7a18-4b6e-a0b7-4930948d0cff&algo_exp_id=74f67b04-7a18-4b6e-a0b7-4930948d0cff-1)

Amazon - $25 USD - [Panda N600 Dual Band (2.4GHz & 5.0GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-2-4GHz-300Mbps-Wireless-Adapter/dp/B00U2SIS0O)

ebay - $22 USD - [Kali Linux compatible dual band WiFi sniffer & Packet injection based on RT5572](https://www.ebay.com/itm/Kali-Linux-compatible-dual-band-WiFi-sniffer-Packet-injection-based-on-RT5572/273538484636?hash=item3fb02a099c:g:-1kAAOSwNe9cG~S-)

Amazon - $13 USD - [Socobeta RT5572 USB Dual-Band 5.8G/2.4G AC Wireless Network WiFi Adapter](https://www.amazon.com/Socobeta-Network-Dual-Band-Wireless-Adapter/dp/B08MKNH2PJ)

Walmart - [Walmart has many links to adapters based on the rt5572 chipset](https://www.walmart.com/search/?query=rt5572)

##### ```chipset - Mediatek/Ralink rt3572 (Mediatek bought Ralink a few years ago)```

AliExpress - $14 USD - [CHANEVE RT3572 Dual band 300Mbps Wireless Lan Adapter 5.8Ghz USB Wi-Fi Adapter Ralink RT3572 Dongle For Kali Linux and Samsung TV](https://www.aliexpress.com/item/4000979870302.html)

AliExpress - $14 USD - [WTXUP RT3572 600Mbps 802.11a/b/g/n Wireless USB WiFi Adapter + 2x 5dBi External WiFi Antenna for SamSung TV Windows 7/8/10
](https://www.aliexpress.com/item/32814137704.html)

AliExpress - [AliExpress has many links to adapters based on the rt3572 chipset](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20210821143225&origin=y&SearchText=rt3572)

-----

### Single Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers

-----

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can be very handy.

-----

#### N300 - USB 2 - 2.4 GHz (WIFI 4)

-----

##### ```chipset - Mediatek/Ralink rt5372 (Mediatek bought Ralink a few years ago)```

![image](https://user-images.githubusercontent.com/69053122/146690261-6117d58b-3c57-402c-9ac8-a3406ed80444.png)

Amazon - $20 USD - [Panda Wireless PAU06 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU06-300Mbps-Adapter/dp/B00JDVRCI0) - I have read many positive comments from Linux users about this adapter.

Amazon - $20 USD - [Panda Wireless PAU05 300Mbps Wireless N USB Adapter](https://www.amazon.com/Panda-300Mbps-Wireless-USB-Adapter/dp/B00EQT0YK2)

Amazon - $10 USD - [ASHATA Wireless USB Adapter RT5372 N300](https://www.amazon.com/ASHATA-Wireless-Network-Adapter-DWA-140/dp/B07X264THJ)

Amazon - $8 USD - [Wendry Wireless USB Adapter, 2.4GHz, DWA-140, RT5372 N300](https://www.amazon.com/Wendry-Wireless-Network-Frequency-Ethernet/dp/B07Y2VKDNJ)

##### ```chipset - Realtek rtl8192cu```
Adafruit - $14 USD - [USB WiFi (802.11b/g/n) Module: For Raspberry Pi and more](https://www.adafruit.com/product/1012)

AliExpress - $7 USD - [300M RTL8192CU USB Wireless](https://www.aliexpress.com/item/1005001870267733.html?spm=a2g0o.productlist.0.0.63722220c11UEf&algo_pvid=54943967-a6d9-41a5-a9ee-3c2a6e5a990e&algo_exp_id=54943967-a6d9-41a5-a9ee-3c2a6e5a990e-8&pdp_ext_f=%7B%7D)

-----

#### N150 - USB 2 - 2.4 GHz (WIFI 4)

-----

Note: Several of the below adapters say "Raspberry Pi" which seems to imply they only works with the Raspberry Pi OS but that is not the case. These adapters will work with any mainstream Linux distro that is currently supported by its maker. Another point to make is while N150 adapters are not the latest toy available, they are still very capable, very solid and will certainly allow users to stream FHD video, watch youtube videos, listen to online music and support heavy web surfing without slowdown. Some are cheap enough to justify keeping one around as a backup if for no other reason. My wife's computer uses an adapter with a mt7601u chipset. It just works. In case you are wondering, she uses Linux Mint 20 on an old, but still fast enough, quad core desktop.

-----

##### ```chipset - Mediatek rt5370 (Mediatek bought Ralink a few years ago)``` - N150 - USB 2

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/146597475-4fa85f49-f04b-424d-85b5-15cec897f2f2.png)

Amazon - $15 USD - (nano) [Panda PAU03 (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG) [1]

Review: Solid little NANO adapter. It just works. Some technical details...

```
Supported interface modes:
	 * IBSS
	 * managed
	 * AP
	 * AP/VLAN
	 * monitor
	 * mesh point
Valid interface combinations:
		 * #{ AP, mesh point } <= 8, total <= 8, #channels <= 1
Supported extended features:
	* [ RRM ]: RRM
	* [ FILS_STA ]: STA FILS (Fast Initial Link Setup)
	* [ CQM_RSSI_LIST ]: multiple CQM_RSSI_THOLD records
	* [ CONTROL_PORT_OVER_NL80211 ]: control port over nl80211
WPA3 supported: Yes
```

![image](https://user-images.githubusercontent.com/69053122/146597551-7bbe3b45-528d-4a55-a5c6-c08b85d9d8a6.png)

Amazon - $16 USD - [Panda Mid Range 150Mbps Wireless N USB Adapter w/ 2dBi Antenna](https://www.amazon.com/gp/product/B004AC0L4Y) - I have read many positive comments from Linux users about this adapter.

Amazon - $12 USD - [EDUP USB Wireless WiFi Dongle Stick Adapter for Set-top Box, Laptop, Notebook, Desktop PC, Jynxbox, Linkbox, Raspberry Pi](https://www.amazon.com/Wireless-Adapter-Notebook-Raspberry-WINCE6-0/dp/B09NNMJQVL)

Amazon - $20 USD - [CanaKit BC19675 Raspberry Pi WiFi Adapter](https://www.amazon.com/dp/B00GFAN498)

Amazon - $10 USD - [DM-Digital USB WiFi Dongle RT5370 - Ralink](https://www.amazon.com/DM-Digital-WiFi-Dongle-RT5370-Ralink/dp/B015TCA2EM)

Amazon - $11 USD - [150Mbps USB WiFi Adapter, LOTEKOO Wireless Network Card Adapter WiFi Dongle for Desktop Laptop PC](https://www.amazon.com/LOTEKOO-150Mbps-Adapter-Wireless-Raspberry/dp/B06Y2HKT75)

Amazon - $12 USD - [Wireless WiFi USB Dongle Stick Adapter RT5370 150Mbps](https://www.amazon.com/Wireless-Adapter-150Mbps-Set-Top-Raspberry/dp/B01KWQAQ00)

AliExpress - [AliExpress has many links to adapters based on the rt5370 chipset](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20211217111156&origin=y&SearchText=rt5370+usb+wifi+adapter)

-----

##### ```chipset - Atheros ar9271 [2]``` - N150 - USB 2

```
=====> ALFA AWUS036NHA <=====
```
![image](https://user-images.githubusercontent.com/69053122/132881997-c6f89f85-4505-4154-a711-a08796b527a7.png)

Rokland - $25 - [ALFA AWUS036NHA Atheros AR9271 802.11n WIRELESS-N USB Wi-Fi adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036nha-802-11n-wireless-n-usb-wi-fi-adapter-2-watt) - Info: free shipping and no tax outside of Florida. Ships to Canada and US. I have read many positive comments from Linux users about this adapter.

ebay - $25 - [ALFA AWUS036NHA 802.11n Wireless-N Wi-Fi USB Adapter High Speed Atheros AR9271](https://www.ebay.com/itm/ALFA-AWUS036NHA-802-11n-Wireless-N-Wi-Fi-USB-Adapter-High-Speed-Atheros-AR9271/380458349886?epid=1600491254&hash=item589515b53e:g:zW8AAOSwnCFaQ9Oe) - I have read many positive comments from Linux users about this adapter.

AliExpress - $15 USD - [CHANEVE Atheros AR9271 Chipset 150Mbps Wireless USB WiFi Adapter 802.11n Kali Linux](https://www.aliexpress.com/item/4000947646485.html)

Amazon - $42 USD - [WiFi Nation WN-H3 USB WiFi Antenna 802.11n, Speed: 150Mbps, Freq. 2.4GHz and 5dBi Antenna, chipset: Atheros AR9271](https://www.amazon.com/WiFi-Nation-Antenna-802-11n-Speed/dp/B08D7S3GL9)

-----

##### ```chipset - Mediatek/Ralink rt3070 (Mediatek bought Ralink a few years ago)``` - N150 - USB 2

```
=====> ALFA AWUS036NEH <=====
```
![image](https://user-images.githubusercontent.com/69053122/132881657-a3d6a38f-2182-4e39-ab19-149534802118.png)

Rokland - $30 USD - [ALFA AWUS036NEH 802.11n WIRELESS-N USB Wi-Fi adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036neh-802-11n-wireless-n-usb-wi-fi-adapter) - Info: free shipping and no tax outside of Florida. Ships to Canada and US. I have read many positive comments from Linux users about this adapter.

Amazon - $40 USD - [ALFA AWUS036NEH Long Range WIRELESS 802.11b/g/n Wi-Fi USB Adapter](https://www.amazon.com/AWUS036NEH-Range-WIRELESS-802-11b-USBAdapter/dp/B0035OCVO6) I have read many positive comments from Linux users about this adapter.

Note: I own this adapter and run it with Linux. Feel free to ask questions.
Amazon - $13 USD - [Panda Long Range 150Mbps Wireless N USB Adapter w/High Gain Antenna - PAU08](https://www.amazon.com/Panda-150Mbps-Wireless-Adapter-Antennas/dp/B004AC6X0K)

Amazon - $13 USD - [Deal4GO RT3070 802.11n 150Mbps Wireless USB WiFi Adapter WLAN w/ YP243433 Power Amplifier for Ralink RT3070L WiFi Module Kali Linux Ubuntu ](https://www.amazon.com/dp/B086D72XR6)

Amazon - $7 USD - [Panda Mini WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Mini-150Mbps-Wireless-Adapter/dp/B003283M6Q)

Amazon - $20 USD - [INTELLINET IEEE 802.11b/g/n Wireless 150N High-Power USB Adapter](https://www.amazon.com/INTELLINET-802-11b-Wireless-High-Power-525152/dp/B005HF6H28)

Amazon - $13 USD - [coolxan USB Rt3070 Chipset 802.11n 150m WiFi Wireless-n Adapter](https://www.amazon.com/Rt3070-Chipset-802-11n-Wireless-n-Adapter/dp/B00NAXX40C)

-----

##### ```chipset - Mediatek/Ralink rt2870 (Mediatek bought Ralink a few years ago) [2]``` - N150 - USB 2
```
Supported interface modes:
	 * IBSS
	 * managed
	 * AP
	 * AP/VLAN
	 * monitor
	 * mesh point
Valid interface combinations:
		 * #{ AP, mesh point } <= 8, total <= 8, #channels <= 1
Supported extended features:
	* [ RRM ]: RRM
	* [ FILS_STA ]: STA FILS (Fast Initial Link Setup)
	* [ CQM_RSSI_LIST ]: multiple CQM_RSSI_THOLD records
	* [ CONTROL_PORT_OVER_NL80211 ]: control port over nl80211
WPA3 supported: Yes
```

I can't find any new adapters with the rt2870 chipset for sale. My adapter with this chipset is many years old but still snaps to life and works very well when plugged in so if you see adapters, even used adapters with the rt2870 chipset, know that it is still supported in modern distros of Linux and likely will be supported for a long time. If you are wondering if this adapter is slow... it is an 11n adapter and I do not consider it to be slow. You can stream video, surf the net, and listen to online radio without buffering or slowdown (as long as you have good internet service.) I don't list chipsets and adapters here unless I am confident they will meet today's use cases for the WiFi bands that they support.

-----

##### ```chipset -  Mediatek mt7601u``` - N150 - USB 2 - Note: only supports managed and monitor modes (no AP mode and monitor mode only supports a limited number of features).

Note: I own this adapter and run it with Linux. Feel free to ask questions.

Amazon - $9 USD - [DM-Digital USB WiFi Dongle 2dBi MT7601](https://www.amazon.com/DM-Digital-USB-WiFi-Dongle-MediaTek/dp/B0783QRGFR) [1]
```
Supported interface modes:
	 * managed
	 * monitor
Valid interface combinations: None
Supported extended features:
	* [ RRM ]: RRM
	* [ FILS_STA ]: STA FILS (Fast Initial Link Setup)
	* [ CQM_RSSI_LIST ]: multiple CQM_RSSI_THOLD records
	* [ CONTROL_PORT_OVER_NL80211 ]: control port over nl80211
WPA3 supported: Yes
```
Review by Nick - The DM-Digital USB WiFi adapter has proven to be a solid little adapter that has short to medium range (2 dBi antenna.) It runs cool. The driver only supports managed (client) mode and monitor mode, however, this is not an adapter you want if you do WiFi security analysis as some features are not supported in monitor mode. It appears the product was designed for limited function to keep costs low. I have conducted a long term test of this adapter in client (managed) mode and it is very solid. This adapter is a low cost product but appears to be of reasonable quality. If you need a low cost adapter that is only going to be used only in client (managed) mode, you should be happy with this adapter or the EDUP adapter below.

Note: I own this adapter and run it with Linux. Feel free to ask questions.

Amazon - $7 USD - [EDUP USB WiFi Adapter for PC - High Gain 6dBi Antenna](https://www.amazon.com/gp/product/B0827LG8L2)

Amazon - $7 USD - (nano) [MTK7601 Mini 150Mbps USB WiFi Adapter](https://www.amazon.com/Adapter-Dongle-MTK7601-150Mbps-Wireless/dp/B07YQDLHQJ)

Amazon - $9 USD - [Mini 150m USB Wifi Wireless Network Card](https://www.amazon.com/Wireless-Network-802-11-Adapter-Antenna/dp/B008Z9IZSW)

Amazon -$5 USD - [Zibo Mini USB Wifi Wireless Adapter, 150Mbps](https://www.amazon.com/Zibo-Wireless-Adapter-150Mbps-Supports/dp/B00RBBUQLE)

-----

### Linux out-of-kernel drivers (Realtek) for Dual Band USB WiFi Adapters

Note: The below list is ranked in order by quality of driver with best at the top. The best overall Realtek drivers currently are the 8812au, the 8821au (8811au and 8821au chipsets),  the 8821cu (8811cu and 8821cu chipsets) and the 88x2bu (8812bu and 8822bu chipsets).  These drivers perform well in all supported modes that I have been able to test. I concentrate my testing on client (managed), AP and monitor modes. The fastest driver in managed mode is the 88x2bu (8812bu and 8822bu chipsets). My advice, for Linux users needing to buy a new adapter, is to give preference to Mediatek chipset based adapters, as shown above, because the Mediatek drivers are based on Linux Wireless Standards (mac80211) and are maintained in the kernel. This makes the Mediatek based adapters much more troublefree in the long run. If you are unable to find an adapter based on Mediatek chipsets, then I recommend adapters based on these chipsets (in order): 8812au, 8811au, 8811cu and 8812bu. I currently recommend you AVOID adapters based on the Realtek 8814au  and 8832au chipsets as the drivers are not good and I am not seeing anything from Realtek that would change this assessment.

Note: Remember that Realtek out-of-kernel drivers require you to find, download, compile and install the driver source code. The below links provide a lot of information, including information about supported adapters. Nine total chipsets are supported with the following five drivers.

-----

Recent changes:

- 2002-03-07 - changes to reflect a new 8821cu driver
- 2022-02-02 - additions to reflect a lack of support for 4addr
- 2022-01-08 - additions to reflect a lack of support for virtual interface (VIF) or set_wiphy_netns.
- 2021-11-20 - changes to reflect the new 8812au, 8821au and 88x2bu drivers.

-----

##### chipset - rtl8812au - AC1200 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8812AU Chipset](https://github.com/morrownr/8812au-20210629)

The rtl8812au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8812bu chipset for adapters in the AC1200 class. Not many rtl8812au adapters remain available on the market. The above driver is a good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset.  The preferred solution is for Realtek to support an in-kernel Linux Wireless Standards compliant driver but I have seen no indication this will happen.

The Good:

- managed (client) mode works very well
- master (AP) mode is very good
- monitor mode is good
- power saving works well
- very stable
- clean compile and clean log

The Bad:

- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the lack of an in-kernel, Linux Wireless Standards (mac80211) compliant driver makes this chipset problematic
- WPA3 will only work if a version of wpa_supplicant greater than v2.9 is installed
- future Realtek support unknown
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8812bu

Recommendation: This chipset doesn't provide any significant advantages over the mt7612u chipset and the driver for the mt7612u chipset is far superior and is professionally maintained in the Linux kernel. Your long term happiness is probably best served by buying an adapter with a mt7612u chipset if you are looking for an AC1200 class adapter.

-----

##### chipsets - rtl8811au and rtl8821au - AC600 - USB 2
[Linux Driver for USB WiFi Adapters that use the RTL8811AU and RTL8821AU Chipsets](https://github.com/morrownr/8821au-20210708)

The rtl8811au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8811cu chipset for adapters in the AC600 class. Adapters that use the rtl8811au chipset are still available but availability is declining. The above driver is a really good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset. The preferred solution is for Realtek to support an in-kernel Linux Wireless Standards compliant driver but I have seen no indication this will happen.

The Good:

- managed (client) mode works very well
- master (AP) mode is very good
- monitor mode is good
- power saving works well
- very stable
- clean compile and clean log

The Bad:

- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the lack of an in-kernel, Linux Wireless Standards (mac80211) compliant driver makes this chipset problematic
- WPA3 will only work if a version of wpa_supplicant greater than v2.9 is installed
- future Realtek support unknown
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8811cu

Recommendation: Better options are available. You will likely be happier in the long run with an adapter that uses the mt7610u chipset if you are looking for an AC600 class adapter.

-----

##### chipsets - rtl8811cu, rtl8821cu and rtl8831au - AC600  - USB 2
[Linux Driver for USB WiFi Adapters that use the RTL8811CU, RTL8821CU and RTL8831AU Chipsets](https://github.com/morrownr/8821cu)

The rtl8811cu chipset may see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. This chipset tends to run cool, which is good, and Realtek currently provides updated out-of-kernel driver source code on a semi-regular basis. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

The Good:

- fast enough for most users
- runs cool
- possible in-kernel driver support at some point
- AP mode is good
- Monitor mode is good
- readily available at low prices
- power saving works well

The Bad:

- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the lack of an in-kernel, Linux Wireless Standards (mac80211) compliant driver makes this chipset problematic
- the really bad quality of some adapters made with this chipset means you need to reseach before buying

Recommendation: While adapters with this chipset are readily available at low prices, the chipset doesn't provide any advantages over the mt7610u chipset and the driver for the mt7610u chipset is far superior and is professionally maintained in the Linux kernel. As a Linux user, your long term happiness is probably best served by buying an adapter with a mt7610u chipset.

-----

##### chipsets - rtl8812bu and rtl8822bu - AC1200 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu-20210702)

The rtl8812bu chipset may see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. This chipset tends to run cool, which is good. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

The Good:

- very fast in managed (client) mode (for an AC1200 chipset)
- AP mode works well except with RasPi4B (still trying to determine the problem)
- runs cool
- possible in-kernel driver support at some point
- readily available at low prices
- power saving works well

The Bad:

- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the lack of an in-kernel, Linux Wireless Standards (mac80211) compliant driver makes this chipset problematic
- WPA3 will only work if a version of wpa_supplicant greater than v2.9 is installed
- the really bad quality of some adapters made with this chipset means you need to reseach before buying

Recommendation: While adapters with this chipset are readily available at low prices, the chipset doesn't provide any significant advantages over the mt7612u chipset and the driver for the mt7612u chipset is far superior and is professionally maintained in the Linux kernel. As a Linux user, your long term happiness is probably best served by buying an adapter with a mt7612u chipset.

-----

##### chipset - rtl8814au - AC1900 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

The rtl8814au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. Adapters based on this chipset can really push data at high speed and are still available but are relatively expensive. They need a pretty good amount of power so a powered USB 3 hub may be a good idea. This chipset builds a lot of heat so look for adapters that have plenty of vent holes and search reviews to see if users are reporting heat problems. The above driver is not very good but it is based on the latest source we have available. The source is from 2019. We need Realtek to release an updated, modernized version of the driver source code as the code for this driver is showing some age and is hard to maintain. Will Realtek release a new, improved version? I don't know.

The Good:

- fastest USB chipset available (however, performance with the currently available driver is not that good, the AC1200 based adapters are faster)
- managed (client) mode is reasonably good but not fast
- master (AP) mode was recently patched and is working now (finally)
- monitor mode, including injection and deauth, are now working (finally), still some problems with capture

The Bad:

- Many resellers advertize Linux support but that is deceptive at best
- the lack of an in-kernel, Linux Wireless Standards (mac80211) compliant driver makes this chipset problematic
- WPA3 does not work on tested distros
- no support for interface combinations
- no support for extended features
- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- no AP mode DFS support
- no mesh support
- no AP/VLAN support
- no P2P-client support
- no P2P-GO support
- future Realtek support unknown
- no new source code releases since 2019, and that 2019 release was not a good driver
- uses a lot of power so using a powered hub may be a good idea
- produces a lot of heat, adapter needs a lot of vent holes
- expensive

Recommendation: Do not buy adapters based on this chipset. You will be disappointed.

-----

##### chipset - rtl8832au - AX1800 - USB 3

The rtl8832au chipset is a very new chipset and is the first AX class chipset that is available for use in USB WiFi adapaters. Unfortunately, Realtek has decided to support it with an out-of-kernel driver instead of doing the right thing and providing a mac80211 technology in-kernel driver. I have been testing this driver (v1.15.0.1). The results are not good. As many of you known, I have a lot of USB WiFi adapters that I test. I cannot recall a single time when a driver has locked up a system... until now. While testing this new driver on multiple systems this week, I experienced numerous system lockups requiring me to pull the plug to get things going again. Additionally many features are simply not working. Power saving does not work. DFS channels do not work in AP mode. USB mode control is problematic. WPA3 does not work in any mode. I see problems in basic client mode that I cannot explain. This is a VERY BAD driver. Avoid adapters based on the 8832au chipset.

The Good:

- I'm still looking for the good.
-
The Bad:

- A lot of bad here. I'll update the list at some point as I have time.

Recommendation: AVOID adapters based on this chipset. You will be disappointed.

-----

Link to MT76 driver in the Linux kernel: (mt7612u and mt7610u chipsets)

https://github.com/torvalds/linux/tree/master/drivers/net/wireless/mediatek/mt76

-----

Hopefully this document is of help to Linux users that want or need USB WiFi
adapter support. I will look to expand and improve this document in the future.

-----

The mission of this site is to collect information and provide links regarding the purchase and use of USB WiFi adapters with Linux.

Any information and links you can provide are welcome. Submit the information and links by clicking on Issues...or if you are a Github user, submit a Pull Request.

Regards,

Nick

[1] I have and use this adapter

[2] I have an adapter that uses this chipset
