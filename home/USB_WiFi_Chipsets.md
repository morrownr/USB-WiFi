2022-06-10

## USB WiFi chipset information for Linux

This document is a summary of the available USB WiFi chipsets for Linux.

Not all USB WiFi adapters are created equally.  While the chipset and driver
dictate which WiFi features are supported (e.g. which frequency bands), the
vendor of the adapter is free to decide on the performance of the antenna(s),
the power of the amp and whether the device requires mode switching and so on.

Chipset           | Interface[^1]   | Standard   | MIMO | 2.4 | 5   | 6   | Linux<br>In-Kernel<br>Driver | AP Mode          | Monitor Mode     |
------------------|-----------------|------------|:----:|:---:|:---:|:---:|:----------------------------:|:----------------:|:----------------:|
Mediatek MT7921u [1]  | USB3 / 5 Gbps   | WiFi 6/6e  | 2x2  |  40 |  80 |  80 |:heavy_check_mark:            |:heavy_check_mark: [2]|:heavy_check_mark:|
Realtek RTL8852au | USB3 / 5 Gbps   | WiFi 6     | 2x2  |  40 |  80 |  N  |:x: - avoid                   | bad driver       | bad driver       |
Realtek RTL8832au | USB3 / 5 Gbps   | WiFi 6     | 2x2  |  40 |  80 |  N  |:x: - avoid                   | bad driver       | bad driver       |
Mediatek MT7612u  | USB3 / 5 Gbps   | WiFi 5     | 2x2  |  40 |  80 |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8814au | USB3 / 5 Gbps   | WiFi 5     | 3x3  |  40 |  80 |  N  |:x: - avoid                   | old driver       | old driver       |
Realtek RTL8822bu | USB3 / 5 Gbps   | WiFi 5     | 2x2  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8812bu | USB3 / 5 Gbps   | WiFi 5     | 2x2  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8812au | USB3 / 5 Gbps   | WiFi 5     | 2x2  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Mediatek MT7610u  | USB2 / 480 Mbps | WiFi 5     | 1x1  |  20 |  80 |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8821au | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8821cu | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8811au | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8811cu | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT5572     | USB2 / 480 Mbps | WiFi 4     | 2x2  |  40 |  40 |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT3572     | USB2 / 480 Mbps | WiFi 4     | 2x2  |  40 |  40 |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT5372     | USB2 / 480 Mbps | WiFi 4     | 2x2  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8192cu | USB2 / 480 Mbps | WiFi 4     | 2x2  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Mediatek MT7601u  | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:x:               | limited          |
Ralink RT5370     | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Atheros AR9271    | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT3070     | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|

## Mediatek MT7921U

:sob: 2022-06-10 - Adapters are Not yet available for purchase. Expect availability to start during the second half of 2002.

[1] 2022-06-10 - USB support added to mt7921 driver in kernel 5.18.

[2] 2022-06-10 - AP mode support added to mt7921 driver in kernel 5.19. Firmware update is required also.

