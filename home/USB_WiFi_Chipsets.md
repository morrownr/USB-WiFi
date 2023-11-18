## USB WiFi chipset information for Linux

This document is a summary that includes information about many modern USB WiFi chipsets.

Not all USB WiFi adapters are created equally.  While the chipset and driver
dictate which WiFi features are supported (e.g. which frequency bands), the
vendor of the adapter is free to decide on the performance of the antenna(s),
the power of the amp and whether the device requires mode switching and so on.

| Chipset           | Interface | Standard | Maximum<br>Channel<br>Width   | Linux<br>In-Kernel<br>Driver | AP Mode        | Monitor Mode   | Recommended<br>For<br>Linux |
|:------------------:|-----------|----------|:-----:|:----------------------------:|:----------------:|:----------------:|:-----------------:|
Mediatek MT7925   | USB3      | WiFi 7  |  160   |:heavy_check_mark: 6.7+       |:heavy_check_mark:|:heavy_check_mark:| [4] |
Realtek RTL8852cu | USB2      | WiFi 6E  |  160  |:x: [6]                       |                  |                  | No  |
Realtek RTL8832cu | USB3      | WiFi 6E  |  160  |:x:                           |                  |                  | No  |
Mediatek MT7921au | USB3      | WiFi 6E  |   80  |:heavy_check_mark: 5.18+      |:heavy_check_mark:|:heavy_check_mark:| Yes |
Realtek RTL8852bu | USB       | WiFi 6   |   80  |:x: [6]                       |                  |                  | No  |
Realtek RTL8832bu | USB3      | WiFi 6   |   80  |:x:                           |:heavy_check_mark:|:heavy_check_mark:| No  |
Realtek RTL8852au | USB2      | WiFi 6   |   80  |:x: - avoid [2]               | bad driver       | bad driver       | No  |
Realtek RTL8832au | USB3      | WiFi 6   |   80  |:x: - avoid                   | bad driver       | bad driver       | No  |
Realtek RTL8814au | USB3      | WiFi 5   |   80  |:x: - avoid                   | old driver       | old driver       | No  |
Mediatek MT7662u  | USB2      | WiFi 5   |   80  |:heavy_check_mark: 5.9+ [6]   |:heavy_check_mark:|:heavy_check_mark:| No  |
Mediatek MT7612u  | USB3      | WiFi 5   |   80  |:heavy_check_mark: 4.19+      |:heavy_check_mark:|:heavy_check_mark:| Yes |
Realtek RTL8822bu | USB2 [5]  | WiFi 5   |   80  |:heavy_check_mark: 6.2+ [3][6]|:heavy_check_mark:|:heavy_check_mark:| No  |
Realtek RTL8812bu | USB3      | WiFi 5   |   80  |:heavy_check_mark: 6.2+ [3]   |:heavy_check_mark:|:heavy_check_mark:| Yes |
Realtek RTL8822cu | USB2 [5]  | WiFi 5   |   80  |:heavy_check_mark: 6.2+ [3][6]|:heavy_check_mark:|:heavy_check_mark:| No  |
Realtek RTL8812cu | USB3      | WiFi 5   |   80  |:heavy_check_mark: 6.2+ [3]   |:heavy_check_mark:|:heavy_check_mark:| No  |
Realtek RTL8812au | USB3      | WiFi 5   |   80  |:x:                           |:heavy_check_mark:|:heavy_check_mark:| No  |
Mediatek MT7610u  | USB2      | WiFi 5   |   80  |:heavy_check_mark: 4.19+      |:heavy_check_mark:|:heavy_check_mark:| Yes |
Realtek RTL8821cu | USB2      | WiFi 5   |   80  |:heavy_check_mark: 6.2+ [3][6]|:heavy_check_mark:|:heavy_check_mark:| No  |
Realtek RTL8811cu | USB2      | WiFi 5   |   80  |:heavy_check_mark: 6.2+ [3]   |:heavy_check_mark:|:heavy_check_mark:| No  |
Realtek RTL8821au | USB2      | WiFi 5   |   80  |:x: [6]                       |:heavy_check_mark:|:heavy_check_mark:| No  |
Realtek RTL8811au | USB2      | WiFi 5   |   80  |:x:                           |:heavy_check_mark:|:heavy_check_mark:| No  |
Ralink RT3573     | USB2      | WiFi 4   |   40  |:heavy_check_mark: 3.12+      |:heavy_check_mark:|:heavy_check_mark:| Yes |
Ralink RT5572     | USB2      | WiFi 4   |   40  |:heavy_check_mark: 3.10+      |:heavy_check_mark:|:heavy_check_mark:| Yes |
Ralink RT3572     | USB2      | WiFi 4   |   40  |:heavy_check_mark: 2.6.31+    |:heavy_check_mark:|:heavy_check_mark:| Yes |
Ralink RT5372     | USB2      | WiFi 4   |   40  |:heavy_check_mark: 3.0+       |:heavy_check_mark:|:heavy_check_mark:| Yes |
Realtek RTL8192cu | USB2      | WiFi 4   |   40  |:heavy_check_mark: 2.6.33+    |:heavy_check_mark:|:heavy_check_mark:| Yes |
Mediatek MT7601u  | USB2      | WiFi 4   |   40  |:heavy_check_mark: 4.2+       |:x:               | limited          | Yes |
Ralink RT5370     | USB2      | WiFi 4   |   40  |:heavy_check_mark: 3.0+       |:heavy_check_mark:|:heavy_check_mark:| Yes |
Atheros AR9271    | USB2      | WiFi 4   |   40  |:heavy_check_mark: 2.6.35+    |:heavy_check_mark:|:heavy_check_mark:| Yes |
Ralink RT3070     | USB2      | WiFi 4   |   40  |:heavy_check_mark: 2.6.31+    |:heavy_check_mark:|:heavy_check_mark:| Yes |

## Mediatek MT7921AU and MT7922AU (in-kernel driver is mt7921u) (WiFi 6E)

Adapters based on the mt7921au chipset have been available since July of 2022.

[1] USB support added with the mt7921u driver in kernel 5.18. Internal cards are supported by the mt7921e driver which has been in the kernel since 5.12.

[2] AP mode support added to the mt7921u driver in kernel 5.19. Firmware update is required also.

-----

## Realtek RTW88 (in-kernel driver) (WiFi 5)

[3] In-kernel support for the following chipsets is now in kernel 6.2 and later:

```
rtl8822bu
rtl8812bu (recommended)
rtl8821cu
rtl8811cu
rtl8822cu
rtl8812cu
```
 
-----

[4] Chipset is not available to USB adapter makers yet. Driver is going into the Linux kernel soon:

https://lwn.net/Articles/939966/

-----

[5] https://www.realtek.com/en/products/communications-network-ics/item/rtl8822bu

-----

[6] Chipset has bluetooth turned on. Recommend Linux user avoid chipsets with bluetooth turned on.

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----


