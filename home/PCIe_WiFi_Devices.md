2022-04-26

## PCIe WiFi card information for Linux

Note: This document is under construction. If you see mistakes or have information to add, please get in touch via `Issues`. I
almost exclusively use USB WiFi adapters and am not knowledgable about WiFi cards. The only card I have is in a laptop computer. It
is based on the Mediatek MT7921 chipset and works really well. 

There is additional information below the summary table.

Chipset               | Interface   | Standard | MIMO | 2.4 | 5   | 6   | Linux In-Kernel Driver | AP Mode              | Monitor Mode     |
----------------------|-------------|----------|:----:|:---:|:---:|:---:|:----------------------:|:--------------------:|:----------------:|
Mediatek MT7922       | PCIe 2.1 x? | WiFi 6E  | 2x2  |  40 | 160 | 160 |:heavy_check_mark:      |:heavy_check_mark: [1]|:heavy_check_mark:|
Intel AX210           | PCIe ?.0 x? | WiFi 6E  | 2x2  |  40 | 160 | 160 |:heavy_check_mark:      |2.4 Ghz only          | ?                |
Mediatek MT7921K      | PCIe 2.1 x? | WiFi 6E  | 2x2  |  40 |  80 |  80 |:heavy_check_mark:      |:heavy_check_mark: [1]|:heavy_check_mark:|
Mediatek MT7921       | PCIe 2.1 x? | WiFi 6   | 2x2  |  40 |  80 |  N  |:heavy_check_mark:      |:heavy_check_mark: [1]|:heavy_check_mark:|
Intel AX200           | PCIe ?.0 x? | WiFi 6   | 2x2  |  40 | 160 |  N  |:heavy_check_mark:      |2.4 Ghz only          | ?                |
Qualcomm (Atheros) [2]| PCIe ?      | WiFi 6   | ?    |  ?  |  ?  |  ?  |?                       |?                     | ?                |
Realtek RTL8852       | PCIe 2.0 x? | WiFi 6   | 2x2  |  40 |  80 |  N  |:heavy_check_mark:      |?                     | ?                |
Realtek RTL8832       | PCIe 2.0 x? | WiFi 6   | 2x2  |  40 |  80 |  N  |:heavy_check_mark:      |?                     | ?                |


[1] AP mode support was recently added to the mt7921 driver via firmware. Many
distros have not updated said firmware so you may have to do it yourself for now.

https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/log/mediatek

```
update firmware for MT7921 WiFi device
or
update firmware for mediatek bluetooth chip (MT7921)
```
[2] Need help to identify and provide information for Qualcomm chipsets.

