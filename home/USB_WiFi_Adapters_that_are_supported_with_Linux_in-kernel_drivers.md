## USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers

```in-kernel``` means plug and play, no need to install a driver.

-----

Important: Price and availability of listed adapters is subject to change. Updating the list of adapters does take a considerable amount of time. I try to complete a review of the links at least once per month. This site has increased in popularity to the point that readers of this site may cause inventory problems for some sellers at times so you may need to wait for inventory to be refreshed. To help with this problem, I have listed multiple links from multiple sellers for some products. If you see any problems or have links that should be added, please post in `Issues.`

Market Conditions: 2022-09-20 - Many good adapters are available. Prices for some, but not all, adapters are still higher than before the pandemic and certainly higher than we would like to see. The global shortage of chips caused by fab plants being shut down for periods during 2020/2021 and the inadequate investment in new fab plants for many years has led to tight markets that have caused high prices for some products and shortages of some products. This problem has recently been compounded by international shipping problems, continued outbreaks of COVID-19 and the war in Ukraine. Higher than normal prices as well as periodic shortages may continue for some time...possibly into 2023. Most of you should be able to find something that meets your needs at a price you can afford if you shop around.

WARNING: I am seeing reports that concern me from users that want to buy adapters based on the mt7921au chipset. They are ending up with adapters that use the rtl8832au chipset due to bad information on some websites. One adapter in particular, Comfast CF-952AX, has been purchased due to ads that say it has the mt7921au chipset. However, it contains the rtl8832au chipset which is a really bad chipset for Linux users. The list below is carefully constructed and maintained to provide information and links that are known to be good. Mistakes can be made and I want to hear about mistakes so they can be corrected. An example of how this site is careful about information and links is that recently Netgear released a new adapter called the A8000. All evidence points to this adapter using the mt7921au chipset but the available evidence is not conclusive at this point so the adapter is not listed yet. Be careful with online information. 

-----

### Tri Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers

-----

#### AX3000 - USB3.0 - 2.4 GHz, 5 GHz and 6 GHz (WiFi 6E)

-----

##### ```chipset - Mediatek mt7921au - supported in-kernel since Linux kernel 5.18 (2022) (AP Mode support added in kernel 5.19) - Filogic 330 - abgn+ac+ax - 2x2:2 - Wi-Fi 6E, WPA3, OFDMA, Zero DFS, BT 5.2, MU-MIMO, 1024QAM, HE80, LNA/PA, ESR```

Status: 2022-10-29 - USB adapters featuring the mt7921au chipset have been available since July 2022. Links and information are shown below. See Issue 87 for an early discussion on techical details. ```Adapters based on the mt7921au chipset should not be considered plug and play``` unless you are using a very recently released distro with kernel 5.19 or later such as the newly released Ubuntu 22.10. Many distros will currently require you to install a newer kernel and firmware than you have. This situation will correct itself over the next few months as Linux distros upgrade to kernel 5.19 or later. ```If you are not technically inclined and want a plug and play adapter right now, continue on to the AC1200/AC1300 section as adapters there and for the rest of the document are currently plug and play with almost all popular non-server distros.```

Warning: USB WiFi adapters based on the mt7921au chipset are new and only limited testing has been reported. The driver and firmware
are new as well. The driver is located in very recent versions of the Linux kernel. The firmware for in-kernel drivers may not be
upgraded in your distro yet so you may need to ungrade it manually. What are the minimums?

- Minimum kernel for managed (client) mode = 5.18
- Minimum kernel for monitor mode = 5.18
- Minimum kernel for master (AP) mode = 5.19
- [Firmware](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Install_Firmware_for_Mediatek_based_USB_WiFi_adapters.md)

Note: There is an exception to the above for OpenWRT. MT7921u has been backported to the kernel (5.10) used in OpenWRT 22.03.x. Simply install the following packages:

```
kmod-mt7921u
kmod-mt7921e (this is only necessary to load the firmware and should be unnecessary in future OpenWRT releases.)
```

Note about OpenWRT 22.03: Luci is only able to support WiFi 6 (AX). WiFi 6e requires manual configuration.

It is possible that some distros using kernel 5.18 or greater have not turned on compiling of the driver so the following is an
example of where the driver (mt7921u.ko) is located depending on which kernel you have installed. You can check to see if the
driver (module) is in this location:

/usr/lib/modules/`<your kernel version>`/kernel/drivers/net/wireless/mediatek/mt76/mt7921/mt7921u.ko

Some distros do not install firmware, Debian is an example, and some distros may not do it right so you need to
check the [firmware](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Install_Firmware_for_Mediatek_based_USB_WiFi_adapters.md)
to see if it needs to be installed or upgraded. Keep in mind that firmware file names do not change so you have to compare file
sized to determine if you have the latest version. The symptom of a firmware problem is that the adapter does not show
up... just like if there is no driver installed. For adapters that use in-kernel drivers to function properly,
the driver (module) is required AND the firmware is required. The absence of either will cause the adapter to
not show up on boot.

