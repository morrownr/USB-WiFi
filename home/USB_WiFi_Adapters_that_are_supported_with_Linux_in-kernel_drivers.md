## USB WiFi adapters that are supported with Linux `in-kernel` drivers

USB WiFi adapters that are supported with `in-kernel` drivers are plug-and-play with most desktop distros. Additional work may be required for server distros as the maintainers of server distros seem to think that there are ethernet cables everywhere a user may choose to locate a server. Linux `in-kernel` drivers are preferable over `out-of-kernel` drivers for most users and use cases as problems with locating, installing and maintaining drivers are dramatically reduced allowing for a better experience.

Note: All USB WiFi adapters listed here are single-state (no Windows driver inside), single-function (no Bluetooth support) and use in-kernel drivers (Plug and Play). Buying adapters that meet this criteria greatly increases the probability of a satisfying experience that should last for many years.

-----

Recent changes:

- 2023-10-15 - checked and updated adapter links and prices.
- 2023-09-21 - added Fenvi FU-AX1800 (AXE3000) to mt7921au chipset section. 
- 2023-07-05 - added ALFA AWUS036AXM (AXE3000) to mt7921au chipset section.
- 2023-05-18 - added ALLNET ALL-WA1200AC (AC1200) to mt7612u chipset section.
- 2023-05-17 - updated ALFA AWUS036ACU (AC1200) to rtl8812bu chipset section.
- 2023-04-10 - added BrosTrend AC3L (AC1200) to rtl8812bu chipset section.
- 2023-03-05 - deleted some old adapters that were overpriced.
- 2023-02-15 - added Panda PAU0B (AC600) to the mt7610u chipset section.
- 2023-02-01 - added ALFA AWUS036AXML (AXE3000) to mt7921au chipset section.
- 2023-02-01 - added Netgear A8000 (AXE3000) to mt7921au chipset section.
- 2023-02-01 - decided to only add single-state, single-function adapters going forward.

-----

Important: Price and availability of listed adapters is subject to change. Updating the list of adapters does take a considerable amount of time. I try to complete a review of the links at least once ever two months. This site has increased in popularity to the point that readers of this site may cause inventory problems for some sellers at times so you may need to wait for inventory to be refreshed. To help with this problem, I have listed multiple links for some popular products. If you see any problems or see links that should be added or removed, please post in `Issues.`

Market Conditions: 2023-12-24 - Many good adapters are available. Prices for some adapters are still higher than before the pandemic but some adapters have returned to or are lower than pre-pandemic prices. There is a worldwide chip surplus currently. This should put downward price pressure on the cost of chipsets but lower prices may show up slowly as existing inventory has to work its way through supply chains. Most of you should be able to find something that meets your needs at a price you can afford if you shop around. Please take a look at the entire list and ask questions is `Issues`.

-----

### Tri Band USB WiFi Adapters that are supported with Linux `in-kernel` drivers

-----

#### AXE3000 - USB3.0 - 2.4 GHz, 5 GHz and 6 GHz (WiFi 6E)

-----

##### `chipset - Mediatek mt7921au - supported in-kernel since Linux kernel 5.18 (2022) (AP Mode support added in kernel 5.19) (P2P Mode support added in kernel 6.4) - Filogic 330 - abgn+ac+ax - 2x2:2 - Wi-Fi 6E, WPA3, OFDMA, Zero DFS, BT 5.2, MU-MIMO, 1024QAM, HE80, LNA/PA, ESR`

Info: It is necessary to add additional information in this section before listing the adapters because the driver, firmware and adapters are relatively new to the market and there are things that Linux users need to know.

Info: Be aware that the range of the 6 GHz band has been reduced compared to the 5 GHz band. So, while 6 GHz may have a big pipeline, it will have less range than 5 GHz. Another issue you need to be aware of is that wifi routers vary in how they handle clients. It is best that you pick a wifi AP/router that gives you the ability to set different names for all 3 bands so that you can control which band you are connected to. Checking the throughput of each band will allow you to see where your best performance is. Testing different channels in your AP/router can also help you find where your best performance is.

Status: USB adapters featuring the mt7921au chipset have been available since July 2022. `Adapters based on the mt7921au chipset should not be considered plug and play` unless you are using a distro using kernel 5.19 or later such as Ubuntu 22.10+. `If you are not technically inclined and want a plug and play adapter for an older distro, continue on down this list to see adapters that are currently plug and play with almost all popular non-server distros. This includes adapters starting at the AC1200 section` Remember that server distros think the entire world has cabled ethernet connections. You can add wifi support to server distros. Check with your distro doumentation or support forums for more information.

What are the kernel versions you should know about?

- Minimum kernel for managed (client) and monitor modes= 5.18
- Minimum kernel for master (AP) and AP/VLAN modes = 5.19
- Minimum kernel for P2P mode = 6.4
- Minimum kernel for mesh point and IBSS modes = not yet


Note: The mt7921au driver must include the VID/PID that your adapter uses in order for the adapter to be plug and play per the above guidance. Adapter makers may use custom company VID/PID numbers. If this is the case, a patch needs to be submitted to the `linux-wireless` list in order for the VID/PID to be merged into the mainline kernel. An example of this situation currently is the Netgear A8000 adapter. For more information and a temporary workaround, see the section about the Netgear A8000 below.

The driver (module) for the mt7921au chipset is called mt7921u.ko.  You can check on the driver by going to the following location:

```
cd /usr/lib/modules/$(uname -r)/kernel/drivers/net/wireless/mediatek/mt76/mt7921

```
Show the files:

```
ls -l

```

The file you are looking for is mt7921u.ko

Note about OpenWRT: There is an exception to the above for OpenWRT. MT7921u has been backported to the kernel (5.10) used in OpenWRT 22.03.x. Starting with OpenWRT 22.03.3, simply install the following package:

```
kmod-mt7921u
```

