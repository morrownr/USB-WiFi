## USB WiFi adapters that are supported with Linux `in-kernel` drivers

With `in-kernel` drivers, adapters are plug-and-play with most desktop distros. Files may need to be added for operation on server distros. Linux `in-kernel` drivers are preferable over `out-of-kernel` drivers for most users and use cases as problems with installation and maintenance are dramatically reduced allowing for a better experience.

-----

Recent changes:

- 2023-04-28 - added EDUP EP-AC1651 (AC600) to rtl8811cu chipset section.
- 2023-04-10 - added BrosTrend AC3L (AC1200) to rtl8812bu chipset section.
- 2023-03-05 - deleted some old adapters that were overpriced.
- 2023-03-05 - checked and updated adapter links and prices.
- 2023-02-15 - added Panda PAU0B (AC600) to the mt7610u chipset section.
- 2023-02-14 - added ALFA AWUS036ACU (AC1200) to rtl8812bu chipset section.
- 2023-02-14 - added EDUP EP-AC1635 (AC600) to rtl8811cu chipset section.
- 2023-02-01 - added ALFA AWUS036AXML (AXE3000) to mt7921au chipset section.
- 2023-02-01 - added Netgear A8000 (AXE3000) to mt7921au chipset section.
- 2023-02-01 - decided to only add single-state, single-function adapters going forward.

-----

Important: Price and availability of listed adapters is subject to change. Updating the list of adapters does take a considerable amount of time. I try to complete a review of the links at least once per month. This site has increased in popularity to the point that readers of this site may cause inventory problems for some sellers at times so you may need to wait for inventory to be refreshed. To help with this problem, I have listed multiple links for some products. If you see any problems or see links that should be added or removed, please post in `Issues.`

Market Conditions: 2023-04-23 - Many good adapters are available. Prices for some, but not all, adapters are still higher than before the pandemic but some adapters have returned to or are lower than pre-pandemic prices. Most of you should be able to find something that meets your needs at a price you can afford if you shop around.

-----

### Tri Band USB WiFi Adapters that are supported with Linux `in-kernel` drivers

-----

#### AXE3000 - USB3.0 - 2.4 GHz, 5 GHz and 6 GHz (WiFi 6E)

-----

##### `chipset - Mediatek mt7921au - supported in-kernel since Linux kernel 5.18 (2022) (AP Mode support added in kernel 5.19) - Filogic 330 - abgn+ac+ax - 2x2:2 - Wi-Fi 6E, WPA3, OFDMA, Zero DFS, BT 5.2, MU-MIMO, 1024QAM, HE80, LNA/PA, ESR`

Info: It is necessary to add additional information in this section before listing the adapters because the driver, firmware and adapters are relatively new to the market and there are things that Linux users need to know.

Status: USB adapters featuring the mt7921au chipset have been available since July 2022. Links to adapters and information are now included in this list. `Adapters based on the mt7921au chipset should not be considered plug and play` unless you are using a recently released distro with kernel 5.19 or later such as Ubuntu 22.10. `If you are not technically inclined and want a plug and play adapter for an older distro, continue on down this list to see adapters that are currently plug and play with almost all popular non-server distros. This includes adapters starting at the AC1200 section` Remember that server distros think the entire world has cabled ethernet connections. You can add wifi support to server distros. Check with your distro doumentation or support forums for more information.

What are the kernel versions you should know about?

- Minimum kernel for managed (client) and monitor modes= 5.18
- Minimum kernel for master (AP) and AP/VLAN modes = 5.19
- Minimum kernel for P2P mode = 6.4
- Minimum kernel for mesh point and IBSS modes = not yet


Note: The mt7921au driver must include the VID/PID that your adapter uses in order for the adapter to be plug and play per the above guidance. Adapter makers may use custom company VID/PID numbers. If this is the case, a patch needs to be submitted to the `linux-wireless` list in order for the VIS/PID to be merged into the mainline and latest LTS as needed. An example of this situation currently is the Netgear A8000 adapter. For more information and a temporary workaround, see the section about the Netgear A8000 below.

The driver (module) is called mt7921u.ko.  You can check on the driver by going to the following location:

/usr/lib/modules/`<your kernel version>`/kernel/drivers/net/wireless/mediatek/mt76/mt7921/mt7921u.ko

Note about OpenWRT: There is an exception to the above for OpenWRT. MT7921u has been backported to the kernel (5.10) used in OpenWRT 22.03.x. Starting with OpenWRT 22.03.3, simply install the following package:

```
kmod-mt7921u
```

Another note about OpenWRT 22.03: Luci supports WiFi 6 (AX) configuration and it works well according to some that have set it up,
Some have reported that WiFi 6e (6 GHz) works but requires manual configuration. Maybe we will see full 6 GHz support in OpenWRT 23.x.

Note about RasPiOS: Missing modules may need to be installed with `sudo apt install linux-modules-extra-raspi`

