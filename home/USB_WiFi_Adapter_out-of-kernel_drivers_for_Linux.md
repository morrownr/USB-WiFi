## USB WiFi adapters with Linux `out-of-kernel` drivers

The below listing of drivers and chipsets is ranked in order by quality of driver with best at the top.

The best overall Realtek out-of-kernel drivers currently are the the 8821cu (8811cu and 8821cu chipsets), the 88x2bu (8812bu and 8822bu chipsets), the 8812au, and the 8821au (8811au and 8821au chipsets).  These drivers perform well in all modes that I regularly test. I concentrate my testing on client (managed), master (AP) and monitor modes. The fastest of these drivers is the 88x2bu (with 8812bu chipset).

My advice, for Linux users needing to buy a new adapter, is to give preference to Mediatek chipset based adapters because the Mediatek drivers are based on Linux Wireless Standards (mac80211) and are maintained in the kernel. This makes the Mediatek based adapters much more troublefree in the long run.

If you are unable to find an adapter based on Mediatek chipsets, then I recommend adapters based on these chipsets (in order): 8811cu, 8812bu, 8812au,  and 8811au. I currently recommend you AVOID adapters based on the Realtek 8814au, 8832au, 8852au, 8832bu and 8852bu chipsets as the drivers are not good and I also recommend you AVOID adapters that are multi-state, and multi-function (wifi and bt).

Note: The below sections provide links to drivers and a lot of information. Ten total chipsets are supported with the listed five drivers.

-----

Recent changes:

- 2023-02-01 - moved 88x2bu higher in the list due to recent improvements
- 2023-01-31 - add new version of driver for the rtl8811cu, rtl8821cu, rtl8821cuh and rtl8731au chipsets (MU-MIMO support)
- 2023-01-30 - add MU-MIMO support for rtl88x2bu driver (new capability)
- 2022-12-01 - added rtl8832bu test results and recommendation
- 2022-10-23 - added section for 8852/32bu chipset
- 2022-04-24 - moved Realtek information into this separate document
- 2022-02-02 - additions to reflect a lack of support for 4addr

Note: The above list shows recent administrative changes. The drivers get regular updates.

-----

##### `chipsets - rtl8811cu, rtl8821cu, rtl8821cuh and rtl8731au - AC600  - USB 2`