When adding new devices, the WiFi Alliance have a
[useful search](https://www.wi-fi.org/product-finder-results?sort_by=certified)
to find the product certification, which lists supported frequencies,
bandwidths and other features.

# WiFi 6E (802.11ax)

Most 6E devices support Bluetooth as well, however Bluetooth is usually
provided via a USB connector which must plug in to a USB port on the
motherboard.  The cards generally do not include a PCIe USB chipset.

## Mediatek MT7922 -supported in the [MT7921 module](https://patchwork.kernel.org/project/linux-wireless/patch/27e39fd3c6d70837772e56f85bf9b01e8beeca47.1626370282.git.deren.wu@mediatek.com/)

:heavy_check_mark: In-kernel Linux support

Adds support for 160 MHz channels to 5 and 6 GHz bands.
Directly competes with Intel AX210, however it is a better choice over the Intel card
for soft AP use in the 5 and 6 GHz bands.

* [Vendor page](https://www.mediatek.com/products/products/broadband-wifi/mediatek-filogic-330)
* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=101441)

## Intel AX210

:heavy_check_mark: In-kernel Linux support

:warning: This device enforces Intel Location Aware Regulatory (LAR) which
prevents it from transmitting on the 5 and 6 GHz bands until it detects signals
from nearby WiFi access points.  LAR devices are very difficult to use as
software access points with hostapd, unless you only require them to provide a
WiFi network in the 2.4 GHz band.

This device has a good reputation for being reliable as a client device,
connecting to an existing WiFi network.

All variants use M.2 socket key E, and are not compatible with an M.2 socket
keyed M or B.

* AX210NGW: As above, M.2 2230 form factor
* AX210D2W: As above, M.2 1216 form factor

Further information:

* [Vendor specifications](https://ark.intel.com/content/www/us/en/ark/products/204836/intel-wifi-6e-ax210-gig.html)
* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=110324)
* [Wireless CAT](https://wikidevi.wi-cat.ru/Intel_Wi-Fi_6E_AX210_(AX210NGW))

## Mediatek MT7921K

:heavy_check_mark: In-kernel Linux support

:warning: Check the part number closely, only the parts ending with a K support
the 6 GHz band.

This card is a newer revision of the MT7921 with support for the 6 GHz band.
Unlike the Intel AX210 it does not support 160 MHz channels (maxing out at
80 MHz), however it uses the standard Linux regulatory framework so unlike
Intel devices, it will work as a software access point on the 5 and 6 GHz bands.

Supported frequencies:

* 2.4GHz: 2.412 - 2.472GHz
* 5GHz: 5.18 - 5.32GHz, 5.50 - 5.72GHz, 5.745 - 5.825GHz
* 6GHz: 5.955 - 6.415GHz, 6.435 - 6.525GHz, 6.525 - 6.875GHz, 6.875 - 7.115GHz

Transfer rates:

* 802.11b: up to 11 Mbps
* 802.11a/g: up to 54 Mbps
* 802.11n: up to 300 Mbps
* 802.11ac: up to 866.7 Mbps
* 802.11ax: up to 1201.0 Mbps

Number of channels:

* 2.4GHz
  * 802.11b, 802.11g, 802.11n (HT20), VHT20, 802.11ax (HE20): 13
  * 802.11n (HT40), VHT40, 802.11ax (HE40): 9
* 5GHz
  * 802.11a, 802.11n (HT20), 802.11ac (VHT20), 802.11ax (HE20): 25
  * 802.11n (HT40), 802.11ac (VHT40), 802.11ax (HE40): 12
  * 802.11ac (VHT80), 802.11ax (HE80): 6
* 6GHz
  * 802.11ax (HE20): 59
  * 802.11ax (HE40): 29
  * 802.11ax (HE80): 14

Further information:

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=102893)
* [Wireless CAT](https://wikidevi.wi-cat.ru/MediaTek_MT7921K_Reference_Design)

# WiFi 6 (802.11ax)

## Intel AX200

:heavy_check_mark: In-kernel Linux support

:warning: This device enforces Intel Location Aware Regulatory (LAR) which
prevents it from transmitting on the 5 and 6 GHz bands until it detects signals
from nearby WiFi access points.  LAR devices are very difficult to use as
software access points with hostapd, unless you only require them to provide a
WiFi network in the 2.4 GHz band.

This device has been superseded by the AX210, which adds support for the
6 GHz band.

Reports are that it works very well as a client connecting to an existing
wireless network.

Further information:

* [Vendor specifications](https://www.intel.com.au/content/www/au/en/products/sku/189347/intel-wifi-6-ax200-gig/specifications.html)
* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=105436)
* [Wireless CAT](https://wikidevi.wi-cat.ru/Intel_Wi-Fi_6_AX200_(AX200NGW))

## Realtek RTL8852


Further information:

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=101434)
* [Wireless CAT](https://wikidevi.wi-cat.ru/Realtek_RTL8852AE_Combo_Module)

## Realtek RTL8832


## Mediatek MT7921

:heavy_check_mark: In-kernel Linux support

This device has been superseded by the MT7921K, which adds support for the
6 GHz band.

Further information:

* [WiFi Alliance certification PDF](https://api.cert.wi-fi.org/api/certificate/download/public?variantId=16519)
* [Wireless CAT](https://wikidevi.wi-cat.ru/MediaTek_MT7921_Reference_Design)

# WiFi 5 (802.11ac)
