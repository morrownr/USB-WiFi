## USB WiFi adapters with Linux `out-of-kernel` drivers

Important: Code to prevent non-Linux Standards Compliant WiFi 7 class chipset drivers from operating in the Linux kernel has been merged into the kernel. This means that drivers build on the same depreciated technology as the ones below, can no longer be used with Linux for WiFi 7. Hopefully this will encourage Realtek to start supporting Linux Standards Compliant in-kernel drivers.

The below listing of drivers and chipsets is ranked in order by quality of driver with best at the top.

The best overall Realtek out-of-kernel drivers currently are the 88x2bu (8812bu and 8822bu chipsets), the 8821cu (8811cu and 8821cu chipsets), the 8812au chipset, and the 8821au (8811au and 8821au chipsets).  These drivers perform well in all modes that I regularly test. I concentrate my testing on client (managed), master (AP) and monitor modes.

My advice, for Linux users needing to buy a new adapter, is to give preference to Mediatek chipset based adapters because the Mediatek drivers are based on Linux Wireless Standards (mac80211) and are maintained in the kernel. This makes the Mediatek based adapters much more troublefree in the long run.

If you are unable to find an adapter based on Mediatek chipsets, then I recommend adapters based on the following chipset:  8812bu. I currently recommend you AVOID adapters based on the Realtek 8814au, 8832au and 8852au chipsets as the drivers are not good and I also recommend you AVOID adapters that are multi-state, and multi-function (wifi and bt).

Note: The below sections provide links to drivers and a lot of information. Twelve (12) total chipsets are supported with the listed drivers.

-----

Recent changes:

- 2023-07-31 - added new driver for the rtl8832bu and rtl8852bu chipsets
- 2023-02-01 - moved 88x2bu higher in the list due to recent improvements
- 2023-01-31 - add new version of driver for the rtl8811cu, rtl8821cu, rtl8821cuh and rtl8731au chipsets (MU-MIMO support)
- 2023-01-30 - add MU-MIMO support for rtl88x2bu driver (new capability)
- 2022-10-23 - added section for 8852/32bu chipset
- 2022-02-02 - additions to reflect a lack of support for 4addr

Note: The above list shows recent administrative changes. The drivers get regular updates.

-----

##### `chipsets - rtl8812bu and rtl8822bu - AC1200 - USB 3`

