# USB WiFi adapters that are supported with Linux `in-kernel` drivers

## Table of Contents
1. [Introduction](#introduction)
2. [Tri Band adapters](#tri-band-usb-wifi-adapters-that-are-supported-with-linux-in-kernel-drivers):
   * [BE6500 - USB3.0 - 2.4 GHz, 5 GHz and 6 GHz (WiFi 7)](#be6500---usb30---24-ghz-5-ghz-and-6-ghz-wifi-7)
   * [AXE3000 - USB3.0 - 2.4 GHz, 5 GHz and 6 GHz (WiFi 6E)](#axe3000---usb30---24-ghz-5-ghz-and-6-ghz-wifi-6e)
3. [Dual Band adapters](#dual-band-usb-wifi-adapters-that-are-supported-with-linux-in-kernel-drivers):
   * [AX1800 - USB 3 - 2.4 GHz and 5 GHz (WiFi 6)](#ax1800---usb-3---24-ghz-and-5-ghz-wifi-6)
   * [AC1900 - USB 3 - 2.4 GHz and 5 GHz (WiFi 5)](#ac1900---usb-3---24-ghz-and-5-ghz-wifi-5)
   * [AC1200 / AC1300 - USB 3 - 2.4 GHz and 5 GHz (WiFi 5)](#ac1200--ac1300---usb-3---24-ghz-and-5-ghz-wifi-5)
   * [AC580 / AC600 / AC650 - USB 2 - 2.4 GHz and 5 GHz (WiFi 5)](#ac580--ac600--ac650---usb-2---24-ghz-and-5-ghz-wifi-5)
4. [Single Band adapters](#single-band-usb-wifi-adapters-that-are-supported-with-linux-in-kernel-drivers):
   * [N150 - USB 2 - 2.4 GHz (WiFi 4)](#n150---usb-2---24-ghz-wifi-4)

-----

## Introduction

### What is this list ?
USB WiFi adapters that are supported with Linux Wireless Standards Compliant (mac80211) drivers and follow the additional policies shown below. These adapters will be plug-and-play with almost all desktop distros as long as the kernel in the distro that is in use is modern enough to contain the support. Most modern adapters shown in the list will mention what kernel version is required for the adapter to be plug and play. Additional work may be required for server distros as the maintainers of server distros seem to think that there are ethernet cables everywhere a user may choose to locate a server. Linux `in-kernel` drivers are preferable over `out-of-kernel` drivers for most users and use cases as problems with locating, installing and maintaining drivers are dramatically reduced allowing for a better experience.

Policy: USB WiFi adapters listed here adhere to the following policies:

```
- all adapters use modern in-kernel (mac80211) drivers that make the adapters plug and play (No Exceptions!)
- all adapters are single-state (no Windows driver inside) (No Exceptions!)
- all adapters must pass rigorous testing by me, @morrownr, or have multiply recommendations from users 
- adapters that are single-function (no Bluetooth support) are preferred and will be given listing priority
- adapters that use chip maker default device IDs, VID/PID, are preferred and will be given listing priority
- no adapters from brands that have a history of doing things that make Linux support difficult
- no white-box adapters. White box adapters are used by resellers that pop up for short periods
```

Buying adapters that meet these criteria greatly increase the probability of a satisfying experience that should last for many years.

Note: This site strives for continuous improvement. You can be a part of making this site better.

### Recent changes:

- 2025-11-01 - added Brostrend AX9L to the axe3000 section - WiFi 6, AXE3000.
- 2025-09-18 - added Netgear A7500 to the ax1800 section - WiFi 6, AX1800.
- 2025-09-08 - added Netgear A9000 to the be6500 section - WiFi 7, BE6500.
- 2025-08-25 - added ALFA AWUS1900 to the ac1900 section - WiFi 5, AC1900.
- 2025-08-03 - returned ALFA AWUS036AXML to the axe3000 section after extensive testing with kernels 6.12+.
- 2025-06-05 - added ALFA AWUS036ACH to the ac1200 section - WiFi 5, AC1200. 
- 2025-05-12 - added ALFA AWUS036ACS to the ac600 section - WiFi 5, AC600.
- 2025-01-08 - added TP-Link TXE50UH to the axe3000 section - WiFi 6, AXE3000.
- 2024-11-10 - removed the Alfa AXML and AXM adapters due to an ongoing issue. Edit: 2025-06-05 - tests with Ubuntu 25.04, which uses kernel 6.14, show AXML operating normally again after recent patches have made it into mainline. Once additional testing is completed with additional distros, the AXML may be returned to this list. If you have an AXML adapter, please test and post your results to `Issues`.
- 2024-07-18 - added Panda PAU0F to the axe3000 section - WiFi 6, AXE3000.
- 2024-07-10 - added Fenvi FU-AX1801D to the ax1800 section - WiFi 6, AX1800.
- 2024-03-24 - added EDUP EP-AX1672 to the axe3000 section - WiFi 6, AXE3000. 
- 2024-03-24 - added PIX-LINK LV-UAC04 to ac1200 section - WiFi 5, AC1200.
- 2024-01-13 - added generic rtl8812bu adapter to the ac1200 section - WiFi 5, AC1200.
- 2023-09-21 - added Fenvi FU-AX1800 to the ax1800 section - WiFi 6, AX1800. 
- 2023-05-18 - added ALLNET ALL-WA1200AC to the ac1200 section - WiFi 5, AC1200.
- 2023-04-10 - added BrosTrend AC3L to the ac1200 section - WiFi 5, AC1200.
- 2023-02-15 - added Panda PAU0B to the ac600 section - WiFi 5, AC600.
- 2023-02-01 - added ALFA AWUS036AXML to the axe3000 section - WiFi 6, AXE3000.
- 2023-02-01 - added Netgear A8000 to axe3000 section - WiFi 6, AXE3000.


### Market & pricing

Important: Price and availability of listed adapters is subject to change. Updating the list of adapters does take a considerable amount of time. I try to complete a review of the links and information at least once ever three months. This site has increased in popularity to the point that readers of this site may cause inventory problems for some sellers at times so you may need to wait for inventory to be refreshed. To help with this problem, I have listed multiple links for some of the popular adapters. If you see any problems or see links that should be added, changed or removed, please post in `Issues.`

Market Conditions: 2025-10-17 - Many good adapters are available. Prices for some adapters are still higher than before the pandemic but many adapters have returned to or are lower than pre-pandemic prices. Unfortunately, price stability is uncertain for many countries going forward given the ongoing trade wars or threatened trade wars initiated by the US president. The outcome of the trade wars is unknown at this time. Most of you should be able to find something that meets your needs at a price you can afford if you shop around. Please take a look at the entire list and ask questions in `Issues`.


-----

## Tri Band USB WiFi Adapters that are supported with Linux `in-kernel` drivers

-----

### BE6500 - USB3.0 - 2.4 GHz, 5 GHz and 6 GHz (WiFi 7)

-----

#### `chipset - Mediatek mt7925 - supported in-kernel since Linux kernel 6.7 (2024)` - WiFi 7 chip that supports 160 MHz Channel width

Warning: There is also a mt7927 chipset that is very similar to the mt7925. It is also available on cards for internal installation. However, support for the mt7927 has not gone into the Linux kernel yet. The mt7927 supports a channel width of 320 MHz but otherwise appears to be the same as the mt7925 chipset. A separate entry for the mt7927 will be made above once support is in the Linux kernel.

```
>================================<
>======>  Netgear A9000 <========<
>================================<
```

<img width="1200" height="1200" alt="image" src="https://github.com/user-attachments/assets/69458506-c547-4579-b874-f449893b3624" />

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: The Windows driver is supplied on a small flash drive.
Note: This adapter uses the mt7925u chipset.
Note: This adapter does not use the standard Mediatek device ID (VID/PID). See below.
Note: Oldest kernel that supports this adapter: 6.7
Note: Oldest LTS kernel that supports this adapter: kernel 6.12
Note: Recommended kernel: 6.12 or later
Note: Supported interface modes with kernel where support started:
		* managed		(6.7+)
		* AP			(6.7+)
		* AP/VLAN		(6.7+)
		* monitor		(6.7+)
		* P2P-client	(6.7+)
		* P2P-GO		(6.7+)

Note: Device supports active monitor (which will ACK incoming frames)
```

Amazon - 100 USD - [Netgear A9000 - BE6500 class USB WiFi adapter](https://www.amazon.com/NETGEAR-Nighthawk-WiFi-Adapter-A9000/dp/B0F9HTJXXC)

Walmart - 100 USD - this adapter is on the shelves of many Walmart Supercenters

07-07-25: I was able to purchase a new Netgear A9000 WiFi 7 USB adapter based on the mt7925 chip at a local Walmart. I will be testing and reporting at the following location: https://github.com/morrownr/USB-WiFi/issues/630 This adapter may or may not stay in this list depending on how testing and reports go. So far, the results have been good so I am listing this adapter for now. I am impressed with the range and overall quality of this adapter.

Important: The Netgear A9000 uses a device ID (VID/PID) that is scheduled to go into Linux kernel 6.18. (Edit: The patch that added the VID/PID to kernel 6.18 went in as expected and backported versions of the patch were applied to kernels 6.17 and 6.12 on 10-17-2025.) If you are using kernel 6.7 or later and this adapter is not plug and play, there is a way to tell your Linux system about the device ID (VID/PID):

Hotplug automation using udev

Open a terminal: Ctrl + Alt + T

Create a file:

```
sudo nano /etc/udev/rules.d/90-usb-0846:9072-mt7925u.rules
```

Note: you can change nano to the text editor of your choice in the above command.

Copy the below lines and paste them into the above file that you are creating:

```
ACTION=="add", \
	SUBSYSTEM=="usb", \
	ENV{ID_VENDOR_ID}=="0846", \
	ENV{ID_MODEL_ID}=="9072", \
	RUN+="/usr/sbin/modprobe mt7925u", \
	RUN+="/bin/sh -c 'echo 0846 9072 > /sys/bus/usb/drivers/mt7925u/new_id'"
 ```

Save file: Ctrl + O, Ctrl + X

Reboot:

```
sudo reboot
```

To remove the file created above: (if it is no longer necessary or did not work)

```
sudo rm /etc/udev/rules.d/90-usb-0846:9072-mt7925u.rules
```

Reviews: in progress

-----

### AXE3000 - USB3.0 - 2.4 GHz, 5 GHz and 6 GHz (WiFi 6E)

-----

#### `chipset - Mediatek mt7921au - supported in-kernel since Linux kernel 5.18 (2022) (AP Mode support added in kernel 5.19) (P2P Mode support added in kernel 6.4) (PS2 Device Mode support add in kernel 6.14)- Filogic 330 - abgn+ac+ax - 2x2:2 - Wi-Fi 6E, WPA3, OFDMA, Zero DFS, BT 5.2, MU-MIMO, 1024QAM, HE80, LNA/PA, ESR`

Info: It is necessary to add additional information in this section before listing the adapters because the driver, firmware and adapters are still relatively new to the market and there are things that Linux users need to know.

Info: Be aware that the range of the 6 GHz band has been reduced compared to the 5 GHz band. This is especially true in some countries. So, while 6 GHz may have a big pipeline, it will have less range than 5 GHz and dramatically less range than the 2.4 GHz band. My testing often shows better throughput on 5 GHz vs 6 GHz depending on distance from AP. Another issue you need to be aware of is that wifi routers vary in how they handle clients. It is best that you pick a wifi AP/router that gives you the ability to set different names for all 3 bands so that you can control which band you are connected to. Checking the throughput of each band will allow you to see where your best performance is. Testing different channels in your AP/router can also help you find where your best performance is. Another issue that users need to be aware is that 6 GHz AP mode operation may be unavailable in some countries due to regulatory issues. An example of this is the US where laws make it such that NO-IR has to be shown in regdb which makes AP mode impossible for 6 GHz with USB WiFi adapters. Hopefully this can be changed at some point.

Status: USB adapters featuring the mt7921au chipset have been available since July 2022. `Adapters based on the mt7921au chipset should not be considered plug and play` unless you are using a distro using kernel 5.19 or later such as Ubuntu 22.10+. `If you are not technically inclined and want a plug and play adapter for an older distro, continue on down this list to see adapters that are currently plug and play with almost all popular non-server distros. This includes adapters starting at the AC1200 section` Remember that server distros think the entire world has cabled ethernet connections. You can add wifi support to server distros. Check with your distro doumentation or support forums for more information.

What are the kernel versions you should know about regarding the mt7921au chipset?

- Minimum kernel for managed (client) and monitor modes= 5.18
- Minimum kernel for master (AP) and AP/VLAN modes = 5.19
- Minimum kernel for P2P-GO and P2P-client modes = 6.4
- Minimum kernel for P2P-device = 6.14
- Recommended kernel = 6.6 or later


Note: The mt7921au driver must include the VID/PID that your adapter uses in order for the adapter to be plug and play per the above guidance. Adapter makers may use custom company VID/PID numbers. We like for companies to use default Mediatek VID/PID numbers but some companies like Netgear and TP-Link like to use their own. If this is the case, a patch needs to be submitted to the `linux-wireless` list in order for the VID/PID to be merged into the mainline kernel. An example of this situation is the Netgear A8000 adapter. For more information and a temporary workaround, see the section about the Netgear A8000 below.

The driver (module) for the mt7921au chipset is called mt7921u.ko (plus possibly an additional ending showing the type of compression if the driver is compressed.)  You can check on the driver by running the following command in a terminal:

```
ls -l /usr/lib/modules/$(uname -r)/kernel/drivers/net/wireless/mediatek/mt76/mt7921
```

The file you are looking for is mt7921u.ko.*

Note about OpenWRT: There is an exception to the above information for OpenWRT. The mt7921u driver has been backported to the kernel (5.10) used in OpenWRT 22.03.x. Starting with OpenWRT 22.03.3, simply install the following package:

```
kmod-mt7921u
```

Another note about OpenWRT 22.03: Luci supports WiFi 6 (AX) configuration and it works well. OpenWRT 23.05 supports WiFi 6e. Your success with the 6 Ghz band is dependent on the rules and regulations in the country that you live in. Many countries have yet to pass laws authorizing the 6 Ghz band and then some countries, such as the US, have really restrictive rules on the 6GHz band.

Remember that in-kernel drivers in Linux come in 2 or more parts. There is what is normally called the driver, which is part of the kernel, and the firmware, which may be 1 or more files, is not part of the kernel. Firmware files are part of the distro and have to be installed and updated by the maintainers of your distros or by you. Some distros do not install firmware, Debian, prior to version 12, is an example. Therefore you may to need to install the firmware yourself depending on your Linux distro. You can check the [firmware](./How_to_Install_Firmware_for_Mediatek_based_USB_WiFi_adapters.md) , see appropriate section, to see if firmware needs to be installed or upgraded. Keep in mind that firmware file names should change so you need to check the version to determine if you have the latest version. The symptom of a missing firmware file is that the adapter does not show up on boot... just like if there is no driver in your kernel. To repeat, adapters that use in-kernel drivers, to function properly, the driver (module) is required AND the firmware is required. The absence of either will cause the adapter to not show up on boot. All of the more popular mainstream distros have everything in place. This includes but is not limited to current releases of Ubuntu (and all of its puppies), Debian, fedora, Manjaro, Raspberry Pi OS and many more.

```
>================================<
>======>  Brostrend AX9L <=======<
>================================<
```

<img width="964" height="1285" alt="image" src="https://github.com/user-attachments/assets/fc11c93a-9074-49e0-9c3a-6f12f0fc3ef3" />


```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: Uses the mt7921au chipset.
Note: Uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
Note: Oldest kernel that supports this adapter: 5.18
Note: Oldest LTS kernel that supports this adapter: kernel 6.1
Note: Recommended kernel: 6.6 or later
Note: Supported interface modes with kernel where support started:
		* managed		(5.18+)
		* AP			(5.19+)
		* AP/VLAN		(5.19+)
		* monitor		(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO		(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
```
Video: [Brostrend AX9L](https://www.youtube.com/watch?v=T0bxheJjAMM&t=7s)

Brostrend - 46 USD - [Brostrend AX9L](https://www.brostrend.com/products/ax9l)

Amazon USA - 34 USD (as of 2025-11-01 a 10% off coupon is clickable) - [Brostrend AX9L](https://www.amazon.com/BrosTrend-AXE3000-Linux-WiFi-Adapter/dp/B0F6MY7H62)  - 4.6 stars and 100+ bought in past month

List of Worldwide Amazon Links for the AX9L: (Provided by Brostrend)

USA: https://www.amazon.com/dp/B0F6MY7H62

Canada: https://www.amazon.ca/dp/B0F6MY7H62

Mexico: https://www.amazon.com.mx/dp/B0F6MY7H62

United Kingdom: https://www.amazon.co.uk/dp/B0F6MY7H62

Germany: https://www.amazon.de/dp/B0F6MY7H62

France: https://www.amazon.fr/dp/B0F6MY7H62

Spain: https://www.amazon.es/dp/B0F6MY7H62

Italy: https://www.amazon.it/dp/B0F6MY7H62

Belgium: https://www.amazon.com.be/dp/B0F6MY7H62

Netherlands: https://www.amazon.nl/dp/B0F6MY7H62

Ireland: https://www.amazon.ie/dp/B0F6MY7H62

Poland: https://www.amazon.pl/dp/B0F6MY7H62

Australia: https://www.amazon.com.au/dp/B0F6MY7H62

UAE: https://www.amazon.ae/dp/B0F6MY7H62

KSA: https://www.amazon.sa/dp/B0F6MY7H62

Note: Brostrend has a tech support rep that is very knowledgable regarding Linux.

Review by @morrownr: 2025-11-01 - Brostrend was kind enought to send me an AX9L for testing and review.

I am very impressed with this adapter so far. I will continue testing but it uses a time tested, stable Linux driver, mt7921u, and it has impressed me enough that including it here in The Plug and Play List was an easy decision. The client system is using Debian 13 (kernel 6.12). The adapter was plug and play. I updated the driver firmware per the [Firmware Guide](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Install_Firmware_for_Mediatek_based_USB_WiFi_adapters.md) in the Main Menu but there were no indications that this update was needed. I could not find any problems. The adapter was fast and very stable. I did not notice any thermal related issues even though I pushed it at max WiFi 6 throughput for extended periods. The case of the adapter does have vent holes. Indications are that this adapter has better than average range. It has an LED that serves as a powered up indicator. The LED is a dull blue color that should not bother you if working in low light conditions. Interestingly, on the box that the product ships in, it says `Plug and Play on Linux OS` but does not say anything about Windows, however, it will work on Windows via the Windows 11 driver... the link is provided below. All indications are that this product was designed with Linux in mind. This adapter is plug and play on Linux as long as the kernel you are using is kernel 5.18 or later. My overall opinion is that this adapter is a good adapter and the price is good. Most Linux users running modern Linux distros such as Debian 12+, Ubuntu 24.04+ or fedora 39+ should find this adapter to be a problem free experience.

Update 2025-11-02: I am aware that many Linux users also support at least one Windows 11 system so it can be handy to have an adapter that is also well supported under Windows. It was not easy for me to find the Windows 11 driver on Brostrend's website but here is the link:

[Windows 11 driver for the Brostrend AX9L](https://www.brostrend.com/pages/ax9l-download)

If you want something specific tested or otherwise have questions, let me know by asking in Issues.

```
>================================<
>=====>  EDUP EP-AX1672 <=======<
>================================<
```

![image](https://github.com/morrownr/USB-WiFi/assets/69053122/13513b2b-92b3-4171-92e6-f841510a7f77)

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: Uses the mt7921au chipset.
Note: Uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
Note: Oldest kernel that supports this adapter: 5.18
Note: Oldest LTS kernel that supports this adapter: kernel 6.1
Note: Recommended kernel: 6.6 or later
Note: Supported interface modes with kernel where support started:
		* managed		(5.18+)
		* AP			(5.19+)
		* AP/VLAN		(5.19+)
		* monitor		(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO		(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
Note: Removable antennas.
```

Amazon - 25 USD - [EDUP EP-AX1672](https://www.amazon.com/EDUP-Wireless-802-11AX-Tri-Band-Compatible/dp/B0CZ82RM5L) - 4.5 stars and 300+ bought in past month

Amazon - 30 USD - [EDUP EP-AX1672](https://www.amazon.com/EDUP-Wireless-802-11AX-Tri-Band-Compatible/dp/B0CVVWNSH2)

AliExpress - cheap - [EDUP  EP-AX1672 WiFi 6E Wireless USB 3.0 WiFi Adapter Tri-Band](https://www.aliexpress.us/item/3256807258105481.html)

The following extension cable may be useful for use with this and similar usb wifi adapters:

Amazon - 10 USD - [Extension cable with Dock Station - 2.6ft](https://www.amazon.com/Type-Female-Extension-Station-Docking/dp/B07QMM6YFZ) - 4.6 stars and 50+ bought in past month

Review by @morrownr: 2024-04-24 - I now have one of these adapters.

I tested this adapter for several days in client (managed) mode. I pushed it hard with iperf3. The client system is using Debian 12 (kernel 6.6). The adapter was plug and play. I updated the driver firmware per the Firmware guide in the Main Menu but there were no indications that this update was needed. I could not find any problems. The adapter was fast and very stable. I did not notice any thermal related issues even though I pushed it at max WiFi 6 throughput for extended periods. The case of the adapter does have vent holes. When you combine well done vent holes with a chip that runs cool to begin with, there are no thermal problems. Indications are that this adapter has better than average range. The antennas are removable. I consider removable qntennas to be a really good feature. Lately, the adapter has been running in AP mode using my AP mode guide here on the Main Menu. AP mode performance has been very good. It is very stable with 5 GHz WiFi 6 AP mode. It has an LED that serves as a powered up indicator. At the time of this review, When I look at the Amazon reviews, I see a few less than perfect reviews but I think Linux users can ignore that. It appears that all of the lower rated reviews are from Windows users that are complaining about finding a driver. As Linux users, we don't worry about that since the adapter is plug and play on Linux as long as the kernel you are using is kernel 5.19 or later. My testing is with kernel 6.6 and I have not found any problems that would affect daily use by regular desktop or laptop users. My overall opinion is that this adapter is a good adapter and the price is good. Most Linux users running modern Linux distros such as Debian 12+, Ubuntu 24.04+ or fedora 39+ should find this adapter to be a problem free experience.

Update: 2024-12-15 - Running the adapter with kernel 6.12 these days. It is still very stable. This is a really good adapter to use with Linux.

Update: 2025-03-19 - Running this adapter with kernel 6.14 using Ubuntu 25.04 these days. Extremely stable. New capability for kernel 6.14: P2P-device. Highly recommended adapter for Linux users. Many Linux users have this adapter now. 

If you want something specific tested, let me know by asking in Issues.

```
>================================<
>========> Panda PAU0F <=========<
>================================<
```

![image](https://github.com/user-attachments/assets/b2cd7c31-97cf-4c2f-8525-c64cbe85dfb8)

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: Uses the mt7921au chipset.
Note: Uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
Note: Oldest kernel that supports this adapter: 5.18
Note: Oldest LTS kernel that supports this adapter: kernel 6.1
Note: Recommended kernel: 6.6 or later
Note: Supported interface modes with kernel where support started:
		* managed		(5.18+)
		* AP			(5.19+)
		* AP/VLAN		(5.19+)
		* monitor		(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO		(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
```

Amazon - 33 USD - [Panda PAU0F](https://www.amazon.com/Panda-Wireless%C2%AE-PAU0F-AXE3000-Adapter/dp/B0D972VY9B?th=1) - 4.5 stars and 200+ bought in past month

Review: See reviews at Amazon link above. The reviews are really positive for this adapter. All indications are that this is a really good adapter to use with Linux.

```
>================================<
>======>  Netgear A8000  <==-====<
>================================<
```

Note: This adapter is currently (2025-09-14) listed as a [Best USB WiFi Adapter at the NYTimes](https://www.nytimes.com/wirecutter/reviews/best-usb-wi-fi-adapters/)

<img width="779" height="536" alt="image" src="https://github.com/user-attachments/assets/1bd3fd36-f0e8-4c8e-9d10-12806d2fb0c9" />

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: The Windows driver is supplied on a small flash drive.
Note: This adapter uses the mt7921aun chipset.
Note: This adapter does not use the standard Mediatek device ID (VID/PID). See below.
Note: Oldest kernel that supports this adapter: 6.4
Note: Oldest LTS kernel that supports this adapter: kernel 6.6
Note: Recommended kernel: 6.6 or later
Note: Supported interface modes with kernel where support started:
		* managed		(5.18+)
		* AP			(5.19+)
		* AP/VLAN		(5.19+)
		* monitor		(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO		(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
```

Amazon - 69 USD [NETGEAR Nighthawk WiFi 6E USB 3.0 Adapter (A8000) | AXE3000 Tri-Band Wireless](https://www.amazon.com/gp/product/B0B94R78N7) - 2K+ bought in past month

Walmart - 69 USD [NETGEAR Nighthawk AXE3000 WiFi 6E USB 3.0 Adapter (A8000-100PAS)](https://www.walmart.com/ip/NETGEAR-Nighthawk-AXE3000-WiFi-6E-USB-3-0-Adapter-A8000-100PAS/1457856595)

Netgear - 79 USD -[AXE3000 USB 3.0 WiFi Adapter -A8000](https://www.netgear.com/home/wifi/adapters/a8000/)

Important: The Netgear A8000 uses a device ID (VID/PID) that went into kernel 6.4. If you are using kernel 6.1 or later and this adapter is not plug and play, there is a way to tell your Linux system about the device ID (VID/PID):

Hotplug automation using udev

Open a terminal: Ctrl + Alt + T 

Create a file:

```
sudo nano /etc/udev/rules.d/90-usb-0846:9060-mt7921u.rules
```

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

Save file: Ctrl + O, Ctrl +X

Reboot:

```
sudo reboot
```

To remove the file created above: (if it is no longer necessary or did not work)

```
sudo rm /etc/udev/rules.d/90-usb-0846:9060-mt7921u.rules
```

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
- Cost: At $99 USD MSRP this adapter is not inexpensive. (Editor's note: the price has been falling.)

Overall: Reviews are good for Linux and Windows. This is a very popular adapter for Linux and Windows users. I cannot recall a single user of this adapter reporting anything negative. This appears to be a good adapter to use with Linux.

```
>================================<
>=====>  ALFA AWUS036AXML  <=====<
>================================<
```

![image](https://user-images.githubusercontent.com/69053122/214129007-b58bd915-57e2-4465-afc5-37ae1a0c80a2.png)

Important notice: This adapter includes Bluetooth support. I do not normally recommend
USB WiFi adapters that include Bluetooth support but I am making an exception to policy
to include this adapter. During 2024, a problem in the Linux Bluetooth subsystem caused
problems with the use of this adapter. It took a lot of work to isolate and fix the
problem. The problem has now been fixed for a sufficient amount of time that most users
should no longer see the problem if purchasing the adapter.

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: This adapter uses the mt7921aun chipset.
Note: Uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
Note: Oldest kernel that supports this adapter: 5.18
Note: Oldest LTS kernel that supports this adapter: kernel 6.1
Note: Recommended kernel: 6.12 or later
Note: Supported interface modes with kernel where support started:
		* managed		(5.18+)
		* AP			(5.19+)
		* AP/VLAN		(5.19+)
		* monitor		(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO		(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
```

Rokland - 70 USD - [ALFA AWUS036AXML 802.11ax WiFi 6 1800 mbps Tri Band WiFi USB Adapter w Bluetooth](https://store.rokland.com/collections/wifi-6-6e/products/alfa-awus036axml-802-11ax-wifi-6-1800-mbps-tri-band-wifi-usb-adapter-w-bluetooth)

Video 1 - [Video from Rokland](https://www.youtube.com/watch?v=KkcKSuGn4gw)

Video 2 - [Video from Rokland](https://www.youtube.com/watch?v=_PcuRDY4Jic)

[ALFA AWUS036AXML Driver & Support Page](https://store.rokland.com/pages/alfa-awus036axml-driver-support-page)

Amazon - 61 USD - [ALFA AWUS036AXML 802.11axe WiFi 6E USB 3.0 Adapter AXE3000, Tri Band 6 GHz, Gigabit Speed up to 3Gbps](https://www.amazon.com/ALFA-AWUS036AXML-802-11axe-Adapter-AXE3000/dp/B0BY8GMW32)

ebay - 70 USD - [ALFA AWUS036AXML 802.11axe WiFi 6E USB 3.0 Adapter AXE3000, Tri Band 6 GHz](https://www.ebay.com/itm/134613987799)

Note: Contact [Alfa](https://www.alfa.com.tw/) for information about Alfa dealers near you.

Review by @morrownr : I have owned this adapter for 2+ years. During 2024, a problem with Bluetooth support caused WiFi support to be
problematic. I have been testing the fix for a few months now and I think most modern distros will have the fix included. One of the advantages this adapter has over many of the other listed adapters in this section is that it has removable antennas which allow users to install directional antennas for longer range if so desired. Rokland keeps directional antennas for this adapter in stock. This adapter also appears to have no thermal issues at all and it has a VERY NICE extension cable that can plug into USB3-A and USB3-C ports.

```
>================================<
>======>  TP-Link TXE50UH  <=====<
>================================<
```

![image](https://github.com/user-attachments/assets/773e69c2-a660-4960-b589-10c65d8864c5)

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: This adapter uses the mt7921au chipset.
Note: This adapter does not use the standard Mediatek device ID (VID/PID). See below.
Note: Oldest kernel that supports this adapter: New product
Note: Oldest LTS kernel that supports this adapter: New product
Note: Recommended kernel: 6.14 or later
Note: Supported interface modes with kernel where support started:
		* managed		(5.18+)
		* AP			(5.19+)
		* AP/VLAN		(5.19+)
		* monitor		(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO		(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
```

Amazon - 60 USD [TP-Link WiFi 6E USB Adapter (TXE50UH) AXE3000 Tri-Band Wireless Network Adapter](https://www.amazon.com/TP-Link-WiFi-USB-Adapter-Desktop/dp/B0D4PL4FQM) - 300+ bought in past month

WARNING WARNING WARNING: TP-Link makes an adapter with a very similar name, TX50UH, but it uses a rtl8852/32cu chip and is a multi-state (windows driver onboard) adapter. That is not what you want. Use care to ensure that you order a TP-Link TXE50UH

Important: The TP-Link TXE50UH uses a device ID (VID/PID) that is scheduled to go into Linux kernel 6.14. That means this adapter may not be plug and play on kernels earlier than 6.14. (Edit: The patch with the VID/PID did go into kernel 6.14.) There is a method to let the Linux kernel know the device ID for kernels where the adapter is not yet plug and play: 

Hotplug automation using udev.

Open a terminal: Ctrl + Alt + T 

Create a file called `/etc/udev/rules.d/90-usb-35bc:0107-mt7921u.rules`

```
sudo nano /etc/udev/rules.d/90-usb-35bc:0107-mt7921u.rules
```

Note: you can change `nano` to the text editor of your choice in the above command.

Copy the below lines and paste them into the above file:

```
ACTION=="add", \
	SUBSYSTEM=="usb", \
	ENV{ID_VENDOR_ID}=="35bc", \
	ENV{ID_MODEL_ID}=="0107", \
	RUN+="/usr/sbin/modprobe mt7921u", \
	RUN+="/bin/sh -c 'echo 35bc 0107 > /sys/bus/usb/drivers/mt7921u/new_id'"
```

Save file: Ctrl + O, Ctrl +X

Reboot:

```
sudo reboot
```

Review: See https://github.com/morrownr/USB-WiFi/issues/534 for information. 

Overall: This adapter appears to meet the policy criteria in that it is single-state (no windows driver onboard) and single-function (no bluetooth). For now, users will need to use one of the two methods outlined above for the adapter to work. Once using kernel 6.14 or later, there is no need to use the methods above as the adapter will be plug and play. This appears to be a good adapter to use with Linux so I am making an exception to policy to include this TP-Link adapter here in The Plug and Play List. Users in various parts of the world do not have access to a wide variety of brands and I have seen reports where TP-Link is often available when other brands are not. This adapter will be here on a probationary period. Please report any problems.

-----

## Dual Band USB WiFi Adapters that are supported with Linux `in-kernel` drivers

-----

### AX1800 - USB 3 - 2.4 GHz and 5 GHz (WiFi 6)

-----

#### `chipset - Mediatek mt7921au - supported in-kernel since Linux kernel 5.18 (2022) (AP Mode support added in kernel 5.19) (P2P Mode support added in kernel 6.4) (PS2 Device Mode support add in kernel 6.14)- Filogic 330 - abgn+ac+ax - 2x2:2 - Wi-Fi 6E, WPA3, OFDMA, Zero DFS, BT 5.2, MU-MIMO, 1024QAM, HE80, LNA/PA, ESR`
-----

```
>================================<
>======>  Netgear A7500  <=======<
>================================<
```

<img width="1200" height="1200" alt="image" src="https://github.com/user-attachments/assets/7593239f-9e8d-40cc-8855-f09dbf621cdd" />

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: The Windows driver is supplied on a small flash drive.
Note: This adapter uses the mt7921aun chipset.
Note: This adapter does not use the standard Mediatek device ID (VID/PID). See below.
Note: Oldest kernel that supports this adapter: tbd
Note: Oldest LTS kernel that supports this adapter: kernel 6.12
Note: Recommended kernel: 6.18 or later
Note: Supported interface modes with kernel where support started:
		* managed		(5.18+)
		* AP			(5.19+)
		* AP/VLAN		(5.19+)
		* monitor		(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO		(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
```

Amazon - 49 USD [NETGEAR Nighthawk WiFi 6 USB 3.0 Adapter (A7500) – AX1800 Dual-Band Wireless](https://www.amazon.com/NETGEAR-Nighthawk-WiFi-Adapter-A7500/dp/B0CT66KSW7)

Important: The Netgear A75000 uses a device ID (VID/PID) that is scheduled to go into Linux kernel 6.18. (Edit: The patch that added the VID/PID to kernel 6.18 went in as expected and backported versions of the patch were applied to kernels 6.17, 6.12 and 6.6 on 10-17-2025.) If you are using kernel 6.1 or later and this adapter is not plug and play, there is a way to tell your Linux system about the device ID (VID/PID):

Hotplug automation using udev

Open a terminal: Ctrl + Alt + T 

Create a file:

```
sudo nano /etc/udev/rules.d/90-usb-0846:9065-mt7921u.rules
```

Note: you can change `nano` to the text editor of your choice in the above command.

Copy the below lines and paste them into the above file that you are creating:

```
ACTION=="add", \
	SUBSYSTEM=="usb", \
	ENV{ID_VENDOR_ID}=="0846", \
	ENV{ID_MODEL_ID}=="9065", \
	RUN+="/usr/sbin/modprobe mt7921u", \
	RUN+="/bin/sh -c 'echo 0846 9065 > /sys/bus/usb/drivers/mt7921u/new_id'"
```

Save file: Ctrl + O, Ctrl +X

Reboot:

```
sudo reboot
```

To remove the file created above: (if it is no longer necessary or did not work)

```
sudo rm /etc/udev/rules.d/90-usb-0846:9065-mt7921u.rules
```

Review: If you own this adapter, please provide a review.

Overall: Reviews are good Windows users at the above link. No Linux reviews as we did not know this adapter used the mt7921au chip until very recently. Keep in mind that the VID/PID is scheduled to go into kernel 6.18 so you may need to use the workarounds above if the adapter is not plug and play.

```
>================================<
>=====>  Fenvi FU-AX1800 <=======<
>================================<
```

![image](https://user-images.githubusercontent.com/797782/269444432-5d37d032-8b9b-498a-a4a9-fb135a9194b3.jpg)

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: Uses the mt7921au chipset.
Note: Uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
Note: Oldest kernel that supports this adapter: 5.18
Note: Oldest LTS kernel that supports this adapter: kernel 6.1
Note: Recommended kernel: 6.6 or later
Note: Supported interface modes with kernel where support started:
		* managed	(5.18+)
		* AP		(5.19+)
		* AP/VLAN	(5.19+)
		* monitor	(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO	(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
```

Important: FENVI makes a very similar adapter that contains the rtl8852bu chipset. That is not what you want. The model number that you want is `FU-AX1800` and make sure the ad says `mt7921` in the ad or specifications.

AliExpress - 9 USD (price varies) - [Fenvi FU-AX1800](https://www.aliexpress.us/item/3256805749323751.html?gatewayAdapt=glo2usa4itemAdapt) - 4.7 - 282 Reviews - 1,000+ sold

AliExpress - 9 USD (price varies) - [Fenvi FU-AX1800](https://www.aliexpress.us/item/3256805749359535.html) - 4.7 - 708 Reviews - 3,000+ sold

eBay - 14 USD - [Wifi 6 USB Adapter AX1800 MT7921 Dual Band Wireless USB3.0 Dongle for PC Desktop](https://www.ebay.com/itm/195910179966?itmmeta=01HPSBRRXNF3W2GRKAEVWCXTAH&hash=item2d9d281c7e:g:rosAAOSwOLJkxNlv&itmprp=enc%3AAQAIAAAA4EXD0N%2FMUrA5h9H1aKu84P33%2BnryNROZaAZcNxwxFVXqbW6RTWVXPU0bfpnweDXg0%2B0Yfcf6MCV0pm3i8S88koId8mJxrYkFIcpqVl2sr2Gl71xs9bA6NzyPmSmslgZlpKmNivzvEk4mFPj4gXcQI477lsnur3Efkgzh%2Bi%2FJ66%2FVVhEBAp9H5oYth4HNTjBnNZBEO2WmS%2FIJMiwCAD8KL8GTn9WEETCp4i6JrtfAXeLdS0t1IuG3zIae3%2Bn3CHi1JsKICeApV1FDg0ym8%2FeNc90gGYf926zMQtS11LWAf2ja%7Ctkp%3ABk9SR_iO46u2Yw)

The below link calls the adapter the `Pro` model. It appears the reason for this is that they have included an extension cable.

ebay - 21 USD - [FENVI FU-AX1800 Pro](https://www.ebay.com/itm/226073349190)

Reviews on AliExpress are very positive with almost all Linux users appearing to be happy but keep in mind that low cost adapters with short antennas will likely not have long range. 

```
>================================<
>=====>  Fenvi FU-AX1801D <======<
>================================<
```

![image](https://github.com/user-attachments/assets/eedb3a26-4074-415b-8d5d-9a1ae4ca3cb1)

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: Uses the mt7921au chipset.
Note: Uses the standard Mediatek device ID (VID/PID) for the mt7921au chipset: ID 0e8d:7961
Note: Oldest kernel that supports this adapter: 5.18
Note: Oldest LTS kernel that supports this adapter: kernel 6.1
Note: Recommended kernel: 6.6 or later
Note: Supported interface modes with kernel where support started:
		* managed	(5.18+)
		* AP		(5.19+)
		* AP/VLAN	(5.19+)
		* monitor	(5.18+)
		* P2P-client	(6.4+)
		* P2P-GO	(6.4+)
		* P2P-device	(6.14+)

Note: Device supports active monitor (which will ACK incoming frames)
```

Important: FENVI makes a very similar adapter that contains an rtl8852 chipset. That is not what you want. The model number that you want is `FU-AX1801D` and make sure the ad or specifications say `mt7921`.

AlExpress - 13 USD (price varies) - [Fenvi WiFi 6 USB Adapter](https://aliexpress.com/item/1005007076639821.html) - 4.6 - 344 Reviews - 1,000+ sold

AlExpress - 11 USD (price varies) - [Fenvi WiFi 6 USB Adapter](https://aliexpress.com/item/1005007088760987.html) - 4.7 - 10 Reviews - 84 sold

AlExpress - 15 USD (price varies) - [Fenvi WiFi 6 USB Adapter](https://aliexpress.com/item/1005007097614925.html)

There is a discussion and a review several messages into the following issue:

https://github.com/morrownr/USB-WiFi/issues/455

### AC1200 / AC1300 - USB 3 - 2.4 GHz and 5 GHz (WiFi 5)

-----

#### `chipset - Mediatek mt7612u - supported in-kernel since Linux kernel 4.19 (2018)` - [mt7612u info](https://github.com/morrownr/7612u)

```
>===============================<
>=====>  ALFA AWUS036ACM  <=====<
>===============================<
```

![image](https://user-images.githubusercontent.com/69053122/127750949-809364a6-65ed-4c7c-9abe-4a77cb73848e.png)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
Note: Oldest currently supported LTS kernel that supports this adapter: kernel 5.4
Note: This adapter is a very popular adapter with Linux users.
Note: Supported interface modes:
		 * IBSS
		 * managed
		 * AP
		 * AP/VLAN
		 * monitor
		 * mesh point
		 * P2P-client
		 * P2P-GO
```

Important: If running this adapter with Kali in Virtual Box, here is a [Video](https://store.rokland.com/pages/alfa-awus036acm-kali-virtual-box-instructions) that should help.

Rokland - 43 USD - US - [ALFA AWUS036ACM 802.11ac Dual Band USB WiFi Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036acm-802-11ac-dual-band-2-4-5-ghz-wifi-usb-adapter) - Info: free shipping and no tax outside of Florida. Ships to Canada and US.

Amazon - 43 USD - US - [Alfa AWUS036ACM Long-Range Dual-Band AC1200 USB 3.0 Wi-Fi Adapter](https://www.amazon.com/Network-AWUS036ACM-Long-Range-Wide-Coverage-High-Sensitivity/dp/B08BJS8FXD)

<!-- markdown-link-check-disable-next-line -->
ebay - 43 USD - US - [Alfa AWUS036ACM 867Mbps Long Range Dual Band Wi-Fi USB Adapter](https://www.ebay.com/p/1738034359)

getic - 33 plus VAT EUR - Latvia - [Alfa USB Adapter AWUS036ACM](https://www.getic.com/product/alfa-awus036acm)

Varia - 39 EUR - Germany - [AWUS036ACM - 802.11ac Dualband-WLAN-USB-Adapter 2,4/5 GHz](https://www.varia-store.com/de/suche/search-AWUS036ACM.html)

Note: Contact [Alfa](https://www.alfa.com.tw/) for information about Alfa dealers near you.

[ALFA AWUS036ACM Technical information](./iw_list/ALFA_AWUS036ACM.txt)

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
Note: Oldest currently supported LTS kernel that supports this adapter: kernel 5.4
Note: Supported interface modes:
		 * IBSS
		 * managed
		 * AP
		 * AP/VLAN
		 * monitor
		 * mesh point
		 * P2P-client
		 * P2P-GO
```

Amazon - 30 USD - US - [Panda Wireless PAU0D AC1200 Wireless AC USB Adapter with High Gain Antennas](https://www.amazon.com/Panda-Wireless-AC1200-Adapter-Antennas/dp/B0B2QD6RPX)

Note: The Amazon reviews made by Linux users are generally very positive.

```
>=============================<
>==>  ALLNET ALL-WA1200AC  <==<
>=============================<
```

![image](https://github.com/morrownr/USB-WiFi/assets/69053122/481e3cf8-eaed-448d-bdb1-d8a2a426eac3)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
Note: Oldest currently supported LTS kernel that supports this adapter: kernel 5.4
Note: Supported interface modes:
		 * IBSS
		 * managed
		 * AP
		 * AP/VLAN
		 * monitor
		 * mesh point
		 * P2P-client
		 * P2P-GO
```

pollin.de - 19 EUR - [ALLNET WLAN-Stick ALL-WA1200AC, 1200 MBit/s](https://www.pollin.de/p/allnet-wlan-stick-all-wa1200ac-1200-mbit-s-741314)

```
>=============================<
>===>  PIX-LINK LV-UAC04  <===<
>=============================<
```

![image](https://github.com/morrownr/USB-WiFi/assets/69053122/6903954b-c64f-4b14-93bf-2fbc2d05d915)

```
Note: This is a single-state adapter.
Note: This adapter uses the mt7612u chipset.
Note: Oldest currently supported LTS kernel that supports this adapter: kernel 5.4
Note: Supported interface modes:
		 * IBSS
		 * managed
		 * AP
		 * AP/VLAN
		 * monitor
		 * mesh point
		 * P2P-client
		 * P2P-GO
```

AliExpress - 11 USD - [PIX-LINK LV-UAC04](https://www.aliexpress.us/item/3256803220959476.html)

Amazon.in - India - [PIX-LINK LV-UAC04](https://www.amazon.in/-/hi/dp/B07LGH4RLK)

Electronics Crazy - Singapore - [PIX-LINK LV-UAC04](https://www.electronicscrazy.sg/wireless-usb-adapter-1200m-2.4-5ghz-dual-band-wifi-portable-router-lv-uac04/)

Review: [See this issue](https://github.com/morrownr/USB-WiFi/issues/400#issuecomment-2034951597)

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
Note: Oldest currently supported LTS kernel that supports this adapter: kernel 5.4
Note: Supported interface modes:
		 * IBSS
		 * managed
		 * AP
		 * AP/VLAN
		 * monitor
		 * mesh point
		 * P2P-client
		 * P2P-GO
```

ebay - 26 USD - [NETGEAR AC1200 USB 3.0 Wi-Fi Adapter - A6210-10000S](https://www.ebay.com/p/18021987463)

Review by Nick - The Netgear A6210 is an adapter that is designed to be portable. I rate the range of this adapter to be average as far as small adapters with no external antenna go so if you need a long range adapter, look elsewhere. On the other hand, if range is not an issue, this adapter is easy to pack and take on the road. It comes with a good quality USB3 extension cable plus cradle. It is a stable performer. I have noted that it runs a little warm which is unusual for Mediatek based adapters. Users looking for a portable AC1200 adapter that uses an in-kernel driver and has good performance over short to medium distances should be happy with this adapter. Note: Due to the somewhat limited range of this adapter, I do not recommend it for use in AP mode unless your requirement is only for same room connections. I also do not recommend this adapter for security analysis/pen testing because of the limited range.

To be clear: This adapter can provide good throughput. Here is a sample from iperf3:

```
Bitrate
  366 Mbits/sec                  sender
  365 Mbits/sec                  receiver
```

This test was conducted in client mode at a distance of about 5 meters with 2 walls between the adapter and wifi router. The test was on 5 GHz on a clean DFS channel. This test shows that this adapter can certainly provide AC1200 performance and it is a good adapter to take on the road. It does not have long range so use as an AP should be limited to same room or short distance and monitor mode performance is not going to let you reach out long distances. It appears the twpower is fixed on this adapter at 18 dBm. I am posting this additional paragraph because a user expressed some displeasure at not being able to get this adapter to do what he wanted. My suggestion is that anyone that is not sure of what you need, go to `issues` and ask.

-----

### AC1900 - USB 3 - 2.4 GHz and 5 GHz (WiFi 5)

-----

#### `chipset - Realtek rtl8814au - supported in-kernel since Linux kernel 6.16 (2025).`

```
>============================<
>=====> ALFA AWUS1900 <======<
>============================<
```

<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/435299ba-e979-4220-a07a-ef3258032d99" />


```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: Uses the rtl8814au chipset.
Note: Uses the Realtek device ID (VID/PID) : ID 0bda:8813
Note: Oldest kernel that supports this adapter: 6.16
Note: Oldest LTS kernel that supports this adapter: n/a
Note: Recommended kernel: 6.16 or later
Note: Supported interface modes with kernel where support started:
		* managed		(6.16+)
		* AP			(6.16+)
		* AP/VLAN		(6.16+)
		* monitor		(6.16+)
		* P2P-client	(6.16+)
		* P2P-GO		(6.16+)

Note: Device driver was initially merged into kernel 6.15 but
numerous optimizations were added to kernel 6.16 so kernel 6.16
is shown as the kernel with initial support.
Note: Removable antenna.

```

Rokland - $65 - [ALFA AWUS1900](https://store.rokland.com/products/alfa-awus1900-802-11ac-1900-mbps-dual-band-2-4-5-ghz-wi-fi-usb-adapter-ac1900)

Review: 2025-08-25 - I have had this adapter for some time. This is a really solid adapter. If your router supports AC1900 capability, then this adapter provides speeds faster than AC1200 class adapters. It has good range but not as good as the ALFA AWUS036ACH shown below. The recently added in-kernel driver is part of the rtw88 series of drivers. The rtl8814au chipset has been popular with Linux users for many years but was only supported with an out-of-kernel driver of questionable quality until recently. Now we can enjoy this and other rtl8814au based adapters with a fully Linux Wireless Standards (mac80211) compliant driver. I have tested this driver with Debian 13 with the rtw88 driver installed from the below repo. This adapter will not be plug and play until you are using kernel 6.16+.

Note: If you need to use the new driver with a kernel that is older than 6.16, as old as kernel 5.4,
you can go the following repo and install it:

https://github.com/lwfinger/rtw88

-----

#### `chipset - Realtek rtl8812au - supported in-kernel since Linux kernel 6.14 (2025).`

```
>============================<
>====> ALFA AWUS036ACH <=====<
>============================<
```

![image](https://github.com/user-attachments/assets/b52771eb-2f74-4e03-8167-66ba27c5fa47)

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: Uses the rtl8812au chipset.
Note: Uses the Realtek device ID (VID/PID) : ID 0bda:8812
Note: Oldest kernel that supports this adapter: 6.14
Note: Oldest LTS kernel that supports this adapter: n/a
Note: Recommended kernel: 6.14 or later
Note: Supported interface modes with kernel where support started:
		* IBSS		(6.14+)
		* managed	(6.14+)
		* AP		(6.14+)
		* AP/VLAN	(6.14+)
		* monitor	(6.14+)
		* P2P-client	(6.14+)
		* P2P-GO	(6.14+)

Note: Device driver was initially merged into kernel 6.13 but
numerous optimizations were added to kernel 6.14 so kernel 6.14
is shown as the kernel with initial support.
Note: Removable antenna.

```

Rokland - $65 - [ALFA AWUS036ACH](https://store.rokland.com/collections/802-11ac-wi-fi-clients-receivers/products/alfa-awus036ach-802-11ac-high-power-ac1200-dual-band-wifi-usb-adapter)

Review: 2025-06-05 - I have had this adapter for a few years. I consider it to be one of the all-time best USB WiFi adapters that have been made. Alfa calls it a MAX Power class of adapter. What that means is that this adapter has range that is very impressive. This is a really solid adapter. The recently added in-kernel driver is part of the rtw88 series of drivers. The rtl8812au chipset has been popular with Linux users for many years but was only supported with an out-of-kernel driver until recently. Now we can enjoy this and other rtl8812au based adapters with a fully Linux Wireless Standards (mac80211) compliant driver. I have tested this driver with Ubuntu 25.04 and it is plug and play.

Note: If you need to use the new driver with a kernel that is older than 6.14, as old as kernel 5.4,
you can go the following repo and install it:

https://github.com/lwfinger/rtw88

-----

#### `chipset - Realtek rtl8812bu - supported in-kernel since Linux kernel 6.2 (2023) but kernel 6.12 (2024) or later is strongly recommended due to numerous stability and performance enhancements.`

Note: The in-kernel driver for this chipset is part of rtw88. The name of the driver is rtw88_8822bu. This driver has been improved greatly over the year 2024 and, as of kernel 6.12, is in really good shape. If you use a distro that uses a kernel older than 6.12, then I would recommend that you choose an adapter with a different chipset.

```
>==========================<
>====> BrosTrend AC3L <====<
>==========================<
```

![image](https://user-images.githubusercontent.com/69053122/231029660-be9a8d62-90a3-4c42-9f7c-9fbc82b74a38.png)

BrosTrend - $39 USD - [BrosTrend AC1200 Linux Compatible USB WiFi Adapter - AC3L](https://www.brostrend.com/collections/linux-wifi-adapter/products/ac3l)

Review by @morrownr : This adapter has performed very well. It is a single-state and single-function adapter, which is what we want.

Good:

- It is fast. I have consistently measured around 545 Mbps (clean DFS channel) using iperf3.

- The adapter comes with a nice extension cable/stand. One of the best designs that I have used.

- The quality seems to be above average.

- The antennas are removable so you can use replacement directional antennas if you want and the ability to move the antennas to the position you want is good.

Average:

- Thermal characteristics are average as the adapter will become warm to the touch if running iperf3 for an extended period of time. There are no slits or holes to help with heat during heavy use. This should not be a problem for most use cases as my testing in this regard is torture. I would prefer to see slits or small holes to allow for some airflow.

Bad:

- None

Overall: If you are looking for a rtl8812bu adapter that has very good performance, this adapter should be on your short list.

```
>===================================================<
>====> Generic Realtek RTL8812BU Adapter <====<
>===================================================<
```

Amazon - 20 USD  - [Realtek RTL8812BU USB Wireless Adapter 1200 Mbps with 5 dBi Antenna Dual Band AC1200 WiFi Dongle](https://www.amazon.com/dp/B078NSSM7W?psc=1&ref=ppx_yo2ov_dt_b_product_details)


Review by @kj_sh604: I was looking for a relatively cheap wireless USB adapter on Amazon after having issues with my TP-Link adapter (rtl8821au) and the out-of-kernel drivers for that chipset. I thought it would be better to just stick with an adapter that already has an in-kernel module even if performance may be a bit slower. I am on a rolling-release distro that updates its kernel package as soon as a new stable one comes out, so alleviating the worry of a dkms module either failing or not working properly was of great benefit. I understand that there may be a bit of skeptism and concern given that the adapter is unbranded and seems to be drop-shipped from China but from my overall experience and monitoring my own network it seems to be fine. It performs better with the in-kernel module rather than the out-of-kernel ones. It definitely won't take advantage of your entire internet connection speed but it's very much hassle-free, affordable, and it works. Definitely beats my other "Plug-and-Play" Atheros ones in terms of performance and it remains relatively cool to the touch.

Additional Notes:
* On the Amazon page it says the Brand is "Connecting" but upon clicking that Brand Name it just leads to a page of books and other material that has the word "connecting" in it.
* Obviously, purchase and use at your own risk. It is a unknown brand with no warranty.
* Tested on Zen Kernel Linux 6.6.5-zen1-1-zen 

-----

### AC580 / AC600 / AC650 - USB 2 - 2.4 GHz and 5 GHz (WiFi 5)

-----

#### `chipset - Mediatek mt7610u - supported in-kernel since Linux kernel 4.19 (2018)`

```
>============================<
>====> ALFA AWUS036ACHM <====<
>============================<
```

![image](https://user-images.githubusercontent.com/69053122/129494292-e3e363ed-8119-4ab5-97cb-13018710a289.png)

Note: This adapter looks like a basic everday wifi adapter but it is not! I have tested many adapters and this adapter has the longest range of any modern dual band adapter that I have tested. If you need long range or an adapter that can run 24/7/365 and never miss a beat, this adapter is worth a look. Don't buy it for speed as it is a AC600 adapter, but if looking for range, great AP mode support, great monitor mode support and reliability, take a look.

Rokland - $40 USD - [ALFA AWUS036ACHM 802.11ac Dual Band High Power Mediatek MT7610U WiFi USB Adapter](https://store.rokland.com/collections/wi-fi-usb-adapters/products/alfa-awus036achm-802-11ac-dual-band-high-power-ac1200-mediatek-wifi-usb-adapter)

Amazon - $43 USD - [Alfa AWUS036ACHM 802.11ac WiFi Range Boost USB Adapter](https://www.amazon.com/AWUS036ACHM-802-11ac-Range-Boost-Adapter/dp/B08SJBV1N3)

ebay - $43 USD - [Alfa AWUS036ACHM 802.11ac dual band High Power Wi-Fi USB Adapter +RP-SMA antenna](https://www.ebay.com/itm/383907328953?epid=22045834288&hash=item5962a8f3b9:g:JiEAAOSwbatgBI-l)

[ALFA AWUS036ACHM Technical information](./iw_list/ALFA_AWUS036ACHM_mt7610u.md)

[ALFA Network Linux support for MT7610U based products](https://docs.alfa.com.tw/Support/Linux/MT7610U/)

Review by Nick - The Alfa AWUS036ACHM is a good product. It is mid-priced, well made, runs cool, has EXCEPTIONAL range and works well in managed mode, master mode and monitor mode. I have recently been testing master (AP) mode: This adapter is exceptional in 2.4 GHz AP mode and good in 5 GHZ AP mode. The range in both bands exceeds the wifi router that I tested it against and I consider that wifi router to have good range. One thing to consider regarding 5 GHz AP mode is that this is an AC600 device so maximum transfer rate is limited to 433 Mb/s. That is fast enough for most use cases and will be for a long time but it is not as fast as you can get from an AC1200 adapter. This adapter shows good link quality and signal level even in difficult situations where other adapters would drop the connection. My testing shows that this adapter has the longest range of any current dual band consumer grade adapter that Alfa sells and Alfa is known for their long range products. My opinion is that this adapter is the single best adapter available for use with Kali Linux or other distros used for pen testing and security analysis. Compared to the Alfa AWUS036ACH, the Alfa AWUS036ACHM has better range, costs less and is supported with in-kernel drivers making it the better choice for Linux users. It comes with the required USB2 cable and a clip that allows you to mount the adapter in various locations. Overall, the Alfa AWUS036ACHM is a solid performer. Highly recommended.


```
=====> PANDA - PAU0B <=====
```

![Panda0B](https://user-images.githubusercontent.com/69053122/219270466-d7e64f57-c0da-4dea-bf59-f9c58b532e59.png)

Amazon - $28 USD - [Panda Wireless® PAU0B AC600 Dual Band (2.4GHz and 5GHz) Wireless USB Adapter W/ High Gain Antenna - Mint, Ubuntu, openSUSE, Fedora, Centos, Kali Linux and Raspberry PiOS](https://www.amazon.com/dp/B08NPX2X4Z/?tag=pandaw-20)

Review: The reviews on Amazon are favorable.

```
=====> ANDDEAR - MT761003 <=====
```

![76-new](https://user-images.githubusercontent.com/69053122/132886023-58a44509-1d65-4de7-96fe-803064631301.jpg)

AliExpress - $9 USD - [ANDDEAR - MT761003](https://www.aliexpress.com/item/4000079918154.html)

Review by amisix - This adapter is $12 as of 2022-04-22. It is size (2.25" x 1" x .3"). It consumes less power than many adapters (~110mA/idle, 150mA-230mA/at load). The ANDDEAR-MT761003 is only an AC600 adapter (150N/433AC) although it performs quite well in real-world usage, has a medium transmission distance, and when running casual internet speed tests it easily achieved 100Mbps - the maximum speed of my ISP. It has an excellent Mediatek chipset that is highly capable with AP, monitor mode, and packet injection and the drivers are included in kernel so it just works. Overall I highly recommend the ANDDEAR-MT761003 if you're looking for something that's highly capable and you need qualities other than raw speed.

Important: ANDDEAR also makes an AC1200 version of this adapter that uses a mt7612u chipset. Avoid it. In testing, it was found to have a bug that generally shows in USB3 ports if port 1 is used. The conclusion of the testers is that the mt7612u chipset version of this adapter should be avoided as no workaround or fix could be identified. However, the above listed adapter based on the mt7610u chipset does not show this critical bug and should work well for you.

--- Links to additional adapters that are based on the mt7610u chipset ---

ebay - $14 USD - [ZyXEL Dual-Band Wireless AC600 USB Adapter, NWD6505](https://www.ebay.com/itm/293268959565)

Amazon - $40 USD - [Asus Dualband Wirel. AC600 USB, USB-AC51](https://www.amazon.com/Asus-Dualband-Wirel-AC600-USB-AC51/dp/B00T3DK154)

Amazon - $25 USD - [Panda Pau0a AC600 Dual Band Wireless USB Adapter](https://www.amazon.com/Panda-Wireless-PAU0A-AC600-Adapter/dp/B07C9TYDR4)

#### `chipset - Realtek rtl8821/11au - supported in-kernel since Linux kernel 6.14 (2025)`

```
>============================<
>====> ALFA AWUS036ACS <====<
>============================<
```

![image](https://github.com/user-attachments/assets/42e443ff-45df-4b20-99a3-b5471d8cb0f4)

```
Note: Single-state, no windows driver onboard, wifi only adapter.
Note: Uses the rtl8811au chipset.
Note: Uses the Realtek device ID (VID/PID) : ID 0bda:0811
Note: Oldest kernel that supports this adapter: 6.14
Note: Oldest LTS kernel that supports this adapter: n/a
Note: Recommended kernel: 6.14 or later
Note: Supported interface modes with kernel where support started:
		* IBSS		(6.14+)
		* managed	(6.14+)
		* AP		(6.14+)
		* AP/VLAN	(6.14+)
		* monitor	(6.14+)
		* P2P-client	(6.14+)
		* P2P-GO	(6.14+)

Note: Device driver was initially merged into kernel 6.13 but
numerous optimizations were added to kernel 6.14 so kernel 6.14
is shown as the kernel with initial support.
Note: Removable antenna.

```

Rokland - $27 - [ALFA AWUS036ACS](https://store.rokland.com/collections/802-11ac-wi-fi-clients-receivers/products/alfa-awus036acs-802-11ac-ac600-dual-band-wifi-usb-adapter-rp-sma)

Review: 2025-05-12 - I have had this adapter for a few years. I consider it to be a very good adapter to use with Linux. This is a really solid small adapter. The recently added in-kernel driver is part of the rtw88 series of drivers. The rtl8811au chipset has been popular with Linux users for many years but was only supported with an out-of-kernel driver until now. Now we can enjoy this and other rtl8821/11au based adapters with a fully Linux Wireless Standards (mac80211) compliant driver. I have tested this driver with Ubuntu 25.04 and it is plug and play.

Note: If you need to use the new driver with a kernel that is older than 6.14, as old as kernel 5.4,
you can go the following repo and install it:

https://github.com/lwfinger/rtw88

-----

## Single Band USB WiFi Adapters that are supported with Linux `in-kernel` drivers

-----

Note: Keeping an inexpensive single band adapter that is supported by in-kernel drivers in your toolkit can be very handy.

-----

### N150 - USB 2 - 2.4 GHz (WiFi 4)

-----

#### `chipset - Ralink rt5370 (Mediatek bought Ralink a few years ago)` - N150 - USB 2

Some technical details... (the driver for this chipset is very good)

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
```

Note: I own one or more adapters based on the rt5370 chipset. Feel free to ask questions.

![image](https://user-images.githubusercontent.com/69053122/146597475-4fa85f49-f04b-424d-85b5-15cec897f2f2.png)

Amazon - $19 USD - (nano) [Panda PAU03 (b/g/n) 150Mbps Wireless-N 2.4GHz USB Adapter](https://www.amazon.com/Panda-Ultra-150Mbps-Wireless-Adapter/dp/B00762YNMG)

Review: Solid little NANO adapter. It just works. 

![image](https://user-images.githubusercontent.com/69053122/146597551-7bbe3b45-528d-4a55-a5c6-c08b85d9d8a6.png)

Amazon - $20 USD - [Panda Mid Range 150Mbps Wireless N USB Adapter w/ 2dBi Antenna](https://www.amazon.com/gp/product/B004AC0L4Y) - I have read many positive comments from Linux users about this adapter.

AliExpress - [AliExpress has many links to adapters based on the rt5370 chipset](https://www.aliexpress.com/wholesale?catId=0&initiative_id=AS_20211217111156&origin=y&SearchText=rt5370+usb+wifi+adapter)

Note: The above link will show many adapters. Ensure you check to make sure the adapter is based on the rt5370 chipset. Read the reviews. Use caution as there may be some poor quality adapters in the list.

-----

#### `chipset -  Mediatek mt7601u` - N150 - USB 2 - supported in-kernel since Linux kernel 4.2 (2015)

Note: the mt7601u driver only supports managed and monitor modes (no AP mode).

Note: I own one or more adapters based on the mt7601u chipset. Feel free to ask questions.

Amazon - $8 USD - [EDUP MS8551 USB WiFi Adapter for PC - High Gain 6dBi Antenna](https://www.amazon.com/gp/product/B0827LG8L2)

Review by Nick: I own this EDUP adapter and run it with Linux. I consider this adapter to be a very dependable long range adapter for managed mode. The antenna on this adapter can only fold 90 degrees but cannot rotate which can be a little annoying depending on how you use it .

Amazon - $8 USD - (nano) [Zibo Mini USB Wifi Wireless Adapter, 150Mbps](https://www.amazon.com/Zibo-Wireless-Adapter-150Mbps-Supports/dp/B00RBBUQLE)


-----