Remember that in-kernel drivers in Linux come in 2 or more parts. There is what is normally called the driver, which is part of the kernel, and the firmware, which may be 1 or more files, is not part of the kernel. It is part of the distro and has to be installed and updated by the maintainers of your distros or by you. Some distros do not install firmware, Debian is an example. Therefore you may to need to install the firmware yourself depending on your Linux distro. You can check the [firmware](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Install_Firmware_for_Mediatek_based_USB_WiFi_adapters.md) . see section 2, to see if firmware needs to be installed or upgraded. Keep in mind that firmware file names do not change so you have to compare file sizes, dates or version to determine if you have the latest version. The symptom of a firmware problem is that the adapter does not show up... just like if there is no driver installed. To repeat,  adapters that use in-kernel drivers, to function properly, the driver (module) is required AND the firmware is required. The absence of either will cause the adapter to not show up on boot.

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

Rokland - $80 USD - [ALFA AWUS036AXML 802.11ax WiFi 6 1800 mbps Tri Band WiFi USB Adapter w Bluetooth](https://store.rokland.com/collections/wifi-6-6e/products/alfa-awus036axml-802-11ax-wifi-6-1800-mbps-tri-band-wifi-usb-adapter-w-bluetooth)

[Video from Rokland](https://www.youtube.com/watch?v=KkcKSuGn4gw)

Review of user comments by @morrownr : User reports so far are positive with the exception of one user finding a driver error in AP mode but he has submitted a PATCH to correct the situation. One of the big advantages this adapter has over the others listed in this section is that it has removable antennas which allow users to install directional antennas for longer range if so desired. Rokland keeps directional antennas for this adapter in stock. This adapter also appears to have no thermal issues at all and it has a VERY NICE extension cable that can plug into USB3 and USB3-C ports.

Review by @mikebutash :

Overall impression of quality?

It feels solid, no wiggle in the usb-c port, no shakes/rattles. I'm calling it good after a few weeks of abuse moving about between devices.

How well does the cable work?

Good so far, both with 3.1 or with the usb-c or 3.0 adapter in use. Not always a fan of the adapters (ahem, monoprice), but this feels very solid and not sloppy when in use. The cable feels like silicon sheathing and stiff/solid, as a usb-c should for a doc or such for thunderbolt @ 40gb.

Thermal issues?

None so far, at idle it's ~88.2F on top,~89.2F says the harbor freight temp gun, and up to 92.4F with an iperf running.

More to come...
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

Amazon - $100 USD [NETGEAR Nighthawk WiFi 6E USB 3.0 Adapter (A8000) | AXE3000 Tri-Band Wireless](https://www.amazon.com/gp/product/B0B94R78N7)

Walmart - $100 USD [NETGEAR Nighthawk AXE3000 WiFi 6E USB 3.0 Adapter (A8000-100PAS)](https://www.walmart.com/ip/NETGEAR-Nighthawk-AXE3000-WiFi-6E-USB-3-0-Adapter-A8000-100PAS/1457856595)

Netgear - $100 USD -[AXE3000 USB 3.0 WiFi Adapter -A8000](https://www.netgear.com/home/wifi/adapters/a8000/)

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
- Not PnP yet: A PATCH is scheduled to go into kernel 6.4.
- Cost: At $99 USD MSRP this adapter is not inexpensive.
- Packing: Minimal for the cost, unboxing is underwhelimg.

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

AliExpress - $21 USD - [COMFAST CF-953AX](https://www.aliexpress.com/item/3256804283254522.html)

Important: Users have reported that some CF-953AX's (and CF-952AX's) come with a Device ID (VID/PID) of 3574:6211. That is not the standard VID/PID provided by Mediatek, which is 0e8d:7961. You can check the VID/PID as follows:

```
$ lsusb
```

A PATCH was submitted and included in a recent Linux kernel. Said PATCH adds the 3574:6211 VID/PID so as to eliminate this issue. If your adapter is not plug and play, see below.

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

Editor's note regarding the above review: The mt7921au chipset is very fast in AC/5 GHz so even without a WiFi 6 capable router, you can see big increases in 5 GHz band speed. Your actual results will vary according to the amount of congestion, distance from router and other factors. 

Overall, so far, comments from owners of this adapter seem to be generally positive. It likely has a little better range than the Comfast CF-951AX that I own due to the external antennas but range is likely not above average. Most users indicate bluetooth does not work but this may be because Comfast intentionally turned it off. Adapter makers are free to turn on and off any capabilities of the chipset so even though the chipset supports bluetooth, makers may turn it off. Historically, multi-function (wifi and bt) adapters are limited to USB2 because USB3 cables, wiring and connections emit radio energy in the 2.4 GHz frquency range that can and will interfere with bluetooth so, unless an engineer has found a solution, if an adapter says is wifi and bt capable, you can expect wifi to be limited to USB2. This is likely the reason that adapters makers so far have been turning off bluetooth. And I agree with them. This chipset should not be limited to USB2 capability for WiFi.

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

AliExpress - $21 USD - [COMFAST CF-951AX Wifi 6 USB Adapter 802.11AX](https://www.aliexpress.com/item/3256804245691865.html)

BadgerWiFi - $28 Pounds - [COMFAST CF-951AX](https://www.badgerwifi.co.uk/store/p/cf-951ax)

Review: I have been using the CF-951AX for a few months now. I have good things to say about the mt7921au chipset and the mt7921u in-kernel driver. The jury is still out on this specific adapter.

The good:

- The mt7921au chipset seems to be very good. It is fast and the driver is stable.
- Did I mention that this chipset is fast? WiFi 5 = around 625 to 650 Mb/s in my testing.
- The mt7921u in-kernel driver is good (maybe a bug or two for now but overall good).
- The mt7921u in-kernel driver is very stable and supports more than one adapter with the
mt7921au chipset in a single system at the same time.
- I have tested 5 GHz band managed mode, AP mode and monitor mode with very good results.
- I have tested WiFi 6 support for managed mode, AP mode and monitor mode with very good results.

Note: I am not well equipped to test WiFi 6e yet so will have to do that when able.

The bad:

- This adapter will not work with any of the USB3 extension cables or powered USB3 hubs that I have. The cause is unknown at this time. I consider good compatibility with extension cables a must with USB WiFi adapters so that the adapter can be positioned for best reception. You may have to plug this adapter into a port on your system for it to work.
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

Rokland - 43 USD - US - [ALFA AWUS036ACM 802.11ac Dual Band USB WiFi Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036acm-802-11ac-dual-band-2-4-5-ghz-wifi-usb-adapter) - Info: free shipping and no tax outside of Florida. Ships to Canada and US.

Amazon - 42 USD - US - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD)

<!-- markdown-link-check-disable-next-line -->
ebay - 40 USD - US - [Alfa AWUS036ACM 867Mbps Long Range Dual Band Wi-Fi USB Adapter](https://www.ebay.com/p/1738034359)

Amazon.it - 51 EUR - Italy - [Alfa AWUS036ACM](https://www.amazon.it/Alfa-AWUS036ACM/dp/B08BJS8FXD/ref=sr_1_9?__mk_it_IT=%C3%85M%C3%85%C5%BD%C3%95%C3%91&crid=2G6VAKKHUQXQB&keywords=mediatek+wifi+adapter&qid=1650990071&sprefix=mediatek+wifi+adapter%2Caps%2C278&sr=8-9)

getic - 32 plus VAT EUR - Latvia - [Alfa USB Adapter AWUS036ACM](https://www.getic.com/product/alfa-awus036acm)

TUNG NETWORK TRADING - 220 RM - Malaysia - [Alfa AWUS036ACM 802.11ac Dual Band 2.4/5 GHz WiFi USB Adapter](https://www.alfa.net.my/webshaper/store/viewProd.asp?pkProductItem=70)

(out of stock) Varia - 42 EUR - Germany - [AWUS036ACM - 802.11ac Dualband-WLAN-USB-Adapter 2,4/5 GHz](https://www.varia-store.com/de/product/265294-awus036acm-802-11ac-mimo-dualband-wlan-usb-adapter-mit-2-4-5-ghz.html)

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

Amazon - 38 USD - US - [Panda Wireless PAU0D AC1200 Wireless AC USB Adapter with High Gain Antennas](https://www.amazon.com/Panda-Wireless-AC1200-Adapter-Antennas/dp/B0B2QD6RPX)

Review: Pending

```
>=============================<
>=====>  TEROW ROW02CD  <=====<
>=============================<
```

![image](https://user-images.githubusercontent.com/69053122/127751374-7a814003-6ff5-4da6-8534-bdc61ea5f249.png)

```
Note: This adapter uses the mt7612u chipset.
```

Out of stock at previous link. If you are aware of a good link to the TEROW ROW02CD, please let us know.

Warning: TEROW sells a TEROW ROW02FD that is a multi-state adapter. That is not what you want.
Warning: TEROW sells a TEROW ROW12CD that is reported to be based on a rtl8812bu chipset. That is not what you want.

Review by Nick - The TEROW ROW02CD works very well with the Raspberry Pi 4B, 3B+ and 3B. I have tested with various desktop and laptop systems. The TEROW ROW02CD is a single state adapter. The cost of this adapter is low. The performance and quality of the materials used and capabilities is not quite as good as the Alfa AWUS036ACM but that is to be expected since the Alfa AWUS036ACM is a more expensive, premium quality adapter. My experience is that this adapter will provide good stable performance and should meet the needs of most Linux users. In fact, during my testing, a TEROW ROW02CD outperformed in link quality and signal level vs. a similar adapter based on a rtl8812bu chipset when plugged into the same USB3 port and connected to the same wifi router.

```
>=====>  AVM FRITZ! AC 860  <=====<
```

Maintained by @mendel5

![Fritz-860](https://user-images.githubusercontent.com/69053122/193471131-931d28e0-0353-4d66-9732-99662b8f5c0c.jpeg)

```
Note: This is a hybrid single-state/multi-state adapter. It is multi-state but automatically changes state on its own.
Note: This adapter uses the mt7612un chipset.
```

Geizhals.eu - 35 EUR - [AVM FRITZ! AC 860](https://geizhals.eu/avm-fritz-wlan-usb-stick-ac-860-20002687-20002724-a1082383.html)

Amazon Germany - 37 EUR - [AVM FRITZ! AC 860](https://www.amazon.de/dp/B017BD21R8/)

Amazon France - 52 EUR - [AVM FRITZ! AC 860](https://www.amazon.fr/dp/B019E28V4G/)

Amazon Italy - 39 EUR - [AVM FRITZ! AC 860](https://www.amazon.it/dp/B019E28V4G/)

Review by mendel5 - The AVM FRITZ! AC 860 USB WiFi adapter is manufactured by the German company AVM which is well-known in Europe for its FRITZ! products, e.g. routers (FRITZ!Box), WiFi hardware, DECT phones, etc. The official name of this USB WiFi adapter is "AVM FRITZ!WLAN USB Stick AC 860".

The AVM AC 860 was unveiled in 2014 and has been available for purchase since 2015. The performance is advertised as 300 Mbit/​s for 2.4 GHz and 867 Mbits/​s for 5 GHz. The reception of this USB WiFi adapter is mostly good, however not outstanding because it does not have a large antenna unlike other USB WiFi adapters.

AVM has not disclosed any information about the chipset that is used in the AVM AC 860. On a few other websites (e.g. forums, wikis, etc.) it is stated that the AVM AC 860 uses a `mt7662u` chipset. However, the source for these claims is not known. My copy of the AVM AC 860 does not use a `mt7662u` chipset but a `mt7612un` chipset as indicated by the IC markings on my chip. There might be other versions of the AVM AC 860 that use a `mt7662u` chipset.

When analyzing the AVM AC 860 with Linux system tools (e.g. `lsusb`), there is unfortunately no information provided about the chipset that is used in this USB WiFi adapter. Due to the lack of information regarding the chipset from both AVM and `lsusb`, I had to break my AVM AC 860 open and analyze the markings on the chip (IC markings). The markings on the chip were obfuscated by being covered in a layer of black paint which I had to remove with chemicals. Only then it was revealed that my copy of the AVM AC 860 uses a `mt7612un` chipset.

The `usb_modeswitch` properties of the AVM AC 860 are unusual. When I open the file `/etc/usb_modeswitch.conf`, set `DisableSwitching=1` and plug my AVM AC 860 into my Linux computer, a flash drive is opened where I can see the Windows drivers of this USB WiFi adapter. Then after 3-5 minutes the flash drive automatically ejects itself from my computer and the WiFi functionality starts working. So, at first it appears that the AVM AC 860 is a multi-state adapter but then it automatically switches to the WiFi state. Therefore, it can be described as being a multi-state adapter that has been configured to resemble a single-state adapter. It is recommended to set `DisableSwitching=0` for the adapter to be used easily as a plug-and-play device on Linux systems.

To summarize, it appears that AVM has unfortunately modified the `mt7612un` chipset of the AVM AC 860 heavily compared to the chipset's original condition:
1. The chipset information that is accessible through Linux system tools (`lsusb`) does not include the name of the chipset.
2. The IC markings on the chip have been covered in black paint to hide the name of the chipset.
3. The chipset has a weird single-state configuration that appears to be multi-state at first but after approx. 5 minutes the USB WiFi adapter starts working even if `DisableSwitching=1` is set.

Given the obfuscation in both (1) the software and (2) the hardware as well as (3) the unusual single-state / multi-state configuration, I would recommend that people who are interested in the AVM AC 860 question whether the properties of the AVM AC 860 that are described in this review are acceptable for its planned usage.

Other USB WiFi adapters could (and should) be considered that operate as normal single-state adapter, that have less obfuscation about the chipset and that have a larger antenna and therefore stronger reception.

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

Note: The distance from adapter to access point was about 20 feet through 2 walls. I was using a clean DFS channel (104) and set iperf3 to run for 2 minutes so as to see if there were any abnormalities that would show up. No problems noted. This adapter can sustain high transfer rates and uses only about 380 mA during sustained high transfer rates. I used this adapter as my daily driver on my main workstation for about 2 months. I have not noticed any drops at all. It seems to be a very solid adapter and has pretty good range. Range is not what you see from an adapter like the ALFA AWUS036ACHM (further down) but the ALFA AWUS036ACHM is really hard to beat for range. Overall, this adapter is solid and comes with a low price tag.

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

Review by Joop - The AC range is limited (same floor only) Turning on CF-WU782AC on any channel reduces the range of my ALFA AWUS036ACM. Both adapters have USB extension cables and this leads me to think that CF-WU782AC creates unnecessary interference. CF-WU782AC does not support DFS.

Comment by @morrownr - The mt7612u, mt7610u and mt7921u drivers do not currently support DFS channels in AP mode. DFS channels work fine in managed mode. This is an issue that needs to be brought to the attention of Mediatek as this is a capability that we need.

```
>=============================<
>=====>  Netgear A6210  <=====<
>=============================<
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/127751480-4c34f5d7-3e7e-47ad-baab-aa5bad62c6bb.png)

```
Note: This adapter uses the mt7612u chipset.
```

Walmart - $29 USD - [NETGEAR - AC1200 Dual-Band USB 3.0 WiFi Adapter (A6210-10000S)](https://www.walmart.com/ip/NETGEAR-AC1200-Dual-Band-USB-3-0-WiFi-Adapter-A6210-10000S/106539212?a)

ebay - $30 USD - [NETGEAR AC1200 USB 3.0 Wi-Fi Adapter - A6210-10000S](https://www.ebay.com/p/18021987463)

Amazon - $40 USD - [NETGEAR AC1200 Wi-Fi USB Adapter High Gain Dual Band USB 3.0 (A6210)](https://www.amazon.com/NETGEAR-AC1200-Wi-Fi-Adapter-A6210-100PAS/dp/B00MRVJY1G)

Review by Nick - The Netgear A6210 is an adapter that is designed to be portable. I rate the range of this adapter to be average as far as small adapters with no external antenna go so if you need a long range adapter, look elsewhere. On the other hand, if range is not an issue, this adapter is easy to pack and take on the road. It comes with a good quality USB3 extension cable plus cradle. It is a stable performer. I have noted that it runs a little warm which is unusual for Mediatek chipset based adapters. Users looking for a portable AC1200 adapter that uses an in-kernel driver and has good performance over short to medium distances should be happy with this adapter. Note: Due to the somewhat limited range of this adapter, I do not recommend it for use in AP mode unless your requirement is only for same room connections. I also do not recommend this adapter for security analysis/pen testing because of the limited range.

To be clear: This adapter can provide good throughput. Here is a sample from iperf3:

```
Bitrate
  366 Mbits/sec                  sender
  365 Mbits/sec                  receiver

```

This test was conducted in client mode at a distance of about 5 meters with 2 walls between the adapter and wifi router. The test was on 5 GHz on a clean DFS channel. This test shows that this adapter can certainly provide AC1200 performance and it is a good adapter to take on the road. It does not have long range so use as an AP should be limited to same room or short distance and monitor mode performance is not going to let you reach out long distances. It appears the twpower is fixed on this adapter at 18 dBm. I am posting this additional paragraph because a user expressed some displeasure at not being able to get this adapter to do what he wanted. My suggestion is that anyone that is not sure of what you need, go to `issues` and ask.

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

##### `chipset - Realtek rtl8812bu - supported in-kernel since Linux kernel 6.2 (2023)`

Note: While Linux kernel 6.2 does contain an in-kernel driver for this chipset, performance is not that good yet but is improving so some users may decide to use the out-of kernel driver located here at this site for now as it is fast and feature rich:

[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

```
=====> ALFA  AWUS036ACU <=====
```

![image](https://user-images.githubusercontent.com/69053122/218380076-23fdfcc2-ec1c-4037-bed0-a0b24d3d7a7b.png)

Rokland - $22 USD - [ALFA AWUS036ACU (single-state, single-function)](https://store.rokland.com/collections/802-11ac-wi-fi-clients-receivers/products/alfa-awus036acu-802-11ac-ac1200-dual-band-wifi-usb-dongle-rp-sma-antennas)

Review: pending

```
=====> BrosTrend AC3L <=====
```

![image](https://user-images.githubusercontent.com/69053122/231029660-be9a8d62-90a3-4c42-9f7c-9fbc82b74a38.png)

BrosTrend - $41 USD - [BrosTrend AC1200 Linux Compatible USB WiFi Adapter - AC3L](https://www.brostrend.com/collections/linux-wifi-adapter/products/ac3l)

Review by @morrownr: This adapter performed very well. It is a single-state, single-function adapter, which is what we want.

Good:

- It is fast. I have consistently measured around 545 Mbps (clean DFS channel) using iperf3 with the [out-of-kernel driver](https://github.com/morrownr/88x2bu). Testing with the in-kernel driver in kernel 6.3 as of 2023-04-10 shows an iperf3 score of 410 Mbps. The in-kernel driver appears to be stable at this point and the performance is reasonably good. Optimizations continue to be merged.

- Range is above average for a rtl8812bu based adapter.

- The adapter comes with a nice extension cable/stand. One of the best designs that I have used.

- The quality seems to be above average.

- The antennas are removable so you can use replacement directional antennas if you want and the ability to move the antennas to the position you want is good.

Average:

- Thermal characteristics are average as the adapter will become warm to the touch if running iperf3 for an extended period of time. There are no slits or holes to help with heat during heavy use. This test was conducted with an ambient air temperature of 72F so I would not recommend this adapter if it will operate in higher temperatures at high throughput. This should not be a problem for most use cases as my testing in this regard is torture. I would prefer to see slits or small holes to allow for some airflow.

Bad:

- Nothing so far.

Overall: If you are looking for a rtl8812bu adapter that has above average range and very good performance, this adapter should be on your short list. In fact, if my testing continues to show very good results with this adapter, once the in-kernel driver is to the point that it is a very good driver, which may be getting close with kernel 6.4, this driver may end up in the The Superstar List. It is that good.

Additional adapters with the rtl8812bu chipset will be added as time permits. If you have suggestions for adapters that should be included here, please let me know in `issues`.

-----

#### AC580 / AC650 - USB 2 - 2.4 GHz and 5 GHz (WIFI 5)

-----

##### `chipset - Mediatek mt7610u - supported in-kernel since Linux kernel 4.19 (2018)`

```
=====> ALFA AWUS036ACHM <=====
```

![image](https://user-images.githubusercontent.com/69053122/129494292-e3e363ed-8119-4ab5-97cb-13018710a289.png)

Note: This adapter looks like a basic everday wifi adapter but it is not! I have tested many adapters and this adapter has the longest range of any modern dual band adapter that I have tested. If you need long range or an adapter that can run 24/7/365 and never miss a beat, this adapter is worth a look. Don't buy it for speed as it is a AC600 adapter, but if looking for range, great AP mode support, great monitor mode support and reliability, take a look.

Rokland - $40 USD - [ALFA AWUS036ACHM 802.11ac Dual Band High Power Mediatek MT7610U WiFi USB Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036achm-802-11ac-dual-band-high-power-ac1200-mediatek-wifi-usb-adapter)

ebay - $40 USD - [Alfa AWUS036ACHM 802.11ac dual band High Power Wi-Fi USB Adapter +RP-SMA antenna](https://www.ebay.com/itm/265323549415)

Amazon - $40 USD - [Alfa AWUS036ACHM 802.11ac WiFi Range Boost USB Adapter](https://www.amazon.com/AWUS036ACHM-802-11ac-Range-Boost-Adapter/dp/B08SJBV1N3)

ebay - $44 USD - [Alfa AWUS036ACHM 802.11ac dual band High Power Wi-Fi USB Adapter +RP-SMA antenna](https://www.ebay.com/itm/383907328953?epid=22045834288&hash=item5962a8f3b9:g:JiEAAOSwbatgBI-l)

Varia - 44 EUR - Germany - [AWUS036ACHM - 802.11ac WiFi USB-Adapter](https://www.varia-store.com/de/product/265368-awus036achm-802-11ac-wifi-range-boost-usb-adapter.html)

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

AliExpress - $12 USD - [ANDDEAR - MT761003](https://www.aliexpress.com/item/4000079918154.html)

Review by amisix - This adapter is $12 as of 2022-04-22. It is size (2.25" x 1" x .3"). It consumes less power than many adapters (~110mA/idle, 150mA-230mA/at load). The ANDDEAR-MT761003 is only an AC600 adapter (150N/433AC) although it performs quite well in real-world usage, has a medium transmission distance, and when running casual internet speed tests it easily achieved 100Mbps - the maximum speed of my ISP. It has an excellent Mediatek chipset that is highly capable with AP, monitor mode, and packet injection and the drivers are included in kernel so it just works. Overall I highly recommend the ANDDEAR-MT761003 if you're looking for something that's highly capable and you need qualities other than raw speed.

Important: ANDDEAR also makes an AC1200 version of this adapter that uses a mt7612u chipset. Avoid it. In testing, it was found to have a bug that generally shows in USB3 ports if port 1 is used. The conclusion of the testers is that the mt7612u chipset version of this adapter should be avoided as no workaround or fix could be identified. However, the above listed adapter based on the mt7610u chipset does not show this critical bug and should work well for you.

```
=====> Linksys AE6000 <=====
```

Note: I own this adapter and run it with Linux. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/130810068-149bfebd-f93d-4bf3-af84-9a568806d93d.png)

Note: The ANDDEAR - MT761003 is a more cost effective adapter unless you happen to need a very small adapter.

Walmart - $41 USD - [Linksys AE6000 Wireless-AC Mini USB Adapter](https://www.walmart.com/ip/Linksys-AE6000-Wireless-AC-Mini-USB-Adapter/24032271)

Review by Nick - The Linksys AE6000 is a good product. It has better range than most other small adapters that I have used. I am not saying that it is a long range adapter, just that it does pretty good for being a very small adapter. And it is a small adapter. The picture may make the adapter look larger than it is. It is not much bigger than a nano size adapter. Overall, it is a solid performer. Recommended.

--- Links to additional adapters that are based on the mt7610u chipset ---

ebay - $20 USD - [ZyXEL Dual-Band Wireless AC600 USB Adapter, NWD6505](https://www.ebay.com/itm/293268959565)

Amazon - $30 USD - [Asus Dualband Wirel. AC600 USB, USB-AC51](https://www.amazon.com/Asus-Dualband-Wirel-AC600-USB-AC51/dp/B00T3DK154)

Amazon - $25 USD - [Panda Pau0a AC600 Dual Band Wireless USB Adapter](https://www.amazon.com/Panda-Wireless-PAU0A-AC600-Adapter/dp/B07C9TYDR4)

-----

##### `chipset - Realtek rtl8811cu - supported in-kernel since Linux kernel 6.2 (2023) (recommend kernel 6.4 oe later)`

Warning: Do not buy adapters based on the rtl8821cu chipset. This is the version of the chipset that has bluetooth support turned on. I have seen countless problems reported by users of adapters that support bluetooth. I am listing the rtl8811cu for a reason, it is the version of the chipset that does not support bluetooth.

Warning: Numerous adapters with the rtl8811cu and rtl8821cu chipset are multi-state. You do not want a multi-state adapter.

Info: The adapters listed in this section are confirmed to be single-function (no bluetooth) and single-state (no onboard windows driver).

Note: While Linux kernel 6.2+ does contain an in-kernel driver for this chipset, performance in kernel 6.2 is not that good but should improve as time passes. Some users may decide to use the out-of kernel driver located here at this site for now as it is a good driver for an out-of-kernel driver:

[Linux Driver for USB WiFi Adapters that use the RTL8811CU, RTL8821CU, RTL8821CUH and RTL8831AU Chipsets](https://github.com/morrownr/8821cu-20210916)

```
============================
=====> EDUP EP-AC1635 <=====
============================
```

![image](https://user-images.githubusercontent.com/69053122/218340955-c278c636-4fd1-432f-8745-079f782d6865.png)

Amazon - $14 USD - [EDUP EP-AC1635 (single-state, single-function)](https://www.amazon.com/dp/B075R7BFV2/?coliid=I346VGJXS0D9B9&colid=8U2PX153MLY4&psc=1&ref_=lv_ov_lig_dp_it)

Review by @morrownr:

This is a very solid adapter that does its job. Range is above average for a small adapter. No problems to report.

```
============================
=====> EDUP EP-AC1651 <=====
============================
```

Amazon - $10 USD - [EDUP LOVE USB WiFi Adapter AC 650Mbps Nano Size Wireless Network Adapter](https://www.amazon.com/dp/B089QL35T2)

Review by @morrownr:

This is a very solid nano adapter that does its job. Range is above average for a nano adapter. No problems to report.

```
=====> BrosTrend AC5L <=====
```
![image](https://user-images.githubusercontent.com/69053122/229980776-50a9a3b0-41c2-4c85-a27d-b4469bb2db24.png)

BrosTrend - $25 USD - [BrosTrend AC5L 650Mbps Linux Compatible WiFi Adapter Supports Kali Linux, Ubuntu, Mint, Debian, Kubuntu, Zorin, PureOS, Raspberry Pi 2+](https://www.brostrend.com/collections/linux-wifi-adapter/products/ac5l)

Review by @morrownr: This adapter performed well. It is a single-state, single-function adapter, which is what we want.

Good:

- It is fast for an AC600 class adapter as I have consistently measured around 275 Mbps (clean DFS channel) using iperf3 with the above out-of-kernel driver. I will test the new in-kernel driver as able.

- Range is slightly above average for a rtl8811cu based adapter. The antenna is a long, high-gain model.

Average:

- Thermal characteristics are average as the adapter will become warm to the touch if running iperf3 for an extended period of time. There are no slits or holes to help with heat during heavy use. This test was conducted with an ambient air temperature of 72F so I would not recommend this adapter if it will operate in higher temperatures at high throughput. This should not be a problem for most use cases as my testing in this regard is torture. I would prefer to see slits or small holes to allow for some airflow.

Bad:

- The antenna will only fold 90 degrees in one direction and will not rotate at all. My opinion is that adapters of this style should fold 90 degrees in 2 directions and rotate 180 degrees (or have a removable antenna). The antenna is not removable. As it is, this adapter will require a [right angle usb adapter](https://www.amazon.com/dp/B07S6B5X76) to work effectively with small systems like the Raspberry Pi 4B or on laptop/notebook computers. Basically, any computer that has horizontal usb ports will need the right angle usb adapter.

Overall: If you are looking for a rtl8811cu adapter that has slightly above average range and good performance, this adapter should be on your short list but be prepared to purchase a right angle usb adapter if your computer has horizontal usb ports.

Additional adapters with the rtl8811cu chipset will be added as time permits. If you have suggestions for adapters that should be included here, please let me know in `issues`.

-----

### Single Band USB WiFi Adapters that are supported with Linux `in-kernel` drivers

-----

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can be very handy.

-----

#### N150 - USB 2 - 2.4 GHz (WIFI 4)

-----

Note: Several of the below adapters say "Raspberry Pi" which seems to imply they only works with the Raspberry Pi OS but that is not the case. These adapters will work with any mainstream Linux distro that is currently supported by its maker. Another point to make is while N150 adapters are not the latest toy available, they are still very capable, very solid and will certainly allow users to stream FHD video, watch youtube videos, listen to online music and support heavy web surfing without slowdown. Some are cheap enough to justify keeping one around as a backup if for no other reason. My wife's computer uses an adapter with a mt7601u chipset. It just works. In my opinion, the best full function (managed, AP and monitor modes) single band chipset for Linux users is the rt5370 as shown in the next section below:

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

Amazon - $16 USD - (nano) [Panda PAU03 (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG)

Review: Solid little NANO adapter. It just works. 

![image](https://user-images.githubusercontent.com/69053122/146597551-7bbe3b45-528d-4a55-a5c6-c08b85d9d8a6.png)

Amazon - $16 USD - [Panda Mid Range 150Mbps Wireless N USB Adapter w/ 2dBi Antenna](https://www.amazon.com/gp/product/B004AC0L4Y) - I have read many positive comments from Linux users about this adapter.

Amazon - $20 USD - [CanaKit BC19675 Raspberry Pi WiFi Adapter](https://www.amazon.com/dp/B00GFAN498)

AliExpress - [AliExpress has many links to adapters based on the rt5370 chipset](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20211217111156&origin=y&SearchText=rt5370+usb+wifi+adapter)

Note: The above link will show many adapters. Ensure you check to make sure the adapter is based on the rt5370 chipset. Use caution as there are likely a lot of poor quality adapters in the list.

-----

##### `chipset -  Mediatek mt7601u` - N150 - USB 2 - supported in-kernel since Linux kernel 4.2 (2015)

Note: the mt7601u driver only supports managed and monitor modes (no AP mode and monitor mode does not support
packet injection).

Note: I own one or more adapters based on the mt7601u chipset. Feel free to ask questions.

Amazon - $6 USD - [EDUP MS8551 USB WiFi Adapter for PC - High Gain 6dBi Antenna](https://www.amazon.com/gp/product/B0827LG8L2)

Review by Nick: I own this EDUP adapter and run it with Linux. I consider this adapter to be a very dependable long range adapter. The antenna on this
adapter can only fold 90 degrees but cannot rotate which can be a little annoying depending on how you use it .

Amazon - $9 USD - [Mini 150m USB Wifi Wireless Network Card](https://www.amazon.com/Wireless-Network-802-11-Adapter-Antenna/dp/B008Z9IZSW)

Amazon - $1 USD - (nano) [Zibo Mini USB Wifi Wireless Adapter, 150Mbps](https://www.amazon.com/Zibo-Wireless-Adapter-150Mbps-Supports/dp/B00RBBUQLE)

-----

##### `chipset - Atheros ar9271 [2]` - N150 - USB 2

Note: Production of the ar9271 chipset ended during 2021. There are still new adapters for sale for now.

Note: I own one or more adapters based on the ar9271 chipset. Feel free to ask questions.

```
=====> ALFA AWUS036NHA <=====
```
![image](https://user-images.githubusercontent.com/69053122/132881997-c6f89f85-4505-4154-a711-a08796b527a7.png)

Rokland - $27 - [ALFA AWUS036NHA Atheros AR9271 802.11n WIRELESS-N USB Wi-Fi adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036nha-802-11n-wireless-n-usb-wi-fi-adapter-2-watt) - Info: free shipping and no tax outside of Florida. Ships to Canada and US. I have read many positive comments from Linux users about this adapter.

ebay - $29 - [ALFA AWUS036NHA 802.11n Wireless-N Wi-Fi USB Adapter High Speed Atheros AR9271](https://www.ebay.com/itm/ALFA-AWUS036NHA-802-11n-Wireless-N-Wi-Fi-USB-Adapter-High-Speed-Atheros-AR9271/380458349886?epid=1600491254&hash=item589515b53e:g:zW8AAOSwnCFaQ9Oe) - I have read many positive comments from Linux users about this adapter.

-----

##### `chipset - Mediatek/Ralink rt3070 (Mediatek bought Ralink a few years ago)` - N150 - USB 2

Note: Production of the rt3070 chipset ended during 2021. There are still new adapters for sale for now.

Note: I own one or more adapters based on the rt3070 chipset. Feel free to ask questions.

Amazon - $16 USD - [Panda Long Range 150Mbps Wireless N USB Adapter w/High Gain Antenna - PAU08](https://www.amazon.com/Panda-150Mbps-Wireless-Adapter-Antennas/dp/B004AC6X0K)

Review by Nick: The PAU08 has very long range and is capable of handling more than 32 clients. I am aware of users that have used this adapter for AP mode for situations where support for many IoT clients is required and it worked well.

Amazon - $20 USD - [Panda Mini WiFi (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Mini-150Mbps-Wireless-Adapter/dp/B003283M6Q)

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
