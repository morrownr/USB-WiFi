2022-10-19

## USB_WiFi_Adapter_out-of-kernel_drivers_for_Linux

Note: The below list is ranked in order by quality of driver with best at the top. The best overall Realtek drivers currently are the 8812au, the 8821au (8811au and 8821au chipsets),  the 8821cu (8811cu and 8821cu chipsets) and the 88x2bu (8812bu and 8822bu chipsets).  These drivers perform reasonably well in all supported modes that I have been able to test. I concentrate my testing on client (managed), AP and monitor modes. The fastest driver in managed mode is the 88x2bu (8812bu and 8822bu chipsets). My advice, for Linux users needing to buy a new adapter, is to give preference to Mediatek chipset based adapters because the Mediatek drivers are based on Linux Wireless Standards (mac80211) and are maintained in the kernel. This makes the Mediatek based adapters much more troublefree in the long run. If you are unable to find an adapter based on Mediatek chipsets, then I recommend adapters based on these chipsets (in order): 8812au, 8811au, 8811cu and 8812bu. I currently recommend you AVOID adapters based on the Realtek 8814au, 8832au and 8852au chipsets as the drivers are not good and I am not seeing anything from Realtek that would indicate things are going to change.

Note: Remember that Realtek out-of-kernel drivers require you to find, download, compile and install the driver source code. The below links provide a lot of information, including information about supported adapters. Nine total chipsets are supported with the listed five drivers.

-----

Recent changes:

- 2022-10-08 - added note regarding 8821cu based adapters
- 2022-04-24 - moved Realtek information into this separate document
- 2022-03-07 - changes to reflect a new 8821cu driver
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

Recommendation: This chipset doesn't provide any significant advantages over the mt7612u chipset and the driver for the mt7612u chipset is far superior and is professionally maintained in the Linux kernel.

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

Recommendation: This chipset doesn't provide any significant advantages over the mt7610u chipset and the driver for the mt7610u chipset is professionally maintained in the Linux kernel.


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

- use caution buying adapters with the 8821cu chipset as some users have reported issues that could not be fixed. Suspect bad internal firmware.
- many adapter using these chipsets are multi-state.
- no virtual interface (VIF) support
- no support for set_wiphy_netns
- no support for 4addr
- the lack of an in-kernel, Linux Wireless Standards (mac80211) compliant driver makes this chipset problematic
- the really bad quality of some adapters made with this chipset means you need to reseach before buying

Recommendation: While adapters with this chipset are readily available at low prices, the chipset doesn't provide any advantages over the mt7610u chipset and the driver for the mt7610u chipset is professionally maintained in the Linux kernel.

-----

##### chipsets - rtl8812bu and rtl8822bu - AC1200 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8812BU and RTL8822BU Chipsets](https://github.com/morrownr/88x2bu-20210702)

The rtl8812bu chipset may see future in-kernel driver support based on the work being done on the rtw88 in-kernel driver. This chipset tends to run cool, which is good. Adapters based on this chipset are readily available at low prices but beware of poor quality adapters made by some adapter makers. Read the reviews before buying. The driver in the above link works very well with this chipset.

The Good:

- very fast in managed (client) mode (for an AC1200 chipset)
- AP mode works well except with RasPi4B (unable to determine the problem)
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

Recommendation: While adapters with this chipset are readily available at low prices, the chipset doesn't provide any significant advantages over the mt7612u chipset and the driver for the mt7612u chipset is far superior and is professionally maintained in the Linux kernel.

-----

##### chipset - rtl8814au - AC1900 - USB 3
[Linux Driver for USB WiFi Adapters that use the RTL8814AU Chipset](https://github.com/morrownr/8814au)

The rtl8814au chipset is an aging chipset that will likely never be supported by an in-kernel driver which leaves users dependent on Realtek to release future out-of-kernel source code. This makes buying adapters based on this chipset somewhat risky for Linux users. Adapters based on this chipset can really push data at high speed and are still available but are relatively expensive. They need a pretty good amount of power so a powered USB 3 hub may be a good idea. This chipset builds a lot of heat so look for adapters that have plenty of vent holes and search reviews to see if users are reporting heat problems. The above driver is not very good but it is based on the latest source we have available. The source is from 2019. We need Realtek to release an updated, modernized version of the driver source code as the code for this driver is showing some age and is hard to maintain. Will Realtek release a new, improved version? I don't know.

The Good:

- managed (client) mode is reasonably good
- master (AP) is reasonably good
- monitor mode, including injection and deauth, work but there are some problems with capture

The Bad:

- many resellers advertize Linux support but that is deceptive at best (it certainly is the case with this chipset)
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

##### chipset - rtl8832au / rtl8852au - AX1800 - USB 3

No driver is posted for this chipset.

The rtl8832au chipset is a somewhat new chipset and was the first AX class chipset that was available for use in USB WiFi adapters. Unfortunately, Realtek decided to support it with an out-of-kernel driver instead of doing the right thing and providing a mac80211 technology in-kernel driver. I have been testing the provided driver (v1.15.0.1). The results are not good. As many of you know, I have a lot of USB WiFi adapters that I test. I cannot recall an experience as bad as this and I have been using USB WiFi adapters for many years. I experienced numerous system lockups requiring me to pull the plug to get things going again. Additionally many features are simply not working. Power saving does not work. DFS channels do not work in AP mode. USB mode control is problematic. WPA3 does not work in any mode. I see problems in basic client mode that I cannot explain. This is a VERY BAD driver. Avoid adapters based on the 8832au chipset.

The Good:

- I'm still looking for the good.
-
The Bad:

- A lot of bad here.

Recommendation: AVOID adapters based on this chipset. You will be disappointed.

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
