2022-04-08

## USB WiFi chipset information for Linux

This document is a summary of the available USB WiFi chipsets and how well they
work in Linux.  The idea is to find the chipsets that support all the features
you desire, then look for USB devices that use these chipsets.

Not all USB devices are created equal, however.  While the chipset dictates
which WiFi features are supported (e.g. which frequency bands), the vendor of
the USB device is free to decide on the performance of the antenna(s) used,
whether the device requires mode switching before it can be used, and so on.

Once you have decided on a chipset, see the [main device list](README.md) for a
subset of available devices that have been tested or are known to work well.

For more details on each chipset, see the entry below the summary table.

Chipset           | Interface[^1]   | Standard   | MIMO | 2.4 | 5   | 6   | Linux<br>In-Kernel<br>Driver | AP Mode          | Monitor Mode     |
------------------|-----------------|------------|:----:|:---:|:---:|:---:|:----------------------------:|:----------------:|:----------------:|
Mediatek MT7921u  | USB3 / 5 Gbps   | WiFi 6/6e  | 2x2  |  40 |  80 |  80 |:heavy_check_mark:            |:heavy_check_mark:*|:heavy_check_mark:|
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
Ralink RT5370     | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Atheros AR9271    | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|
Mediatek MT7601u  | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:x:               | limited          |
Ralink RT3070     | USB2 / 480 Mbps | WiFi 4     | 1x1  |  40 |  N  |  N  |:heavy_check_mark:            |:heavy_check_mark:|:heavy_check_mark:|

[^1]: The interface column lists the fastest interface natively supported by the
chipset.  You should still confirm the device you use operates at this speed, as
for example some USB 3.0 capable devices are shipped with only USB 2.0
connectors, limiting their bandwidth.

## Mediatek MT7921U

:sob: Not yet available (2022-03-08).

:warning: A [patch was submitted](https://patchwork.kernel.org/project/linux-wireless/patch/6df14f076220c0cbc1d32939cd8be8cb33d7b498.1646235785.git.lorenzo@kernel.org/)
for inclusion in the Linux `mt76` driver.

* 2021-04-01 - AP mpde supporting going into the kernel at this time.

## Realtek RTL8852

:x: Requires out-of-tree drivers (Avoid adapters with this chipset. The Realtek provided driver is bad.)

:information_source: Available in both [PCIe](PCIe_WiFi_Devices.md) and USB versions.

Seems to be the same as RTL8832 but with the addition of Bluetooth.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=106391)

## Realtek RTL8832

:x: Requires out-of-tree drivers (Avoid adapters with this chipset. The Realtek provided driver is bad.)

:information_source: Available in both [PCIe](PCIe_WiFi_Devices.md) and USB versions.

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=104762)

## Mediatek MT7612U

:heavy_check_mark: In-kernel Linux support (`mt76` driver)

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=20441)

## Realtek RTL8814

:x: Requires out-of-tree drivers (Avoid adapters with this chipset. The Realtek provided driver is old and problematic.)

RTL8814AU is the USB version.  AC1900.

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