Update 2022-08-24 - Reports from multiple users indicate that the CF-953AX and CF-951AX adapters are not dual band as advertised,
they are tri band. In other words, these adapters appear to support 6 GHz channels as well as the 5 GHz and 2.4 GHz channels. I am
also getting reports that these adapters are performing well in monitor mode...on all 3 bands and in channel widths up to 80 MHz.
The published information that I have been able to find does indicate the mt7921au chipset is a WiFi 6E, tri band chipset that also
supports Bluetooth 5.2. Let me repeat some of the important information above: If you are not a highly technical person then you
should probably not purchase an adapter based on the mt7921au chipset until such time as your distro has upgraded to at least
kernel 5.19. Skipping to the AC1200/AC1300 section is recommended for most people as that section and the ones that follow use
chipsets and drivers that are well tested and recommended. 

```
>=====>  COMFAST CF-953AX  <=====<
```
![CF-953AX](https://user-images.githubusercontent.com/69053122/180594207-e3ee44ec-aac0-4c75-bd01-09454184bc57.jpg)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7921au chipset.
```

AliExpress - $23 USD - [COMFAST CF-953AX](https://www.aliexpress.com/item/3256804283254522.html)

Review: We need someone with this adapter to write a review.

```
>=====>  COMFAST CF-951AX  <=====<
```

Maintained by @morrownr

![CF-951AX](https://user-images.githubusercontent.com/69053122/185668163-91e6df3c-7e39-45a7-885b-2f36b8b61873.jpg)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7921au chipset.
```

CPU Solutions - $25 USD - [COMFAST CF-951AX Wifi 6 USB Adapter 802.11AX](https://www.cpusolutions.com/store/pc/COMFAST-CF-951AX-Wifi-6-USB-Adapter-802-11AX-Wi-fi-Dongle-1800Mbps-Dual-Band-Wireless-Adapter-p6657.htm) - (CPU Solutions is located in Middleton, WI, USA)

Note about the above link: To get the $25 USD price, you have to call 800-474-4278 and tell them you want the adapter shipped via USPS ground (or cheapest USPS way). Their web site is currently only setup to handle UPS and UPS shipping rates are currently very high. 

AliExpress - $23 USD - [COMFAST CF-951AX Wifi 6 USB Adapter 802.11AX](https://www.aliexpress.com/item/3256804245691865.html)

Review: I have been using the CF-951AX for a few months now. I have good things to say about the mt7921au chipset and the mt7921u in-kernel driver. The jury is still out on this specific adapter.

The bad:

- This adapter will not work with any of the USB3 extention cables or powered USB3 hubs that I have. The cause is unknown at this time. I consider good compatibility with extention cables a must with USB WiFi adapters so that the adapter can be positioned for best reception. You may have to plug this adapter into a port on your system for it to work.
- The case of the adapter is too wide. If you plug it directly in a usb port on a Raspberry Pi, there is no way to use the port to the side.
- No AP mode 5 GHz DFS channels support. Come on Mediatek, fix this! It is more important that you think!

The good:

- The mt7921au chipset seems to be very good. It is fast and it is confirmed to be tri-band.
- Did I mention that this chipset is fast? WiFi 5 = around 650 Mb/s in my testing.
- The mt7921u in-kernel driver is good (maybe a bug or two for now but overall good).
- The mt7921u in-kernel driver is very stable and supports more than one adapter with the
mt7921au chipset in a single system at the same time.
- I have tested 5 GHz band managed mode, AP mode and monitor mode with very good results.
- I have tested WiFi 6 support for managed mode, AP mode and monitor mode with very good results.

Note: I am not well equipped to test WiFi 6e yet so will have to do that when able.

```
>=====>  ALFA ?  <=====<
```
Note: Indications are that ALFA will ship products based on the mt7921au chipset but no timeline is currently available.

-----

### Dual Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers

-----

#### AC1200 / AC1300 - USB 3 - 2.4 GHz and 5 GHz (WIFI 5)

-----

##### ```chipset - Mediatek mt7612u - supported in-kernel since Linux kernel 4.19 (2018)``` - [mt7612u info](https://github.com/morrownr/7612u)

```
>=====>  ALFA AWUS036ACM  <=====<
```

Maintained by @morrownr

![image](https://user-images.githubusercontent.com/69053122/127750949-809364a6-65ed-4c7c-9abe-4a77cb73848e.png)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
```

Rokland - 43 USD - US - [ALFA AWUS036ACM 802.11ac Dual Band USB WiFi Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036acm-802-11ac-dual-band-2-4-5-ghz-wifi-usb-adapter) - Info: free shipping and no tax outside of Florida. Ships to Canada and US.

Amazon - 43 USD - US - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD)

ebay - 38 USD - US - [Alfa AWUS036ACM 867Mbps Long Range Dual Band Wi-Fi USB Adapter](https://www.ebay.com/p/1738034359)

Amazon.it - 51 EUR - Italy - [Alfa AWUS036ACM](https://www.amazon.it/Alfa-AWUS036ACM/dp/B08BJS8FXD/ref=sr_1_9?__mk_it_IT=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=2G6VAKKHUQXQB&keywords=mediatek+wifi+adapter&qid=1650990071&sprefix=mediatek+wifi+adapter%2Caps%2C278&sr=8-9)

getic - 32 plus VAT EUR - Latvia - [Alfa USB Adapter AWUS036ACM](https://www.getic.com/product/alfa-awus036acm)

TUNG NETWORK TRADING - 220 RM - Malaysia - [Alfa AWUS036ACM 802.11ac Dual Band 2.4/5 GHz WiFi USB Adapter](https://www.alfa.net.my/webshaper/store/viewProd.asp?pkProductItem=70)

(out of stock) Varia - 42 EUR - Germany - [AWUS036ACM - 802.11ac Dualband-WLAN-USB-Adapter 2,4/5 GHz](https://www.varia-store.com/de/produkt/265294-awus036acm-802-11ac-mimo-dualband-wlan-usb-adapter-mit-2-4-5-ghz.html)

[ALFA AWUS036ACM Technical information](https://github.com/morrownr/USB-WiFi/blob/main/home/iw_list/ALFA_AWUS036ACM.txt)

[ALFA Network Linux support for MT7612U based products](https://docs.alfa.com.tw/Support/Linux/MT7612U/)

Review by Nick - The Alfa AWUS036ACM is an excellent product. It is mid-priced, well made and works well in managed mode, master mode and monitor mode. It is a very solid, stable performer in 5 GHz AP mode. It supports 80 MHz channel width in AP mode and can sustain 400+ Mb/s as measured by iperf3. It runs cool and uses a maximum of only about 380 mA power when under heavy load. I use one in the wifi router/access point that I built. Works so well with the Raspberry Pi 4B, 3B+ and 3B, it is almost like it was designed specifically for that hardware. You really need to use it with a Raspberry Pi 4b so as to get the full througput capability. It works well with desktop systems (an extension cable is included in the packages most retailers of this product sell). It also works well with laptop systems. This adapter is a high quality product with good range and is plug and play in all of the modern distros of Linux. Highly recommended.

```
>=====>  Panda PAU0D  <=====<
```

![image](https://user-images.githubusercontent.com/69053122/201191537-8f7e093c-250f-4aca-bdf2-8470f0bf621d.png)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
```

Amazon - 40 USD - US - [Panda Wireless PAU0D AC1200 Wireless AC USB Adapter with High Gain Antennas](https://www.amazon.com/Panda-Wireless-AC1200-Adapter-Antennas/dp/B0B2QD6RPX)

Review: Pending

```
>=====>  TEROW ROW02CD and TEROW ROW02FD  <=====<
```

![image](https://user-images.githubusercontent.com/69053122/127751374-7a814003-6ff5-4da6-8534-bdc61ea5f249.png)

```
Note: This adapter uses the mt7612u chipset.
```

Out of stock at previous link. If you are aware of a good link to the TEROW ROW02CD, please let us know.

Warning: TEROW sells a TEROW ROW12CD that is reported to be based on a rtl8812bu chipset. That is not what you want.

Review by Nick - The TEROW ROW02CD and TEROW ROW02FD work very well with the Raspberry Pi 4B, 3B+ and 3B. I have tested both with various desktop and laptop systems. The TEROW ROW02CD is a single state adapter and the TEROW ROW02FD is a multi-state adapter. You should give perferrence to single state adapters. The cost of these adapters is very low. The performance and quality of the materials used and capabilities of these adapters is not quite as good as the Alfa AWUS036ACM but that is to be expected since the Alfa AWUS036ACM is a more expensive, premium quality adapter. My experience is that these adapters do provide good stable performance and should meet the needs of most Linux users. In fact, during my testing, a TEROW ROW02FD outperformed in link quality and signal level vs. a similar adapter based on a rtl8812bu chipset when plugged into the same USB3 port and connected to the same wifi router.

Additional information about the TEROW ROW02FD (driver free) (the multi-state version) - 2022-03-27 - The Raspberry Pi OS 64 bit release date 2022-01-28 ships with an old version of the data file for usb_modeswitch which will make it look like you need to install a driver. That is not the problem. For more information, see [How to Modeswitch](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Modeswitch.md). To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the adapter will "just work."

```
>=====>  AVM FRITZ! AC 860  <=====<
```

Maintained by @mendel5

![Fritz-860](https://user-images.githubusercontent.com/69053122/193471131-931d28e0-0353-4d66-9732-99662b8f5c0c.jpeg)

```
Note: This is a multi-state adapter.
Note: This adapter uses the mt7612un chipset.
```

Geizhals.eu - 35 EUR - [AVM FRITZ! AC 860](https://geizhals.eu/avm-fritz-wlan-usb-stick-ac-860-20002687-20002724-a1082383.html)

Amazon Germany - 37 EUR - [AVM FRITZ! AC 860](https://www.amazon.de/dp/B017BD21R8/)

Amazon France - 52 EUR - [AVM FRITZ! AC 860](https://www.amazon.fr/dp/B019E28V4G/)

Amazon Italy - 39 EUR - [AVM FRITZ! AC 860](https://www.amazon.it/dp/B019E28V4G/)

Review:

```
>=====>  COMFAST CF-WU785AC  <=====<
```

![image](https://user-images.githubusercontent.com/69053122/128245876-c6944254-cf57-4134-92bb-6dd0d67d16bd.png)

```
Note: This is a multi-state adapter.
Note: This adapter uses the mt7612u chipset.
```

AliExpress - $22 USD - [Comfast 1300Mbps WI-FI Receiver 4*6dBi Dual Band Antenna Driver-Free Long Range Network Card 2.4&5GHz Desktop Adapter CF-WU785AC](https://www.aliexpress.com/item/1005002533185743.html)

Review by Nick - This adapter gives solid results. 

Managed (client) mode iperf3 results:

```
Bitrate         Retr
385 Mbits/sec    0             sender
385 Mbits/sec                  receiver
```

Note: The distance from adapter to access point was about 20 feet through 2 walls. I was using a clean DFS channel (104) and set iperf3 to run for 2 minutes so as to see if there were any abnormalities that would show up. No problems noted. This adapter can sustain high transfer rates and uses only about 380 mA during sustained high transfer rates. I used this adapter as my daily driver on my main workstation for about 2 months. I have not noticed any drops at all. It seems to be a very solid adapter and has pretty good range. Range is not what you see from an adapter like the ALFA AWUS036ACHM (further down) but the ALFA AWUS036ACHM is really hard to beat for range. Overall, this adapter is solid and comes with a faily low price tag.

Additional information about the COMFAST CF-WU785AC - 2022-03-27 - The Raspberry Pi OS 64 bit release date 2022-01-28 ships with an old version of the data file for usb_modeswitch which will make it look like you need to install a driver. That is not the problem. For more information, see [How to Modeswitch](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Modeswitch.md). To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the adapter will "just work." 

```
>=====>  COMFAST CF-WU782AC  <=====<
```

![image](https://user-images.githubusercontent.com/69053122/127756396-a5e425c7-0aa0-4593-a4d1-32ef442f58b3.png)

```
Note: This is a multi-state adapter.
Note: This adapter uses the mt7612u chipset.
```

AliExpress - $20 USD - [Comfast USB 3.0 Wireless Wifi Adapter Dual Band 2.4+5 GHz 150 -1300 Mbps 802.11AC 802.11 a/b/n/g/ac with 2*6dbi Antennas](https://www.aliexpress.com/item/32902591576.html)

Note: The above link shows 3 adapters. The one you want is the CF-WU982AC - 1300Mbps - > Black <

Review by soyersoyer - The COMFAST CF-WU782AC works well with my RasPi4b (and hostapd). I had to use the disable_usb_sg=1 parameter. I like this setup because it can route near gigabit speeds. My mobile devices have 300-500mbit/s download speed too, it has guest wifi, and I can easily switch to a newer wifi adapter later. The rpi runs kodi, a shairport server and a bluetooth sound receiver server too. I bought the wifi adapter from AliExpress.

Additional information about the COMFAST CF-WU782AC - 2022-03-27 - The Raspberry Pi OS 64 bit release date 2022-01-28 ships with an old version of the data file for usb_modeswitch which will make it look like you need to install a driver. That is not the problem. For more information, see [How to Modeswitch](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Modeswitch.md). To clarify: Most Linux users will never know that this adapter is multi-state because the usb-modeswitch utility is installed and active on almost all modern Linux distros so the adapter will "just work." 

```
>=====>  Netgear A6210  <=====<
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/127751480-4c34f5d7-3e7e-47ad-baab-aa5bad62c6bb.png)

```
Note: This adapter uses the mt7612u chipset.
```

ebay - $25 USD - [NETGEAR AC1200 USB 3.0 Wi-Fi Adapter - A6210-10000S](https://www.ebay.com/p/18021987463)

Walmart - $65 USD - [NETGEAR AC1200 Dual Band Wifi USB Adapter (A6210-100PAS)](https://www.walmart.com/ip/NETGEAR-AC1200-Dual-Band-Wifi-USB-Adapter-A6210-100PAS/40164604)

Amazon - $58 USD - [NETGEAR AC1200 Wi-Fi USB Adapter High Gain Dual Band USB 3.0 (A6210)](https://www.amazon.com/NETGEAR-AC1200-Wi-Fi-Adapter-A6210-100PAS/dp/B00MRVJY1G)

Best Buy - $65 USD - [NETGEAR - AC1200 Dual-Band WiFi USB 3.0 Adapter - Black](https://www.bestbuy.com/site/netgear-ac1200-dual-band-wifi-usb-3-0-adapter-black/8860004.p?skuId=8860004)

Review by Nick - The Netgear A6210 is an adapter that is designed to be portable and, as such, has a shorter range than adapters with larger antennas. It comes with a good quality USB3 extension cable plus cradle. It is a stable performer. I have noted that it runs a little warm which is unusual for Mediatek chipset based adapters. Users looking for a portable AC1200 adapter that uses an in-kernel driver and has good performance over short to medium distances should be happy with this adapter. Note: Due to the somewhat limited range of this adapter, I do not recommend it for use in AP mode unless your requirement is only for same room connections. I also do not recommend this adapter for security analysis/pen testing because of the shorter than expected range.

To be clear: This adapter can provide good throughput. Here is a sample from iperf3:

```
Bitrate
  366 Mbits/sec                  sender
  365 Mbits/sec                  receiver

```

This test was conducted in client mode at a distance of about 5 meters with 2 walls between the adapter and wifi router. The test was on 5 GHz on a clean DFS channel. This test shows that this adapter can certainly provide AC1200 performance and it is a good adapter to take on the road. It does not have long range so use as an AP should be limited to same room or short distance and monitor mode performance is not going to let you reach out long distances. It appears the twpower is fixed on this adapter at 18 dBm. I am posting this additional paragraph because a user expressed some displeasure at not being able to get this adapter to do what he wanted. My suggestion is that anyone that is not sure of what you need, go to `disccusions` or `issues` and ask.

```
>=====>  Walmart  <=====<
```

Important: The following link to Walmart will show various adapters that supposedly are based on the mt7612u or mt7612un chipsets. My opinion is that most of the ads that say the adapter uses a mt7612u chipset are correct but I've seen some ads (the ones with a single physical antenna are suspect and the ones that do not mention 7612u are also suspect) where I do not think that is the case, however, Walmart's return policy is legendary. Walmart will find a way to make you happy if you are not happy so there is a reduced risk in dealing with Walmart in this regard.

Full disclosure: I do not work for Walmart but I do live just a few minutes away from Walmart Worldwide HQ. I make every effort to provide accurate information and try not to favor any company based on location or association.

Walmart - [Walmart has many links to adapters based on the mt7612u chipset](https://www.walmart.com/search/?query=MT7612U)

Note: The above link will show many adapters. Ensure you check to make sure the adapter is based on the mt7612u chipset.

2022-12-01 - As of this date, the one I would order is shown below. Why? It shows that it ships with a CD which probably means that it is a single-state adapter.

[Lomubue M-1200M Wireless Network Card](https://www.walmart.com/ip/Lomubue-M-1200M-Wireless-Network-Card-High-speed-Anti-interference-Driver-free-USB3-0-MT7612U-Dual-Band-WiFi-Transceiver-for-Router/731709450?athbdg=L1400)

-----

#### AC580 / AC600 - USB 2 - 2.4 GHz and 5 GHz (WIFI 5)

-----

##### ```chipset - Mediatek mt7610u - supported in-kernel since Linux kernel 4.19 (2018)```

Note: I own one or more adapters based on the mt7610u chipset. Feel free to ask questions.

```
=====> ALFA AWUS036ACHM <=====
```

![image](https://user-images.githubusercontent.com/69053122/129494292-e3e363ed-8119-4ab5-97cb-13018710a289.png)

Note: This adapter looks like a basic everday wifi adapter but it is not! I have tested many adapters and this adapter has the longest range of any modern dual band adapter that I have tested. If you need long range or an adapter that can run 24/7/365 and never miss a beat, this adapter is worth a look. Don't buy it for speed as it is a AC600 adapter, but if looking for range, great AP mode support, great monitor mode support and reliability, take a look.

Rokland - $40 USD - [ALFA AWUS036ACHM 802.11ac Dual Band High Power Mediatek MT7610U WiFi USB Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036achm-802-11ac-dual-band-high-power-ac1200-mediatek-wifi-usb-adapter)

ebay - $40 USD - [Alfa AWUS036ACHM 802.11ac dual band High Power Wi-Fi USB Adapter +RP-SMA antenna](https://www.ebay.com/itm/265323549415)

Amazon - $40 USD - [Alfa AWUS036ACHM 802.11ac WiFi Range Boost USB Adapter](https://www.amazon.com/AWUS036ACHM-802-11ac-Range-Boost-Adapter/dp/B08SJBV1N3)

ebay - $44 USD - [Alfa AWUS036ACHM 802.11ac dual band High Power Wi-Fi USB Adapter +RP-SMA antenna](https://www.ebay.com/itm/383907328953?epid=22045834288&hash=item5962a8f3b9:g:JiEAAOSwbatgBI-l)

Varia - 44 EUR - Germany - [AWUS036ACHM - 802.11ac WiFi USB-Adapter](https://www.varia-store.com/de/produkt/265368-awus036achm-802-11ac-wifi-range-boost-usb-adapter.html)

TUNG NETWORK TRADING - 210 RM - Malaysia - [Alfa Network AWUS036ACHM 802.11ac WiFi USB Adapter](https://www.alfa.net.my/webshaper/store/viewProd.asp?pkProductItem=83)

[ALFA AWUS036ACHM Technical information](https://github.com/morrownr/USB-WiFi/blob/main/home/iw_list/ALFA_AWUS036ACHM.txt)

[ALFA Network Linux support for MT7610U based products](https://docs.alfa.com.tw/Support/Linux/MT7610U/)

Review by Nick - The Alfa AWUS036ACHM is a good product. It is mid-priced, well made, runs cool, has EXCEPTIONAL range and works well in managed mode, master mode and monitor mode. I have recently been testing master (AP) mode: This adapter is exceptional in 2.4 GHz AP mode and good in 5 GHZ AP mode. The range in both bands exceeds the wifi router that I tested it against and I consider that wifi router to have good range. One thing to consider regarding 5 GHz AP mode is that this is an AC600 device so maximum transfer rate is limited to 433 Mb/s. That is fast enough for most use cases and will be for a long time but it is not as fast as you can get from an AC1200 adapter. This adapter shows good link quality and signal level even in difficult situations where other adapters would drop the connection. My testing shows that this adapter has the longest range of any current dual band consumer grade adapter that Alfa sells and Alfa is known for their long range products. My opinion is that this adapter is the single best adapter available for use with Kali Linux or other distros used for pen testing and security analysis. Compared to the Alfa AWUS036ACH, the Alfa AWUS036ACHM has better range, costs less and is supported with in-kernel drivers making it the better choice for Linux users. It comes with the required USB2 cable and a clip that allows you to mount the adapter in various locations. Overall, the Alfa AWUS036ACHM is a solid performer. Highly recommended.


```
=====> ANDDEAR - MT761003 <=====
```

![76-new](https://user-images.githubusercontent.com/69053122/132886023-58a44509-1d65-4de7-96fe-803064631301.jpg)

AliExpress - $12 USD - [ANDDEAR - MT761003](https://www.aliexpress.com/item/4000079918154.html)

Review by amisix - This adapter is $12 as of 2022-04-22. It is size (2.25" x 1" x .3"). It consumes less power than many adapters (~110mA/idle, 150mA-230mA/at load). The ANDDEAR-MT761003 is only an AC600 adapter (150N/433AC) although it performs quite well in real-world usage, has a medium transmission distance, and when running casual internet speed tests it easily achieved 100Mbps - the maximum speed of my ISP. It has an excellent Mediatek chipset that is highly capable with AP, monitor mode, and packet injection and the drivers are included in kernel so it just works. Overall I highly recommend the ANDDEAR-MT761003 if you're looking for something that's highly capable and you need qualities other than raw speed.

Important: ANDDEAR also makes an AC1200 version of this adapter that uses a mt7612u chipset. Avoid it. In testing, it was found to have a bug that generally shows in USB3 ports if port 1 is used. The conclusion of the testers is that the mt7612u chipset version of this adapter should be avoided as no workaround or fix could be identified. However, the above listed adapter based on the mt7610u chipset does not show this critical bug and should work well for you.

```
=====> Linksys AE6000 <=====
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/130810068-149bfebd-f93d-4bf3-af84-9a568806d93d.png)

Note: The ANDDEAR - MT761003 is a more cost effective adapter unless you happen to need a very small adapter.

Walmart - $30 USD - [Linksys AE6000 Wireless-AC Mini USB Adapter](https://www.walmart.com/ip/Linksys-AE6000-Wireless-AC-Mini-USB-Adapter/24032271)

Review by Nick - The Linksys AE6000 is a good product. It has better range than most other small adapters that I have used. I am not saying that it is a long range adapter, just that it does pretty good for being a very small adapter. And it is a small adapter. The picture may make the adapter look larger than it is. It is not much bigger than a nano size adapter. Overall, it is a solid performer. Recommended.

--- Links to additional adapters that are based on the mt7610u chipset ---

ebay - $20 USD - [ZyXEL Dual-Band Wireless AC600 USB Adapter, NWD6505](https://www.ebay.com/itm/293268959565)

Amazon - $30 USD - [Asus Dualband Wirel. AC600 USB, USB-AC51](https://www.amazon.com/Asus-Dualband-Wirel-AC600-USB-AC51/dp/B00T3DK154)

Amazon - $25 USD - [Panda Pau0a AC600 Dual Band Wireless USB Adapter](https://www.amazon.com/Panda-Wireless-PAU0A-AC600-Adapter/dp/B07C9TYDR4)

eBay - $17 USD - [TP-LINK Archer T1U AC450 Wireles Nano USB Adapter](https://www.ebay.com/itm/392631860422)

Note: The link to the above TP-Link T1U is for used adapters as the product has been discontinued. I usually do not list links to used products but many people have asked about dual band nano adapters.

-----

#### N600 - USB 2 - 2.4 GHz and 5 GHz (Dual Band) (WIFI 4)
-----
##### ```chipset - Mediatek/Ralink rt5572 (Mediatek bought Ralink a few years ago)```

Walmart - [Walmart has many links to adapters based on the rt5572 chipset](https://www.walmart.com/search/?query=rt5572)

Note: The above link will show many adapters. Ensure you check to make sure the adapter is based on the rt5572 chipset.

Amazon - $65 USD - [Panda Wireless PAU09 N600 Dual Band (2.4GHz and 5GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-Wireless-PAU09-Adapter-Antennas/dp/B01LY35HGO) - I have read many positive comments from Linux users about this adapter but it sure is expensive.

Amazon - $55 USD - [Panda N600 Dual Band (2.4GHz & 5.0GHz) Wireless N USB Adapter](https://www.amazon.com/Panda-2-4GHz-300Mbps-Wireless-Adapter/dp/B00U2SIS0O)

AliExpress - $13 USD - [802.11a/b/g/n 300Mbps Dual Band Wireless USB WiFi Adapter - Ralink RT5572](https://www.aliexpress.us/item/2251832642810939.html)

##### ```chipset - Mediatek/Ralink rt3572 (Mediatek bought Ralink a few years ago)```

AliExpress - $14 USD - [CHANEVE RT3572 Dual band 300Mbps Wireless Lan Adapter 5.8Ghz USB Wi-Fi Adapter Ralink RT3572 Dongle For Kali Linux and Samsung TV](https://www.aliexpress.com/item/4000979870302.html)

AliExpress - $14 USD - [WTXUP RT3572 600Mbps 802.11a/b/g/n Wireless USB WiFi Adapter + 2x 5dBi External WiFi Antenna for SamSung TV Windows 7/8/10
](https://www.aliexpress.com/item/2251832463244006.html)

AliExpress - [AliExpress has many links to adapters based on the rt3572 chipset](https://www.aliexpress.com/wholesale?catId=0&initiative_id=SB_20210821143225&origin=y&SearchText=rt3572)

Note: The above link will show many adapters. Ensure you check to make sure the adapter is based on the rt3572 chipset.

-----

### Single Band USB WiFi Adapters that are supported with Linux ```in-kernel``` drivers

-----

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can be very handy.

-----

#### N150 - USB 2 - 2.4 GHz (WIFI 4)

-----

Note: Several of the below adapters say "Raspberry Pi" which seems to imply they only works with the Raspberry Pi OS but that is not the case. These adapters will work with any mainstream Linux distro that is currently supported by its maker. Another point to make is while N150 adapters are not the latest toy available, they are still very capable, very solid and will certainly allow users to stream FHD video, watch youtube videos, listen to online music and support heavy web surfing without slowdown. Some are cheap enough to justify keeping one around as a backup if for no other reason. My wife's computer uses an adapter with a mt7601u chipset. It just works. In my opinion, the best full function (managed, AP and monitor modes) single band chipset for Linux users is the rt5370 as shown in the next section below:

-----

##### ```chipset - Mediatek rt5370 (Mediatek bought Ralink a few years ago)``` - N150 - USB 2

Note: I own one or more adapters based on the rt5370 chipset. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/146597475-4fa85f49-f04b-424d-85b5-15cec897f2f2.png)

Amazon - $15 USD - (nano) [Panda PAU03 (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG)

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

Amazon - $15 USD - [Panda Mid Range 150Mbps Wireless N USB Adapter w/ 2dBi Antenna](https://www.amazon.com/gp/product/B004AC0L4Y) - I have read many positive comments from Linux users about this adapter.

Amazon - $10 USD - [EDUP USB Wireless WiFi Dongle Stick Adapter for Set-top Box, Laptop, Notebook, Desktop PC, Jynxbox, Linkbox, Raspberry Pi](https://www.amazon.com/Wireless-Adapter-Notebook-Raspberry-WINCE6-0/dp/B09NNMJQVL)

Amazon - $20 USD - [CanaKit BC19675 Raspberry Pi WiFi Adapter](https://www.amazon.com/dp/B00GFAN498)

Amazon - $9 USD - [DM-Digital USB WiFi Dongle RT5370 - Ralink](https://www.amazon.com/DM-Digital-WiFi-Dongle-RT5370-Ralink/dp/B015TCA2EM)

Amazon - $12 USD - [150Mbps USB WiFi Adapter, LOTEKOO Wireless Network Card Adapter WiFi Dongle for Desktop Laptop PC](https://www.amazon.com/LOTEKOO-150Mbps-Adapter-Wireless-Raspberry/dp/B06Y2HKT75)

Amazon - $12 USD - [Wireless WiFi USB Dongle Stick Adapter RT5370 150Mbps](https://www.amazon.com/Wireless-Adapter-150Mbps-Set-Top-Raspberry/dp/B01KWQAQ00)

AliExpress - [AliExpress has many links to adapters based on the rt5370 chipset](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20211217111156&origin=y&SearchText=rt5370+usb+wifi+adapter)

Note: The above link will show many adapters. Ensure you check to make sure the adapter is based on the rt5370 chipset.

-----

##### ```chipset -  Mediatek mt7601u``` - N150 - USB 2 - supported in-kernel since Linux kernel 4.2 (2015)

Note: the mt7601u chipset only supports managed and monitor modes (no AP mode and monitor mode does not support
packet injection).

Note: I own one or more adapters based on the mt7601u chipset. Feel free to ask questions.

Amazon - $7 USD - [EDUP MS8551 USB WiFi Adapter for PC - High Gain 6dBi Antenna](https://www.amazon.com/gp/product/B0827LG8L2)

Review by Nick: I own this EDUP adapter and run it with Linux. I consider this adapter to be a very dependable long range adapter. The antenna on this
adapter can only fold 90 degrees but cannot rotate which can be a little annoying depending on how you use it .

Amazon - $9 USD - [Mini 150m USB Wifi Wireless Network Card](https://www.amazon.com/Wireless-Network-802-11-Adapter-Antenna/dp/B008Z9IZSW)

Amazon - $7 USD - (nano) [Zibo Mini USB Wifi Wireless Adapter, 150Mbps](https://www.amazon.com/Zibo-Wireless-Adapter-150Mbps-Supports/dp/B00RBBUQLE)

Amazon - $4 USD - (nano) [MTK7601 Mini 150Mbps USB WiFi Adapter](https://www.amazon.com/Adapter-Dongle-MTK7601-150Mbps-Wireless/dp/B07YQDLHQJ)

Note: The above adapter is shipped from an overseas location. You can tell by looking at the delivery dates. This does not always work well. Use caution. 

AliExpress - [AliExpress has many links to adapters based on the mt7601u chipset](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20220601173555&SearchText=mt7601+usb+wifi+adapter&spm=a2g0o.productlist.1000002.0)

Note: The above link will show many adapters. Ensure you check to make sure the adapter is based on the mt7601u chipset.

-----

##### ```chipset - Atheros ar9271 [2]``` - N150 - USB 2

Note: Production of the ar9271 chipset ended during 2021. There are still new adapters for sale for now.

Note: I own one or more adapters based on the ar9271 chipset. Feel free to ask questions.

```
=====> ALFA AWUS036NHA <=====
```
![image](https://user-images.githubusercontent.com/69053122/132881997-c6f89f85-4505-4154-a711-a08796b527a7.png)

Rokland - $27 - [ALFA AWUS036NHA Atheros AR9271 802.11n WIRELESS-N USB Wi-Fi adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036nha-802-11n-wireless-n-usb-wi-fi-adapter-2-watt) - Info: free shipping and no tax outside of Florida. Ships to Canada and US. I have read many positive comments from Linux users about this adapter.

ebay - $27 - [ALFA AWUS036NHA 802.11n Wireless-N Wi-Fi USB Adapter High Speed Atheros AR9271](https://www.ebay.com/itm/ALFA-AWUS036NHA-802-11n-Wireless-N-Wi-Fi-USB-Adapter-High-Speed-Atheros-AR9271/380458349886?epid=1600491254&hash=item589515b53e:g:zW8AAOSwnCFaQ9Oe) - I have read many positive comments from Linux users about this adapter.

AliExpress - $15 USD - [CHANEVE Atheros AR9271 Chipset 150Mbps Wireless USB WiFi Adapter 802.11n Kali Linux](https://www.aliexpress.com/item/4000947646485.html)

Amazon - $49 USD - [WiFi Nation WN-H3 USB WiFi Antenna 802.11n, Speed: 150Mbps, Freq. 2.4GHz and 5dBi Antenna, chipset: Atheros AR9271](https://www.amazon.com/WiFi-Nation-Antenna-802-11n-Speed/dp/B08D7S3GL9)

-----

##### ```chipset - Mediatek/Ralink rt3070 (Mediatek bought Ralink a few years ago)``` - N150 - USB 2

Note: Production of the rt3070 chipset ended during 2021. There are still new adapters for sale for now.

Note: I own one or more adapters based on the rt3070 chipset. Feel free to ask questions.

Amazon - $15 USD - [Panda Long Range 150Mbps Wireless N USB Adapter w/High Gain Antenna - PAU08](https://www.amazon.com/Panda-150Mbps-Wireless-Adapter-Antennas/dp/B004AC6X0K)

Review by Nick: The PAU08 has very long range and is capable of handling more than 32 clients. I am aware of users that have used this adapter for AP mode for situations where support for many IoT clients is required and it worked well.

Amazon - $13 USD - [Deal4GO RT3070 802.11n 150Mbps Wireless USB WiFi Adapter WLAN w/ YP243433 Power Amplifier for Ralink RT3070L WiFi Module Kali Linux Ubuntu ](https://www.amazon.com/dp/B086D72XR6)

Amazon - $8 USD - [Deal4GO RT3070 802.11n 150Mbps Wireless USB WiFi Adapter for Ralink RT3070 WLAN Card Kali Linux Ubuntu Windows CE 5.0/6.0 Archlinux manjaro](https://www.amazon.com/gp/product/B08QZDGWJC)

Amazon - $10 USD - [Panda Mini WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Mini-150Mbps-Wireless-Adapter/dp/B003283M6Q)

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