[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

As of kernel 6.2, the above chipsets have an in-kernel driver. It is located in the rtw88 in-kernel driver. I invite all to test the new in-kernel driver and use it if it meets your needs. A list of recommended adapters has been established in the Main Menu, item 2 (In-Kernel Drivers), section on the rtl8812bu chipset.

These chipsets tend to run cool, which is good. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. While the driver supports 2 chipsets, the one that I recommend is the rtl8812bu chipset because it is single-function (wifi only) chipset. I also recommend that you buy single-state (not multi-state) adapters with the rtl8812bu chipset. 

The Good:

- very fast in managed (client) mode (for an AC1200 chipset)
- AP mode works very well except with RasPi4B USB3 ports (unable to determine the problem)
- runs cool
- MU-MIMO support works well
- WPA3 is supported
- readily available at low prices
- power saving works well
- very stable, fast out-of-kernel driver as well as a new in-kernel driver as of kernel 6.2

The Bad:

- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the really bad quality of some adapters made with this chipset means you need to research before buying

Recommendation: Buy only single-function (wifi only) and single-state adapters with the rtl8812bu chipset.

-----

##### `chipsets - rtl8811cu, rtl8821cu, rtl8821cuh and rtl8731au - AC600  - USB 2`

[Linux Driver for USB WiFi Adapters that use the RTL8811CU, RTL8821CU, RTL8821CUH and RTL8731AU Chipsets](https://github.com/morrownr/8821cu)

As of kernel 6.2, the above chipsets have an in-kernel driver. It is located in the rtw88 in-kernel driver. I invite all to test the new in-kernel driver and use it if it meets your needs. A list of recommended adapters has been established in the Main Menu, item 2 (In-Kernel Drivers), section on the rtl8811cu chipset.

These chipsets tend to run cool, which is good. Adapters based on these chipsets are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. While the driver supports 4 chipsets, the one that I STRONGLY recommend is the rtl8811cu chipset because it is a single-function (wifi only) chipset. I also recommend that you buy single-state (not multi-state) adapters with the rtl8811cu chipset. The single-state, single function adapters that I have tested that use the rtl8811cu chipset are very stable. I have seen numerous problems reported by used that have adapters based on the rtl8821cu chipset (adds bluetooth support). You do not want an adapter based on the rtl8821cu chipset.

The Good:

- fast for an AC600 class chipset
- runs cool
- AP mode is very good
- AP mode DFS support
- Monitor mode is good
- MU-MIMO support works well
- WPA3 is supported
- readily available at low prices
- power saving works well
- very stable, fast out-of-kernel driver as well as a new in-kernel driver as of kernel 6.2

The Bad:

- use caution: buying adapters with the 8821cu chipset (multi-function, wifi and bt) can be problematic
- use caution: many adapter using these chipsets are multi-state
- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the really bad quality of some adapters made with this chipset means you need to research before buying

Recommendation: Buy only single-function (wifi only) and single-state adapters with the rtl8811cu chipset.

-----

##### `chipset - rtl8812au - AC1200 - USB 3`

[Linux Driver for USB WiFi Adapters that use the RTL8812AU Chipset](https://github.com/morrownr/8812au-20210629)

The rtl8812au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code.  However, I just learned from a source I trust that Realtek discontinued Linux driver support for this chipset in 2021. This makes buying adapters based on this chipset a deadend for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8812bu chipset for adapters in the AC1200 class. Not many rtl8812au adapters remain available on the market. The above driver is a good quality driver but it is a deadend.

The Good:

- managed (client) mode works very well
- master (AP) mode is very good
- AP mode DFS support
- monitor mode is good
- WPA3 is supported
- power saving works well
- very stable
- clean compile and clean log

The Bad:

- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the lack of an in-kernel, Linux Wireless Standards (mac80211) compliant driver makes this chipset problematic
- Realtek support ended in 2021
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8812bu

Recommendation: Do not buy adapters based on this chipset.

-----

##### `chipsets - rtl8811au and rtl8821au - AC600 - USB 2`

[Linux Driver for USB WiFi Adapters that use the RTL8811AU and RTL8821AU Chipsets](https://github.com/morrownr/8821au-20210708)

The rtl8811au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. However, I just learned from a source I trust that Realtek discontinued Linux driver support for this chipset in 2021. This makes buying adapters based on this chipset a deadend for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8811cu chipset for adapters in the AC600 class. Adapters that use the rtl8811au chipset are still available but availability is declining. The above driver is a really good quality driver but is a deadend.

The Good:

- managed (client) mode works very well
- master (AP) mode is very good
- AP mode DFS support
- monitor mode is good
- WPA3 is supported
- power saving works well
- very stable
- clean compile and clean log

The Bad:

- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the lack of an in-kernel, Linux Wireless Standards (mac80211) compliant driver makes this chipset problematic
- Realtek support ended in 2021
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8811cu

Recommendation: Do not buy adapters based on this chipset.

-----

##### `chipset - rtl8832bu / rtl8852bu - AX1800 - USB 3`

[Linux driver for USB WiFi Adapters that use the rtl8832bu and rtl8852bu chipsets](https://github.com/morrownr/rtl8852bu)

The Good:

- managed (client) mode works very well
- WPA3 is supported
- There is a possibility these chipsets could be supported with an in-kernel driver in the future (rtw89)

The Bad:

- The adapter I am using is multi-state and it appears that most adapters that use this chipset are multi-state. Not good.
- The log is very dirty.
- Driver lacks several features.
- Driver was inadequately tested by Realtek.

Recommendation: If you want WiFi 6, go get an adapter with the mt7921au chipset. At this point, Realtek's support for WiFi 6 on Linux is behind Mediatek's support.

-----

##### `chipset - rtl8814au - AC1900 - USB 3`

[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

The rtl8814au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. However, I just learned from a source I trust that Realtek discontinued Linux driver support for this chipset in 2019. This makes buying adapters based on this chipset a deadend for Linux users. Adapters based on this chipset can really push data at high speed and are still available but are relatively expensive. They need a pretty good amount of power so a powered USB 3 hub may be a good idea. This chipset builds a lot of heat so look for adapters that have plenty of vent holes and search reviews to see if users are reporting heat problems. The above driver is not very good but it is based on the latest source we have available. The source is from 2019. 

The Good:

- managed (client) mode is reasonably good
- master (AP) is reasonably good
- monitor mode, including injection and deauth, work but there are some problems with capture

The Bad:

- many resellers advertise Linux support but that is deceptive at best (it certainly is the case with this chipset)
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
- Realtek support ended in 2019
- no new source code releases since 2019, and that 2019 release was not a good driver
- uses a lot of power so using a powered hub may be a good idea
- produces a lot of heat, adapter needs a lot of vent holes
- expensive

Recommendation: Do not buy adapters based on this chipset. You will be disappointed. Adapters with the new mt7921au will meet or exceed the performance of this chipset in WiFi 5 AC 5 GHz mode plus you get WiFi 6e capability.

-----

##### `chipset - rtl8832au / rtl8852au - AX1800 - USB 3`

Do not expect a driver for this chipset.

The rtl8852/32au chipset was the first AX class chipset that was available for use in USB WiFi adapters. Unfortunately, Realtek decided to support it with an out-of-kernel driver on Linux instead of doing the right thing and providing a mac80211 technology in-kernel driver. I tested the provided driver (v1.15.0.1). The results were terrible. As many of you know, I have a lot of USB WiFi adapters that I use and test. I cannot recall an experience as bad as this and I have been using USB WiFi adapters for many years. I experienced numerous system lockups that required me to pull the plug to get things going again. Additionally many features are simply not working. Power saving does not work. DFS channels do not work in AP mode. WPA3 did not work in any mode. I saw problems in basic client mode that I cannot explain. The driver is VERY BAD. Avoid adapters based on the 8852/32au chipset.

I have given up on working on a driver for this chipset. I have no plans to ever release a driver for this chipset. If you want WiFi 6, go get an adapter with the mt7921au chipset.

The Good:

- Nothing.

The Bad:

- A long list of bad.
- The adapter I have is multi-state and it appears that most adapters that use this chipset are multi-state. Not good.

Recommendation: AVOID adapters based on this chipset. You will be disappointed. The driver is an out-of-kernel driver that is not consistent with Linux Wireless standards and it is a terrible driver. Recommend Linux users seek out usb wifi adapters that use the mt7921au chipset if seeking an adapter that is WiFi 6 capable.

-----

##### `chipset - rtl8832cu / rtl8852cu - AXE3000 - USB 3`

I will consider making an out-of-kernel driver available for this chipset if I can get a copy of the driver and a decent single-state adapter.

The Good:

- There is a possibility these chipsets could be supported with an in-kernel driver in the future (rtw89)

The Bad:

- Unknown

Recommendation: If you want WiFi 6E, go get an adapter with the mt7921au chipset. Looking forward, Mediatek is currently merging support for their new mt7925 WiFi 7 chipset which will have USB support. We may see new adapters based on this chipset in 2024.


-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