Another note about OpenWRT 22.03: Luci supports WiFi 6 (AX) configuration and it works well. OpenWRT 23.05 was recently released and appears to support WiFi 6e. Your success with the 6 Ghz band is dependent on the rules and regulations in the country that you live in. Many countries have yet to pass laws authorizing the 6 Ghz band.

Remember that in-kernel drivers in Linux come in 2 or more parts. There is what is normally called the driver, which is part of the kernel, and the firmware, which may be 1 or more files, is not part of the kernel. Firmware files are part of the distro and have to be installed and updated by the maintainers of your distros or by you. Some distros do not install firmware, Debian, prior to version 12, is an example. Therefore you may to need to install the firmware yourself depending on your Linux distro. You can check the [firmware](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Install_Firmware_for_Mediatek_based_USB_WiFi_adapters.md) . see section 2, to see if firmware needs to be installed or upgraded. Keep in mind that firmware file names do not change so you have to compare file sizes, dates or version to determine if you have the latest version. The symptom of a missing firmware is that the adapter does not show up on boot... just like if there is no driver in your kernel. To repeat, adapters that use in-kernel drivers, to function properly, the driver (module) is required AND the firmware is required. The absence of either will cause the adapter to not show up on boot. All of the more popular mainstream desktop have everything in place. This includes but is not limited to current releases of Ubuntu (and all of its puppies), Debian, fedora, Manjaro, Raspberry Pi OS and many more.

```
>================================<
>=====>  ALFA AWUS036AXM <=======<
>================================<
```

