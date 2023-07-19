## USB WiFi chipset information for Linux

This document is a summary that includes information about many modern USB WiFi chipsets.

Not all USB WiFi adapters are created equally.  While the chipset and driver
dictate which WiFi features are supported (e.g. which frequency bands), the
vendor of the adapter is free to decide on the performance of the antenna(s),
the power of the amp and whether the device requires mode switching and so on.

Chipset           | Interface | Standard | 2.4 | 5   | 6   | Linux<br>In-Kernel<br>Driver | AP Mode          | Monitor Mode     |
------------------|-----------|----------|-----|-----|-----|:----------------------------:|:----------------:|:----------------:|
Mediatek MT7922u  | USB3      | WiFi 6E  |  40 |  ?  | 160 |:heavy_check_mark: 5.16+      |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8852cu | USB3      | WiFi 6E  |  40 |  ?  | 160 |:x: [6]                       |                  |                  |
Realtek RTL8832cu | USB3      | WiFi 6E  |  40 |  ?  | 160 |:x:                           | ?                | ?                |
Mediatek MT7921au | USB3      | WiFi 6E  |  40 |  80 |  80 |:heavy_check_mark: 5.18+      |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8852bu | USB3      | WiFi 6   |  40 |  80 |  N  |:x: [4] [6]                   |                  |                  |
Realtek RTL8832bu | USB3      | WiFi 6   |  40 |  80 |  N  |:x: [4]                       |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8852au | USB3      | WiFi 6   |  40 |  80 |  N  |:x: - avoid [2]               | bad driver       | bad driver       |
Realtek RTL8832au | USB3      | WiFi 6   |  40 |  80 |  N  |:x: - avoid                   | bad driver       | bad driver       |
Realtek RTL8814au | USB3      | WiFi 5   |  40 |  80 |  N  |:x: - avoid                   | old driver       | old driver       |
Mediatek MT7662u  | USB3      | WiFi 5   |  40 |  80 |  N  |:heavy_check_mark: 5.9+ [6]   |:heavy_check_mark:|:heavy_check_mark:|
Mediatek MT7612u  | USB3      | WiFi 5   |  40 |  80 |  N  |:heavy_check_mark: 4.19+      |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8822bu | USB2 [5]  | WiFi 5   |  40 |  80 |  N  |:heavy_check_mark: 6.2+ [3][6]|:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8812bu | USB3      | WiFi 5   |  40 |  80 |  N  |:heavy_check_mark: 6.2+ [3]   |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8822cu | USB2 [5]  | WiFi 5   |  40 |  80 |  N  |:heavy_check_mark: 6.2+ [3][6]|:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8812cu | USB3      | WiFi 5   |  40 |  80 |  N  |:heavy_check_mark: 6.2+ [3]   |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8812au | USB3      | WiFi 5   |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Mediatek MT7610u  | USB2      | WiFi 5   |  20 |  80 |  N  |:heavy_check_mark: 4.19+ [6]  |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8821cu | USB2      | WiFi 5   |  40 |  80 |  N  |:heavy_check_mark: 6.2+ [3]   |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8811cu | USB2      | WiFi 5   |  40 |  80 |  N  |:heavy_check_mark: 6.2+ [3]   |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8821au | USB2      | WiFi 5   |  40 |  80 |  N  |:x: [6]                       |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8811au | USB2      | WiFi 5   |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT3573     | USB2      | WiFi 4   |  40 |  40 |  N  |:heavy_check_mark: 3.12+      |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT5572     | USB2      | WiFi 4   |  40 |  40 |  N  |:heavy_check_mark: 3.10+      |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT3572     | USB2      | WiFi 4   |  40 |  40 |  N  |:heavy_check_mark: 2.6.31+    |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT5372     | USB2      | WiFi 4   |  40 |  N  |  N  |:heavy_check_mark: 3.0+       |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8192cu | USB2      | WiFi 4   |  40 |  N  |  N  |:heavy_check_mark: 2.6.33+    |:heavy_check_mark:|:heavy_check_mark:|
Mediatek MT7601u  | USB2      | WiFi 4   |  40 |  N  |  N  |:heavy_check_mark: 4.2+       |:x:               | limited          |
Ralink RT5370     | USB2      | WiFi 4   |  40 |  N  |  N  |:heavy_check_mark: 3.0+       |:heavy_check_mark:|:heavy_check_mark:|
Atheros AR9271    | USB2      | WiFi 4   |  40 |  N  |  N  |:heavy_check_mark: 2.6.35+    |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT3070     | USB2      | WiFi 4   |  40 |  N  |  N  |:heavy_check_mark: 2.6.31+    |:heavy_check_mark:|:heavy_check_mark:|

## Mediatek MT7921AU and MT7922A (in-kernel driver is mt7921u) (WiFi 6E)

Adapters based on the mt7921au chipset have been available since July of 2022.

[1] USB support added with the mt7921u driver in kernel 5.18. Internal cards are supported by the mt7921e driver which has been in the kernel since 5.12.

[2] AP mode support added to the mt7921u driver in kernel 5.19. Firmware update is required also.

-----

## Realtek RTW88 (in-kernel driver) (WiFi 5)

[3] In-kernel support for the following chipsets is now in kernel 6.2 and later:

```
rtl8822bu
rtl8812bu
rtl8821cu
rtl8811cu
rtl8822cu
rtl8812cu
```

-----

[4] I have a copy of the out-of-kernel driver and now have an adapter to test. Work is in progress but no timeline is set.

-----

[5] https://www.realtek.com/en/products/communications-network-ics/item/rtl8822bu

-----

[6] Chipset has bluetooth turned on. Recommend Linux user avoid chipsets with bluetooth turned on.

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----