[Linux Driver for USB WiFi Adapters that use the RTL8811CU, RTL8821CU, RTL8821CUH and RTL8731AU Chipsets](https://github.com/morrownr/8821cu)

As of kernel 6.2, the above chipsets have an in-kernel driver. It is located in the rtw88 in-kernel driver. The performance of this new in-kernel
driver is not so good currently but will likely improve as time passes. I invite all to test the new in-kernel driver and use it if it meets your needs. Most users will likely want to use the out-of-kernel driver shown above for now as it is very stable and performance is excellent. It even supports MU-MIMO. A list of recommended adapters has been established in the Main Menu, item 2 (In-Kernel Drivers), section on the rtl8811cu chipset.

These chipsets tend to run cool, which is good. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. While the driver supports 4 chipsets, the one that I recoomend is the rtl8811cu chipset because it is single-function (wifi only) chipset. I also recommend that you buy single-state (not multi-state) adapters with the rtl8811cu chipset. 

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

##### `chipsets - rtl8812bu and rtl8822bu - AC1200 - USB 3`

[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu)

As of kernel 6.2, the above chipsets have an in-kernel driver. It is located in the rtw88 in-kernel driver. The performance of this new in-kernel
driver is not so good currently but will likely improve as time passes. I invite all to test the new in-kernel driver and use it if it meets your needs. Most users will likely want to use the out-of-kernel driver shown above for now as it is very stable and performance is excellent. It even supports MU-MIMO. A list of recommended adapters has been established in the Main Menu, item 2 (In-Kernel Drivers), section on the rtl8812bu chipset.

These chipsets tend to run cool, which is good. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. While the driver supports 2 chipsets, the one that I recoomend is the rtl8812bu chipset because it is single-function (wifi only) chipset. I also recommend that you buy single-state (not multi-state) adapters with the rtl8812bu chipset. 

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

##### `chipset - rtl8812au - AC1200 - USB 3`

[Linux Driver for USB WiFi Adapters that use the RTL8812AU Chipset](https://github.com/morrownr/8812au-20210629)

The rtl8812au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8812bu chipset for adapters in the AC1200 class. Not many rtl8812au adapters remain available on the market. The above driver is a good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset.  The preferred solution is for Realtek to support an in-kernel Linux Wireless Standards compliant driver.

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
- future Realtek support unknown
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8812bu

Recommendation: This chipset doesn't provide any significant advantages over the mt7612u chipset and the driver for the mt7612u chipset is far superior and is professionally maintained in the Linux kernel. 

-----

##### `chipsets - rtl8811au and rtl8821au - AC600 - USB 2`

[Linux Driver for USB WiFi Adapters that use the RTL8811AU and RTL8821AU Chipsets](https://github.com/morrownr/8821au-20210708)

The rtl8811au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. The market for USB WiFi adapters has seen a switch over the last few years from this chipset to the rtl8811cu chipset for adapters in the AC600 class. Adapters that use the rtl8811au chipset are still available but availability is declining. The above driver is a really good quality driver but the question is, how long will Realtek continue to release out-of-kernel source code for this chipset. The preferred solution is for Realtek to support an in-kernel Linux Wireless Standards compliant driver.

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
- future Realtek support unknown
- will likely never be supported by an in-kernel driver
- limited availability, has mostly been replaced by rtl8811cu

Recommendation: This chipset doesn't provide any significant advantages over the mt7610u chipset and the driver for the mt7610u chipset is professionally maintained in the Linux kernel.

-----

##### `chipset - rtl8814au - AC1900 - USB 3`

[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

The rtl8814au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. Adapters based on this chipset can really push data at high speed and are still available but are relatively expensive. They need a pretty good amount of power so a powered USB 3 hub may be a good idea. This chipset builds a lot of heat so look for adapters that have plenty of vent holes and search reviews to see if users are reporting heat problems. The above driver is not very good but it is based on the latest source we have available. The source is from 2019. We need Realtek to release an updated, modernized version of the driver source code as the code for this driver is showing some age and is hard to maintain. Will Realtek release a new, improved version? I don't know.

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
- future Realtek support unknown
- no new source code releases since 2019, and that 2019 release was not a good driver
- uses a lot of power so using a powered hub may be a good idea
- produces a lot of heat, adapter needs a lot of vent holes
- expensive

Recommendation: Do not buy adapters based on this chipset. You will be disappointed. Adapters with the new mt7921au will meet or exceed the performance of this chipset in WiFi 5 AC 5 GHz mode plus you get WiFi 6e capability.

-----

##### `chipset - rtl8832bu / rtl8852bu - AX1800 - USB 3`

No driver is posted for this chipset at this time.

I am currently working on a driver for this chipset. Don't hold your breath. If you want WiFi 6, go get an adapter with the mt7921au chipset.

The Good:

- To be determined.

The Bad:

- The adapter I am using is multi-state and it appears that most adapters that use this chipset are multi-state. Not good.

Recommendation: If you want WiFi 6, go get an adapter with the mt7921au chipset. At this point, Realtek's support for WiFi 6 on Linux is far behind Mediatek's support and Mediatek has support for WiFi 6e. There is no WiFi 6e support from Realtek that I am aware of for usb chipsets.

-----

##### `chipset - rtl8832au / rtl8852au - AX1800 - USB 3`

No driver is posted for this chipset.

The rtl8852/32au chipset was the first AX class chipset that was available for use in USB WiFi adapters. Unfortunately, Realtek decided to support it with an out-of-kernel driver on Linux instead of doing the right thing and providing a mac80211 technology in-kernel driver. I tested the provided driver (v1.15.0.1). The results were terrible. As many of you know, I have a lot of USB WiFi adapters that I use and test. I cannot recall an experience as bad as this and I have been using USB WiFi adapters for many years. I experienced numerous system lockups that required me to pull the plug to get things going again. Additionally many features are simply not working. Power saving does not work. DFS channels do not work in AP mode. WPA3 did not work in any mode. I saw problems in basic client mode that I cannot explain. The driver is VERY BAD. Avoid adapters based on the 8852/32au chipset.

The Good:

- Nothing.

The Bad:

- A long list of bad.
- The adapter I tested is multi-state and it appears that most adapters that use this chipset are multi-state. Not good.

Recommendation: AVOID adapters based on this chipset. You will be disappointed. The driver is an out-of-kernel driver that is not consistent with Linux Wireless standards and it is a terrible driver. Recommend Linux uders seek out usb wifi adapters that use the mt7921au chipset if seeking an adapter that is WiFi 6 capable.

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