![image](https://github.com/morrownr/USB-WiFi/assets/69053122/0b5c04bf-28cf-47f2-8dba-dd168b8fe27d)

```
Note: This adapter is a single-state adapter.
Note: This adapter uses the mt7921aun chipset.
Note: This adapter uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
```

Rokland - 59 USD - [ALFA AWUS036AXM WiFi 6E 3000 mbps Tri Band 2.4/5/6 GHz WiFi USB Adapter](https://store.rokland.com/collections/wifi-6-6e/products/alfa-awus036axm-wifi-6e-3000-mbps-tri-band-2-4-5-6-ghz-wifi-usb-adapter)

Varia - 31 plus shipping EUR - [ALFA AWUS036AXM WiFi 6/6E, 2x2 Tri-band](https://www.varia-store.com/en/suche/search-ALFA%20AWUS036AXM.html)

Please help me to add additional links to sellers of this adapter around the world.

Review: Pending. If you have this adapter, please submit a review.

```
>================================<
>======>  Netgear A8000  <==-====<
>================================<
```

![A8000_Gallery-1_FINAL-2022-NEW_tcm148-143396](https://user-images.githubusercontent.com/69053122/214127798-ecd6e225-bd8b-4292-a18f-f4c458997f28.jpg)


```
Note: This is a single-state adapter. The Windows driver is supplied on a small flash drive.
Note: This adapter uses the mt7921aun chipset.
Note: This adapter does not use the standard Mediatek device ID (VID/PID) for the mt7921au chipset. See below.
```

Amazon - 79 USD [NETGEAR Nighthawk WiFi 6E USB 3.0 Adapter (A8000) | AXE3000 Tri-Band Wireless](https://www.amazon.com/gp/product/B0B94R78N7)

Walmart - 79 USD [NETGEAR Nighthawk AXE3000 WiFi 6E USB 3.0 Adapter (A8000-100PAS)](https://www.walmart.com/ip/NETGEAR-Nighthawk-AXE3000-WiFi-6E-USB-3-0-Adapter-A8000-100PAS/1457856595)

Netgear - 89 USD -[AXE3000 USB 3.0 WiFi Adapter -A8000](https://www.netgear.com/home/wifi/adapters/a8000/)

Please help me to add additional links to sellers of this adapter around the world.

Important: The Netgear A8000 uses a device ID (VID/PID) that is scheduled to go into Linux kernel 6.4. This adapter will not be plug and play on earlier kernels. There are two methods for users that want the adapter to work with kernels that do not have the VID/PID included yet.

Method 1: Hotplug automation using udev.

Create a file called `/etc/udev/rules.d/90-usb-0846:9060-mt7921u.rules`

$ sudo nano /etc/udev/rules.d/90-usb-0846:9060-mt7921u.rules

Note: you can change `nano` to the text editor of your choice in the above command.

Copy the below lines and paste them into the above file that you are creating:

```
ACTION=="add", \
	SUBSYSTEM=="usb", \
	ENV{ID_VENDOR_ID}=="0846", \
	ENV{ID_MODEL_ID}=="9060", \
	RUN+="/usr/sbin/modprobe mt7921u", \
	RUN+="/bin/sh -c 'echo 0846 9060 > /sys/bus/usb/drivers/mt7921u/new_id'"
```

Save file and reboot.

Method 2: From a terminal, enter and execute the following commands:

```
su
modprobe mt7921u
echo 0846 9060 > /sys/bus/usb/drivers/mt7921u/new_id
```

Be aware that method 2 will need to be executed after each reboot.

Review by [russeree](https://github.com/russeree) 2.4/5GHz Tested - 6GHz untested.

The Good:
- Reliability: 2.4/5 GHz modes have not dropped a connection or needed to be reset after days of use.
- Speeds: At a distance of ~75 feet getting.
  - ~300mb/s down
  - ~400mb/s up
- Latency: Consistent at ~5ms
- Temps: Device runs cool to the touch. Would not be considered hot or even warm.
- Size: The device, given it's performance, is quite compact.
- Packing: Minimal packing, good for the environment.
- Aesthetics: The new, applied-polished Netgear logo is visually pleasing.

The Bad:
- Not PnP yet: A PATCH is scheduled to go into kernel 6.4. (Editor's note: the patch was merged in kernel 6.4.)
- Cost: At $99 USD MSRP this adapter is not inexpensive. (Editor's note: the price has been falling)
- Packing: Minimal for the cost, unboxing is underwhelimg.

```
>================================<
>=====>  ALFA AWUS036AXML  <=====<
>================================<
```

![image](https://user-images.githubusercontent.com/69053122/214129007-b58bd915-57e2-4465-afc5-37ae1a0c80a2.png)


```
Note: This adapter is a single-state adapter.
Note: This adapter uses the mt7921aun chipset.
Note: This adapter uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
```

Rokland - 80 USD - [ALFA AWUS036AXML 802.11ax WiFi 6 1800 mbps Tri Band WiFi USB Adapter w Bluetooth](https://store.rokland.com/collections/wifi-6-6e/products/alfa-awus036axml-802-11ax-wifi-6-1800-mbps-tri-band-wifi-usb-adapter-w-bluetooth)

Video 1 - [Video from Rokland](https://www.youtube.com/watch?v=KkcKSuGn4gw)

Video 2 - [Video from Rokland](https://www.youtube.com/watch?v=_PcuRDY4Jic)

Amazon - 80 USD - [ALFA AWUS036AXML 802.11axe WiFi 6E USB 3.0 Adapter AXE3000, Tri Band 6 GHz, Gigabit Speed up to 3Gbps](https://www.amazon.com/ALFA-AWUS036AXML-802-11axe-Adapter-AXE3000/dp/B0BY8GMW32)

ebay - 80 USD - [ALFA AWUS036AXML 802.11axe WiFi 6E USB 3.0 Adapter AXE3000, Tri Band 6 GHz](https://www.ebay.com/itm/134613987799)

Varia - 47 plus shipping EUR - [AWUS036AXML - WiFi 6+BT5.2 , 2x2, WLAN USB adapter](https://www.varia-store.com/en/suche/search-AWUS036AXML.html)

Please help me to add additional links to sellers of this adapter around the world.

Note: Contact [Alfa](https://www.alfa.com.tw/) for information about Alfa dealers near you.

Review of user comments by @morrownr : User reports so far are positive with the exception of one user finding a driver error in AP mode but he has submitted a PATCH to correct the situation. One of the advantages this adapter and the Alfa AXM adapter has over the other listed adapters in this section is that it has removable antennas which allow users to install directional antennas for longer range if so desired. Rokland keeps directional antennas for this adapter in stock. This adapter also appears to have no thermal issues at all and it has a VERY NICE extension cable that can plug into USB3-A and USB3-C ports.

```
>================================<
>=====>  COMFAST CF-953AX  <=====<
>================================<
```

![CF-953AX](https://user-images.githubusercontent.com/69053122/180594207-e3ee44ec-aac0-4c75-bd01-09454184bc57.jpg)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7921au chipset.
Note: Some versions of this adapter use the standard Mediatek device ID (VID/PID) and some do not. See below.
```

AliExpress - normally 21 USD but currently on sale - [COMFAST CF-953AX](https://www.aliexpress.com/item/3256804283254522.html)

Please help me to add additional links to sellers of this adapter around the world.

Important: Users have reported that some CF-953AX's (and CF-952AX's) come with a Device ID (VID/PID) of 3574:6211 and some come with the VID/PID provided by Mediatek, which is 0e8d:7961. You can check the VID/PID as follows:

```
$ lsusb
```

A PATCH was submitted and included in a recent Linux kernel (6.3). Said PATCH adds the 3574:6211 VID/PID so as to eliminate this issue. If your adapter is not plug and play, see below.

Method 1: Hotplug automation using udev.

Create a file called `/etc/udev/rules.d/90-usb-3574:6211-mt7921u.rules`

$ sudo nano /etc/udev/rules.d/90-usb-3574:6211-mt7921u.rules

Note: you can change `nano` to the text editor of your choice in the above command.

Copy the below lines and paste them into the above file that you are creating:

```
ACTION=="add", \
	SUBSYSTEM=="usb", \
	ENV{ID_VENDOR_ID}=="3574", \
	ENV{ID_MODEL_ID}=="6211", \
	RUN+="/usr/sbin/modprobe mt7921u", \
	RUN+="/bin/sh -c 'echo 3574 6211 > /sys/bus/usb/drivers/mt7921u/new_id'"
```

Save file and reboot.

Method 2: From a terminal, enter and execute the following commands:

```
su
modprobe mt7921u
echo 3574 6211 > /sys/bus/usb/drivers/mt7921u/new_id
```

Be aware that method 2 will need to be executed after each reboot.

Review by @rop12770:

Bought 2 of these as "recommended" by @morrownr, and even without my router is WIFI 6 (yet), the speed went from a usual 100/120 down and 50/60 up, to 240 down/120up. Amazing card!! Thanks for the recomendation!

Editor's note regarding the above review: The mt7921au chipset is very fast in AC/5 GHz so even without a WiFi 6 capable router, you can see big increases in 5 GHz band speed. Your actual results will vary according to the amount of congestion, distance from router and various other factors such as the capabilities of your AP/router. 

Overall, so far, comments from owners of this adapter seem to be generally positive. It likely has a little better range than the Comfast CF-951AX that I own due to the external antennas but range is likely not above average. Most users indicate bluetooth does not work but this may be because Comfast intentionally turned it off. Adapter makers are free to turn on and off any capabilities of the chipset so even though the chipset supports bluetooth, makers may turn it off. Historically, multi-function (wifi and bt) adapters are limited to USB2 because USB3 cables, wiring and connections emit radio energy in the 2.4 GHz frquency range that can and will interfere with bluetooth so, unless an engineer has found a solution, if an adapter says is wifi and bt capable, you can expect wifi to be limited to USB2. This is likely the reason that adapters makers so far have been turning off bluetooth. And I agree with them. This chipset should not be limited to USB2 capability for WiFi as it would dramatically lower speeds.

```
>================================<
>=====>  Fenvi FU-AX1800 <=======<
>================================<
```

![image](https://user-images.githubusercontent.com/797782/269444432-5d37d032-8b9b-498a-a4a9-fb135a9194b3.jpg)

```
Note: Single-state adapter.
Note: Uses the mt7921au chipset.
Note: Uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961

```

AliExpress - (cheap) - [FENVI 1800Mbps WiFi 6 USB Adapter Dual Band 2.4G/5Ghz Wireless WiFi Receiver USB 3.0 Dongle](https://www.aliexpress.us/item/3256805749323751.html?gatewayAdapt=glo2usa4itemAdapt)

Please help me to add additional links to sellers of this adapter around the world.

Review by @karimHI :

```
ID : ID 0e8d:7961 MediaTek Inc. Wireless_Device
It is plug and play in kali but in windows, no, it comes with a small cd with the driver on it
Does it have good range? : Medium
Where did you order it : aliexpress / Any problems? : no
Thermal problems? : from the adapters I tested before, this is the coolest one. I was surprised.
Is it fast / what bands ? : everything is good and at described in the box (2.4ghz/5.0ghz).
Distro: kali 2023.3
Kernel : 6.5.0-kali2-amd64
Does it work with extension cable : yes, I'm using it with 2 extensions hub.
Cost? : 10$
What modes have you tested? : I have tested managed - ap/vlan - monitor everything is good.
* managed
* AP
* AP/VLAN
* monitor
* P2P-client
* P2P-GO
```

```
>================================<
>=====>  COMFAST CF-951AX  <=====<
>================================<
```

Maintained by @morrownr

![CF-951AX](https://user-images.githubusercontent.com/69053122/185668163-91e6df3c-7e39-45a7-885b-2f36b8b61873.jpg)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7921au chipset.
Note: This adapter uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
```

AliExpress - $17 USD - [COMFAST CF-951AX Wifi 6 USB Adapter 802.11AX](https://www.aliexpress.com/item/3256804245691865.html)

BadgerWiFi - $28 Pounds - [COMFAST CF-951AX](https://www.badgerwifi.co.uk/store/p/cf-951ax)

Review: I have been using the CF-951AX for nearly a year now. I have good things to say about the mt7921au chipset and the mt7921u in-kernel driver.

The good:

- The mt7921au chipset seems to be very good.
- Did I mention that this chipset is fast? WiFi 5 = around 625 to 650 Mb/s in my testing.
- The mt7921u in-kernel driver is very stable.
- I have tested 5 GHz band managed mode, AP mode and monitor mode with very good results.
- I have tested WiFi 6 support for managed mode, AP mode and monitor mode with very good results.

The bad:

- This adapter will not work with any of the USB3 extension cables or powered USB3 hubs that I have. The cause is unknown. It will work with usb right angle adapters.
- The case of the adapter is too wide. If you plug it directly in a usb port on a Raspberry Pi, there is no way to use the port to the side. I use a usb right angle adapter to handle this problem.

-----

### Dual Band USB WiFi Adapters that are supported with Linux `in-kernel` drivers

-----

#### AC1200 / AC1300 - USB 3 - 2.4 GHz and 5 GHz (WIFI 5)

-----

##### `chipset - Mediatek mt7612u - supported in-kernel since Linux kernel 4.19 (2018)` - [mt7612u info](https://github.com/morrownr/7612u)

```
>===============================<
>=====>  ALFA AWUS036ACM  <=====<
>===============================<
```

Maintained by @morrownr

![image](https://user-images.githubusercontent.com/69053122/127750949-809364a6-65ed-4c7c-9abe-4a77cb73848e.png)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
```

Important: If running this adapter with Kali in Virtual Box, here is a [Video](https://store.rokland.com/pages/alfa-awus036acm-kali-virtual-box-instructions) that should help.

Rokland - 43 USD - US - [ALFA AWUS036ACM 802.11ac Dual Band USB WiFi Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036acm-802-11ac-dual-band-2-4-5-ghz-wifi-usb-adapter) - Info: free shipping and no tax outside of Florida. Ships to Canada and US.

Amazon - 42 USD - US - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD)

<!-- markdown-link-check-disable-next-line -->
ebay - 41 USD - US - [Alfa AWUS036ACM 867Mbps Long Range Dual Band Wi-Fi USB Adapter](https://www.ebay.com/p/1738034359)

Amazon.it - 40 EUR - Italy - [Alfa AWUS036ACM](https://www.amazon.it/Alfa-AWUS036ACM/dp/B08BJS8FXD/ref=sr_1_9?__mk_it_IT=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=2G6VAKKHUQXQB&keywords=mediatek+wifi+adapter&qid=1650990071&sprefix=mediatek+wifi+adapter%2Caps%2C278&sr=8-9)

getic - 33 plus VAT EUR - Latvia - [Alfa USB Adapter AWUS036ACM](https://www.getic.com/product/alfa-awus036acm)

TUNG NETWORK TRADING - 220 RM - Malaysia - [Alfa AWUS036ACM 802.11ac Dual Band 2.4/5 GHz WiFi USB Adapter](https://www.alfa.net.my/webshaper/store/viewProd.asp?pkProductItem=70)

Varia - 43 EUR - Germany - [AWUS036ACM - 802.11ac Dualband-WLAN-USB-Adapter 2,4/5 GHz](https://www.varia-store.com/de/suche/search-AWUS036ACM.html)

Note: Contact [Alfa](https://www.alfa.com.tw/) for information about Alfa dealers near you.

[ALFA AWUS036ACM Technical information](https://github.com/morrownr/USB-WiFi/blob/main/home/iw_list/ALFA_AWUS036ACM.txt)

[ALFA Network Linux support for MT7612U based products](https://docs.alfa.com.tw/Support/Linux/MT7612U/)

Review by Nick - The Alfa AWUS036ACM is an excellent product. It is mid-priced, well made and works well in managed mode, master mode and monitor mode. It is a very solid, stable performer in 5 GHz AP mode. It supports 80 MHz channel width in AP mode and can sustain 400+ Mb/s as measured by iperf3. It runs cool and uses a maximum of only about 380 mA power when under heavy load. I use one in the wifi router/access point that I built. Works so well with the Raspberry Pi 4B, 3B+ and 3B, it is almost like it was designed specifically for that hardware. You really need to use it with a Raspberry Pi 4b so as to get the full througput capability. It works well with desktop systems (an extension cable is included in the packages most retailers of this product sell). It also works well with laptop systems. This adapter is a high quality product with good range and is plug and play in all of the modern distros of Linux. Highly recommended.

```
>===========================<
>=====>  Panda PAU0D  <=====<
>===========================<
```

![image](https://user-images.githubusercontent.com/69053122/201191537-8f7e093c-250f-4aca-bdf2-8470f0bf621d.png)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
```

Amazon - 31 USD - US - [Panda Wireless PAU0D AC1200 Wireless AC USB Adapter with High Gain Antennas](https://www.amazon.com/Panda-Wireless-AC1200-Adapter-Antennas/dp/B0B2QD6RPX)

Review: Pending. If you have this adapter, please write a review.


```
>=============================<
>==>  ALLNET ALL-WA1200AC  <==<
>=============================<
```

![image](https://github.com/morrownr/USB-WiFi/assets/69053122/481e3cf8-eaed-448d-bdb1-d8a2a426eac3)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
```

Amazon.de - 22 EUR - [Allnet ALL-NAS200 WA1200AC WLAN 1200MBIT/S Network Card](https://www.amazon.de/gp/product/B00UQSAV3M?smid=A3JWKAKR8XB7XF)

pollin.de - 21 EUR - [ALLNET WLAN-Stick ALL-WA1200AC, 1200 MBit/s](https://www.pollin.de/p/allnet-wlan-stick-all-wa1200ac-1200-mbit-s-741314)

Allnet - [ALLNET Wireless AC 1200Mbit USB 3.0 WLAN Stick Dongle ALL-WA1200AC](https://shop.allnet.de/netzwerk-aktive-komponenten/wireless-lan/wireless-lan-usb-adapter/261762/allnet-all-wa1200ac/1200mbit-wireless-ac-usb-3.0-dual-band-adapter)

Review: Pending

```
>=============================<
>=====>  TEROW ROW02CD  <=====<
>=============================<
```

![image](https://user-images.githubusercontent.com/69053122/127751374-7a814003-6ff5-4da6-8534-bdc61ea5f249.png)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
```

No links available at this time.

Warning: TEROW sells a TEROW ROW02FD that is a multi-state adapter. That is not what you want.

Warning: TEROW sells a TEROW ROW12CD that is reported to be based on a rtl8812bu chipset. That is not what you want.

Review by Nick - The TEROW ROW02CD works very well with the Raspberry Pi 4B, 3B+ and 3B. I have tested with various desktop and laptop systems. The TEROW ROW02CD is a single state adapter. The cost of this adapter is low. The performance and quality of the materials used and capabilities is not quite as good as the Alfa AWUS036ACM but that is to be expected since the Alfa AWUS036ACM is a more expensive, premium quality adapter. My experience is that this adapter will provide good stable performance and should meet the needs of most Linux users. In fact, during my testing, a TEROW ROW02CD outperformed in link quality and signal level vs. a similar adapter based on a rtl8812bu chipset when plugged into the same USB3 port and connected to the same wifi router.

```
>=================================<
>=====>  AVM FRITZ! AC 860  <=====<
>=================================<
```

Maintained by @mendel5

![Fritz-860](https://user-images.githubusercontent.com/69053122/193471131-931d28e0-0353-4d66-9732-99662b8f5c0c.jpeg)

```
Note: This is a hybrid-state adapter. It is multi-state but automatically changes state on its own.
Note: This adapter uses the mt7612un chipset.
```

Geizhals.eu - 34 EUR - [AVM FRITZ! AC 860](https://geizhals.eu/avm-fritz-wlan-usb-stick-ac-860-20002687-20002724-a1082383.html)

Amazon Germany - 36 EUR - [AVM FRITZ! AC 860](https://www.amazon.de/dp/B017BD21R8/)

Amazon France - 46 EUR - [AVM FRITZ! AC 860](https://www.amazon.fr/dp/B019E28V4G/)

Amazon Italy - 36 EUR - [AVM FRITZ! AC 860](https://www.amazon.it/dp/B019E28V4G/)

Review by mendel5 - The AVM FRITZ! AC 860 USB WiFi adapter is manufactured by the German company AVM which is well-known in Europe for its FRITZ! products, e.g. routers (FRITZ!Box), WiFi hardware, DECT phones, etc. The official name of this USB WiFi adapter is "AVM FRITZ!WLAN USB Stick AC 860".

The AVM AC 860 was unveiled in 2014 and has been available for purchase since 2015. The performance is advertised as 300 Mbit/​s for 2.4 GHz and 867 Mbits/​s for 5 GHz. The reception of this USB WiFi adapter is mostly good, however not outstanding because it does not have a large antenna unlike other USB WiFi adapters.

AVM has not disclosed any information about the chipset that is used in the AVM AC 860. On a few other websites (e.g. forums, wikis, etc.) it is stated that the AVM AC 860 uses a `mt7662u` chipset. However, the source for these claims is not known. My copy of the AVM AC 860 does not use a `mt7662u` chipset but a `mt7612un` chipset as indicated by the IC markings on my chip. There might be other versions of the AVM AC 860 that use a `mt7662u` chipset.

When analyzing the AVM AC 860 with Linux system tools (e.g. `lsusb`), there is unfortunately no information provided about the chipset that is used in this USB WiFi adapter. Due to the lack of information regarding the chipset from both AVM and `lsusb`, I had to break my AVM AC 860 open and analyze the markings on the chip (IC markings). The markings on the chip were obfuscated by being covered in a layer of black paint which I had to remove with chemicals. Only then it was revealed that my copy of the AVM AC 860 uses a `mt7612un` chipset.

The `usb_modeswitch` properties of the AVM AC 860 are unusual. When I open the file `/etc/usb_modeswitch.conf`, set `DisableSwitching=1` and plug my AVM AC 860 into my Linux computer, a flash drive is opened where I can see the Windows drivers of this USB WiFi adapter. Then after 3-5 minutes the flash drive automatically ejects itself from my computer and the WiFi functionality starts working. So, at first it appears that the AVM AC 860 is a multi-state adapter but then it automatically switches to the WiFi state. Therefore, it can be described as being a multi-state adapter that has been configured to resemble a single-state adapter. It is recommended to set `DisableSwitching=0` for the adapter to be used easily as a plug-and-play device on Linux systems.

To summarize, it appears that AVM has unfortunately modified the `mt7612un` chipset of the AVM AC 860 heavily compared to the chipset's original condition:
1. The chipset information that is accessible through Linux system tools (`lsusb`) does not include the name of the chipset.
2. The IC markings on the chip have been covered in black paint to hide the name of the chipset.
3. The chipset has a weird single-state configuration that appears to be multi-state at first but after approx. 5 minutes the USB WiFi adapter starts working even if `DisableSwitching=1` is set.

Given the obfuscation in both (1) the software and (2) the hardware as well as (3) the unusual single-state / multi-state configuration, I would recommend that people who are interested in the AVM AC 860 question whether the properties of the AVM AC 860 that are described in this review are acceptable for its planned use.

People who are interested in buying the AVM AC 860 could (and should) consider other USB WiFi adapters that operate as a normal single-state adapter, that have less obfuscation about the chipset and that have a larger antenna and therefore stronger reception.

```
>=============================<
>=====>  Netgear A6210  <=====<
>=============================<
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/127751480-4c34f5d7-3e7e-47ad-baab-aa5bad62c6bb.png)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
```

Walmart - 36 USD - [NETGEAR - AC1200 Dual-Band USB 3.0 WiFi Adapter (A6210-10000S)](https://www.walmart.com/ip/NETGEAR-AC1200-Dual-Band-USB-3-0-WiFi-Adapter-A6210-10000S/106539212?a)

ebay - 36 USD - [NETGEAR AC1200 USB 3.0 Wi-Fi Adapter - A6210-10000S](https://www.ebay.com/p/18021987463)

Review by Nick - The Netgear A6210 is an adapter that is designed to be portable. I rate the range of this adapter to be average as far as small adapters with no external antenna go so if you need a long range adapter, look elsewhere. On the other hand, if range is not an issue, this adapter is easy to pack and take on the road. It comes with a good quality USB3 extension cable plus cradle. It is a stable performer. I have noted that it runs a little warm which is unusual for Mediatek chipset based adapters. Users looking for a portable AC1200 adapter that uses an in-kernel driver and has good performance over short to medium distances should be happy with this adapter. Note: Due to the somewhat limited range of this adapter, I do not recommend it for use in AP mode unless your requirement is only for same room connections. I also do not recommend this adapter for security analysis/pen testing because of the limited range.

To be clear: This adapter can provide good throughput. Here is a sample from iperf3:

```
Bitrate
  366 Mbits/sec                  sender
  365 Mbits/sec                  receiver

```

This test was conducted in client mode at a distance of about 5 meters with 2 walls between the adapter and wifi router. The test was on 5 GHz on a clean DFS channel. This test shows that this adapter can certainly provide AC1200 performance and it is a good adapter to take on the road. It does not have long range so use as an AP should be limited to same room or short distance and monitor mode performance is not going to let you reach out long distances. It appears the twpower is fixed on this adapter at 18 dBm. I am posting this additional paragraph because a user expressed some displeasure at not being able to get this adapter to do what he wanted. My suggestion is that anyone that is not sure of what you need, go to `issues` and ask.

-----

##### `chipset - Realtek rtl8812bu - supported in-kernel since Linux kernel 6.2 (2023)`

Note: While Linux kernel 6.2 does contain an in-kernel driver for this chipset, performance is not that good until kernel 6.4 and later. I have tested with 6.4 and 6.5 and I think performance is good now, not quite a good as the out-of-kernel driver yet, but good. Some users may decide to use the out-of kernel driver located here at this site for now as it is very good for an out-of-kernel driver:

[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

Important: The in-kernel driver and out-of-kernel drivers are not feature equal. Post in Issues if you have questions about what features are supported in which driver.

```
>============================<
>====> ALFA  AWUS036ACU <====<
>============================<
```

![image](https://user-images.githubusercontent.com/69053122/218380076-23fdfcc2-ec1c-4037-bed0-a0b24d3d7a7b.png)

Rokland - 22 USD - [ALFA AWUS036ACU (single-state, single-function)](https://store.rokland.com/collections/802-11ac-wi-fi-clients-receivers/products/alfa-awus036acu-802-11ac-ac1200-dual-band-wifi-usb-dongle-rp-sma-antennas)

Review by @morrownr : I now have this adapter and am slowly testing it. I'll go ahead and give my thoughts so far: This adapter is much smaller than most "football goal" style adapters and it is stylish (cute). The quality appears to be well above average. It is showing an average of 525 Mbps in managed mode testing with iperf3 and 435 Mbps with the in-kernel driver (kernel 6.4). Testing was accomplish on channel 100 DFS (no other APs on the channel) and distance of about 10 meters with 3 walls. Extended iperf3 testing results is less than average heat buildup and the single most impressive thing is the range. This is not called a "High "Power" or "Max Power" adapter as Alfa likes to call its extended range adapters, but it has excellent range. So far, this adapter has exceeded my expectations. Antennas are removable. No extension cable/stand is included.

Overall: If you are looking for a rtl8812bu based adapter that has good performance and excellent range, this adapter should be work well for you.

```
>==========================<
>====> BrosTrend AC3L <====<
>==========================<
```

![image](https://user-images.githubusercontent.com/69053122/231029660-be9a8d62-90a3-4c42-9f7c-9fbc82b74a38.png)

BrosTrend - $41 USD - [BrosTrend AC1200 Linux Compatible USB WiFi Adapter - AC3L](https://www.brostrend.com/collections/linux-wifi-adapter/products/ac3l)

Review by @morrownr : This adapter has performed very well. It is a single-state, single-function adapter, which is what we want.

Good:

- It is fast. I have consistently measured around 545 Mbps (clean DFS channel) using iperf3 with the [out-of-kernel driver](https://github.com/morrownr/88x2bu). Testing with the in-kernel driver in kernel 6.3 as of 2023-04-10 shows an iperf3 score of 410 Mbps. The in-kernel driver appears to be stable at this point and the performance is reasonably good. Optimizations continue to be merged.

- The adapter comes with a nice extension cable/stand. One of the best designs that I have used.

- The quality seems to be above average.

- The antennas are removable so you can use replacement directional antennas if you want and the ability to move the antennas to the position you want is good.

Average:

- Thermal characteristics are average as the adapter will become warm to the touch if running iperf3 for an extended period of time. There are no slits or holes to help with heat during heavy use. This should not be a problem for most use cases as my testing in this regard is torture. I would prefer to see slits or small holes to allow for some airflow.

Bad:

- Official website states it does not yet support the OpenWRT platform.

Overall: If you are looking for a rtl8812bu adapter that has very good performance, this adapter should be on your short list.

-----

#### AC580 / AC650 - USB 2 - 2.4 GHz and 5 GHz (WIFI 5)

-----

##### `chipset - Mediatek mt7610u - supported in-kernel since Linux kernel 4.19 (2018)`

```
>============================<
>====> ALFA AWUS036ACHM <====<
>============================<
```

![image](https://user-images.githubusercontent.com/69053122/129494292-e3e363ed-8119-4ab5-97cb-13018710a289.png)

Note: This adapter looks like a basic everday wifi adapter but it is not! I have tested many adapters and this adapter has the longest range of any modern dual band adapter that I have tested. If you need long range or an adapter that can run 24/7/365 and never miss a beat, this adapter is worth a look. Don't buy it for speed as it is a AC600 adapter, but if looking for range, great AP mode support, great monitor mode support and reliability, take a look.

Rokland - $40 USD - [ALFA AWUS036ACHM 802.11ac Dual Band High Power Mediatek MT7610U WiFi USB Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036achm-802-11ac-dual-band-high-power-ac1200-mediatek-wifi-usb-adapter)

ebay - $42 USD - [Alfa AWUS036ACHM 802.11ac dual band High Power Wi-Fi USB Adapter +RP-SMA antenna](https://www.ebay.com/itm/265323549415)

Amazon - $40 USD - [Alfa AWUS036ACHM 802.11ac WiFi Range Boost USB Adapter](https://www.amazon.com/AWUS036ACHM-802-11ac-Range-Boost-Adapter/dp/B08SJBV1N3)

ebay - $44 USD - [Alfa AWUS036ACHM 802.11ac dual band High Power Wi-Fi USB Adapter +RP-SMA antenna](https://www.ebay.com/itm/383907328953?epid=22045834288&hash=item5962a8f3b9:g:JiEAAOSwbatgBI-l)

TUNG NETWORK TRADING - 210 RM - Malaysia - [Alfa Network AWUS036ACHM 802.11ac WiFi USB Adapter](https://www.alfa.net.my/webshaper/store/viewProd.asp?pkProductItem=83)

[ALFA AWUS036ACHM Technical information](https://github.com/morrownr/USB-WiFi/blob/main/home/iw_list/ALFA_AWUS036ACHM_mt7610u.md)

[ALFA Network Linux support for MT7610U based products](https://docs.alfa.com.tw/Support/Linux/MT7610U/)

Review by Nick - The Alfa AWUS036ACHM is a good product. It is mid-priced, well made, runs cool, has EXCEPTIONAL range and works well in managed mode, master mode and monitor mode. I have recently been testing master (AP) mode: This adapter is exceptional in 2.4 GHz AP mode and good in 5 GHZ AP mode. The range in both bands exceeds the wifi router that I tested it against and I consider that wifi router to have good range. One thing to consider regarding 5 GHz AP mode is that this is an AC600 device so maximum transfer rate is limited to 433 Mb/s. That is fast enough for most use cases and will be for a long time but it is not as fast as you can get from an AC1200 adapter. This adapter shows good link quality and signal level even in difficult situations where other adapters would drop the connection. My testing shows that this adapter has the longest range of any current dual band consumer grade adapter that Alfa sells and Alfa is known for their long range products. My opinion is that this adapter is the single best adapter available for use with Kali Linux or other distros used for pen testing and security analysis. Compared to the Alfa AWUS036ACH, the Alfa AWUS036ACHM has better range, costs less and is supported with in-kernel drivers making it the better choice for Linux users. It comes with the required USB2 cable and a clip that allows you to mount the adapter in various locations. Overall, the Alfa AWUS036ACHM is a solid performer. Highly recommended.


```
=====> PANDA - PAU0B <=====
```

![Panda0B](https://user-images.githubusercontent.com/69053122/219270466-d7e64f57-c0da-4dea-bf59-f9c58b532e59.png)

Amazon - $30 USD - [Panda Wireless® PAU0B AC600 Dual Band (2.4GHz and 5GHz) Wireless USB Adapter W/ High Gain Antenna - Mint, Ubuntu, openSUSE, Fedora, Centos, Kali Linux and Raspberry PiOS](https://www.amazon.com/dp/B08NPX2X4Z/?tag=pandaw-20)

Review pending. Please suubmit a review if you own this adapter. The reviews on Amazon are very favorable.

```
=====> ANDDEAR - MT761003 <=====
```

![76-new](https://user-images.githubusercontent.com/69053122/132886023-58a44509-1d65-4de7-96fe-803064631301.jpg)

AliExpress - $11 USD - [ANDDEAR - MT761003](https://www.aliexpress.com/item/4000079918154.html)

Review by amisix - This adapter is $12 as of 2022-04-22. It is size (2.25" x 1" x .3"). It consumes less power than many adapters (~110mA/idle, 150mA-230mA/at load). The ANDDEAR-MT761003 is only an AC600 adapter (150N/433AC) although it performs quite well in real-world usage, has a medium transmission distance, and when running casual internet speed tests it easily achieved 100Mbps - the maximum speed of my ISP. It has an excellent Mediatek chipset that is highly capable with AP, monitor mode, and packet injection and the drivers are included in kernel so it just works. Overall I highly recommend the ANDDEAR-MT761003 if you're looking for something that's highly capable and you need qualities other than raw speed.

Important: ANDDEAR also makes an AC1200 version of this adapter that uses a mt7612u chipset. Avoid it. In testing, it was found to have a bug that generally shows in USB3 ports if port 1 is used. The conclusion of the testers is that the mt7612u chipset version of this adapter should be avoided as no workaround or fix could be identified. However, the above listed adapter based on the mt7610u chipset does not show this critical bug and should work well for you.

--- Links to additional adapters that are based on the mt7610u chipset ---

ebay - $20 USD - [ZyXEL Dual-Band Wireless AC600 USB Adapter, NWD6505](https://www.ebay.com/itm/293268959565)

Amazon - $40 USD - [Asus Dualband Wirel. AC600 USB, USB-AC51](https://www.amazon.com/Asus-Dualband-Wirel-AC600-USB-AC51/dp/B00T3DK154)

Amazon - $25 USD - [Panda Pau0a AC600 Dual Band Wireless USB Adapter](https://www.amazon.com/Panda-Wireless-PAU0A-AC600-Adapter/dp/B07C9TYDR4)

-----

### Single Band USB WiFi Adapters that are supported with Linux `in-kernel` drivers

-----

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can be very handy.

-----

#### N150 - USB 2 - 2.4 GHz (WIFI 4)

-----

##### `chipset - Mediatek rt5370 (Mediatek bought Ralink a few years ago)` - N150 - USB 2

Some technical details...

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

Note: I own one or more adapters based on the rt5370 chipset. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/146597475-4fa85f49-f04b-424d-85b5-15cec897f2f2.png)

Amazon - $19 USD - (nano) [Panda PAU03 (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG)

Review: Solid little NANO adapter. It just works. 

![image](https://user-images.githubusercontent.com/69053122/146597551-7bbe3b45-528d-4a55-a5c6-c08b85d9d8a6.png)

Amazon - $20 USD - [Panda Mid Range 150Mbps Wireless N USB Adapter w/ 2dBi Antenna](https://www.amazon.com/gp/product/B004AC0L4Y) - I have read many positive comments from Linux users about this adapter.

Amazon - $26 USD - [CanaKit BC19675 Raspberry Pi WiFi Adapter](https://www.amazon.com/dp/B00GFAN498)

AliExpress - [AliExpress has many links to adapters based on the rt5370 chipset](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20211217111156&origin=y&SearchText=rt5370+usb+wifi+adapter)

Note: The above link will show many adapters. Ensure you check to make sure the adapter is based on the rt5370 chipset. Use caution as there are likely a lot of poor quality adapters in the list.

-----

##### `chipset -  Mediatek mt7601u` - N150 - USB 2 - supported in-kernel since Linux kernel 4.2 (2015)

Note: the mt7601u driver only supports managed and monitor modes (no AP mode and monitor mode does not support
packet injection).

Note: I own one or more adapters based on the mt7601u chipset. Feel free to ask questions.

Amazon - $8 USD - [EDUP MS8551 USB WiFi Adapter for PC - High Gain 6dBi Antenna](https://www.amazon.com/gp/product/B0827LG8L2)

Review by Nick: I own this EDUP adapter and run it with Linux. I consider this adapter to be a very dependable long range adapter for managed mode. The antenna on this adapter can only fold 90 degrees but cannot rotate which can be a little annoying depending on how you use it .

Amazon - $7 USD - (nano) [Zibo Mini USB Wifi Wireless Adapter, 150Mbps](https://www.amazon.com/Zibo-Wireless-Adapter-150Mbps-Supports/dp/B00RBBUQLE)

-----

##### `chipset - Atheros ar9271 [2]` - N150 - USB 2

Note: Production of the ar9271 chipset ended during 2021. There are still new adapters for sale for now.

Note: I own one or more adapters based on the ar9271 chipset. Feel free to ask questions.

```
>=================================<
>=======> ALFA AWUS036NHA <=======<
>=================================<

```

![image](https://user-images.githubusercontent.com/69053122/132881997-c6f89f85-4505-4154-a711-a08796b527a7.png)

Rokland - $29 - [ALFA AWUS036NHA Atheros AR9271 802.11n WIRELESS-N USB Wi-Fi adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036nha-802-11n-wireless-n-usb-wi-fi-adapter-2-watt) - Info: free shipping and no tax outside of Florida. Ships to Canada and US. I have read many positive comments from Linux users about this adapter.

ebay - $29 - [ALFA AWUS036NHA 802.11n Wireless-N Wi-Fi USB Adapter High Speed Atheros AR9271](https://www.ebay.com/itm/ALFA-AWUS036NHA-802-11n-Wireless-N-Wi-Fi-USB-Adapter-High-Speed-Atheros-AR9271/380458349886?epid=1600491254&hash=item589515b53e:g:zW8AAOSwnCFaQ9Oe) - I have read many positive comments from Linux users about this adapter.

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
