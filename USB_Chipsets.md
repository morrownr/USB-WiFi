2022-03-06

## USB chipset information for Linux

Note: This document is under construction and there are currently mistakes that
need to be corrected so please ask in issues if you need clarification. If you would
like to improve it, please do so.

This document is a summary of the available USB WiFi chipsets and how well they
work in Linux.  The idea is to find the chipsets that support all the features
you desire, then look for USB devices that use these chipsets.

Not all USB devices are created equal, however.  While the chipset dictates
which WiFi features are supported (e.g. which frequency bands), the vendor of
the USB device is free to decide on the performance of the antenna(s) used,
whether the device requires mode switching before it can be used, and so on.

Once you have decided on a chipset, see the [main device list](README.md) for a
subset of available devices that have been tested.

For more details on each chipset, see the entry below the summary table.

Chipset           | Interface[^1]   | Standard   | MIMO | 2.4 | 5   | 6   | Linux<br>In-Kernel<br>Driver | AP Mode          | Monitor Mode     |
------------------|-----------------|------------|:----:|:---:|:---:|:---:|:----------------------------:|:----------------:|:----------------:|
Mediatek MT7922   | USB3 / 5 Gbps   | WiFi 6E    | 2x2  |  40 | 160 | 160 | ?                            | ?                | ?                |
Mediatek MT7921u  | USB3? / ? Gbps  | WiFi 6(E?) | 2x2  |  40 |  80 |  80 |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8852au | USB3            | WiFi 6     | 2x2  |  40 |  80 |  N  |:x:                           | ?                | ?                |
Realtek RTL8832au | USB3            | WiFi 6     | 2x2  |  40 |  80 |  N  |:x:                           | ?                | ?                |
Mediatek MT7668u  | USB2            | WiFi 5     | 2x2  |  40 |  80 |  N  |:heavy_check_mark:            |:heavy_check_mark:| ?                |
Mediatek MT7612u  | USB3 / 5 Gbps   | WiFi 5     | 2x2  |  40 |  80 |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8814au | USB3 / 5 Gbps   | WiFi 5     | 3x3  |  40 |  80 |  N  |:x:                           | ?                | ?                |
Realtek RTL8822bu | USB3 / 5 Gbps   | WiFi 5     | 2x2  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8812bu | USB3 / 5 Gbps   | WiFi 5     | 2x2  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8812au | USB3 / 5 Gbps   | WiFi 5     | 2x2  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Mediatek MT7610u  | USB2 / 480 Mbps | WiFi 5     | 1x1  |  20 |  80 |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8831   | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           | ?                | ?                |
Realtek RTL8821au | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8821au | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8811au | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8811cu | USB2 / 480 Mbps | WiFi 5     | 1x1  |  40 |  80 |  N  |:x:                           |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT5572     | USB2 / 480 Mbps | WiFi 4     | 2x2  |  40 |  40 |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT5372     | USB2 / 480 Mbps | WiFi 4     | ?    |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Ralink RT5370     | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Atheros AR9271    | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Mediatek MT7601u  | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:x:               |:x:               |
Ralink RT3070     | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8192cu | USB2 / 480 Mbps | WiFi 4     | 2x2  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Realtek RTL8723   | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            | ?                | ?                |

[^1]: The interface column lists the fastest interface natively supported by the
chipset.  You should still confirm the device you use operates at this speed, as
for example some USB 3.0 capable devices are shipped with only USB 2.0
connectors, limiting their bandwidth.

# WiFi 6E (802.11abgn/ac/ax)

## Mediatek MT7922

:sob: Not yet available (2022-03-08).

:heavy_check_mark: Probable in-kernel Linux support

:information_source: Available in both [PCIe](PCIe_WiFi_Devices.md) and USB versions.

Supersedes MT7921.  Adds support for 160 MHz channels to 5 and 6 GHz bands.

* [Vendor page](https://www.mediatek.com/products/products/broadband-wifi/mediatek-filogic-330)
* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=101441)

## Mediatek MT7921U

:sob: Not yet available (2022-03-08).

:warning: A [patch was submitted](https://patchwork.kernel.org/project/linux-wireless/patch/6df14f076220c0cbc1d32939cd8be8cb33d7b498.1646235785.git.lorenzo@kernel.org/)
for inclusion in the Linux `mt76` driver.  It has not yet been merged.

The USB version of the [MT7921K](PCIe_WiFi_Devices.md#Mediatek%20MT7921K).

* WiFi Alliance certification PDF ([Not yet certified](https://www.wi-fi.org/product-finder-results?sort_by=certified&sort_order=desc&keywords=MT7921U))

# WiFi 6 (802.11abgn/ac/ax)

## Realtek RTL8852

:x: Requires out-of-tree drivers

:information_source: Available in both [PCIe](PCIe_WiFi_Devices.md) and USB versions.

Seems to be the same as RTL8832 but with the addition of Bluetooth.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=106391)

## Realtek RTL8832

:x: Requires out-of-tree drivers

:information_source: Available in both [PCIe](PCIe_WiFi_Devices.md) and USB versions.

Same as RTL8812 but with the addition of WiFi 6 features.  Only seems to be used
in one router, and superseded by the RTL8852.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=104762)

# WiFi 5 (802.11abgn/ac)

## Mediatek MT7668U

:heavy_check_mark: In-kernel Linux support (`mt76` driver)

Same as MT7612U but with Bluetooth 5.0 LE support.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=107280)

## Mediatek MT7612U

:heavy_check_mark: In-kernel Linux support (`mt76` driver)

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=20441)

## Realtek RTL8814

:x: Requires out-of-tree drivers

RTL8814AU is the USB version.  Apparently rated AC1900.

* No WiFi Alliance certification

## Realtek RTL8822

:x: Requires out-of-tree drivers

Same as RTL8812 but with the addition of Bluetooth.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=35078)

## Realtek RTL8812

:x: Requires out-of-tree drivers

:information_source: Available in both [PCIe](PCIe_WiFi_Devices.md) and USB versions.

RTL8812BU is the USB version of the PCIe RTL8812AE.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=22430)

## Mediatek MT7610U

:heavy_check_mark: In-kernel Linux support (`mt76` driver)

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=20043)

# WiFi 4 (802.11bgn)

## Realtek RTL8831

:x: Requires out-of-tree drivers

* No WiFi Alliance certification

## Realtek RTL8821

:x: Requires out-of-tree drivers

* No WiFi Alliance certification

## Realtek RTL8811

:x: Requires out-of-tree drivers

* No WiFi Alliance certification

## Realtek RTL8192

:heavy_check_mark: In-kernel Linux support

One of the few Realtek devices to have in-kernel support.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=19121)

## Ralink RT5572

:heavy_check_mark: In-kernel Linux support

:information_source: Dual band 2.4 GHz + 5 GHz.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=19124)

## Ralink RT5372

:heavy_check_mark: In-kernel Linux support

:warning: Single band 2.4 GHz only

* WiFi Alliance certification PDF ([Not certified](https://www.wi-fi.org/product-finder-results?sort_by=certified&sort_order=desc&keywords=RT5372))

## Ralink RT5370

:heavy_check_mark: In-kernel Linux support

:warning: Single band 2.4 GHz only

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=5397)

## Realtek RTL8723

:heavy_check_mark: In-kernel Linux support

:warning: Single band 2.4 GHz only

One of the few Realtek devices to have in-kernel support.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=30149)
