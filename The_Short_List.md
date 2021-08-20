2021-08-20

The Short List - Superstar USB WiFi Adapters for Linux

Note: This list is subject to change as new information becomes available.  Your input is welcome. 

-----

```
Adapter                      Chipset / Class  / Bands       USB  WPA3  Range     State
```

-----

```
Alfa AWUS036ACM [1] [2]      mt7612u / AC1200 / 2.4, 5      USB3  Yes  Long      Single

COMFAST CF-WU785AC [1] [2]   mt7612u / AC1300 / 2.4, 5      USB3  Yes  Long      Multi

TEROW ROW02FD [1] [2]        mt7612u / AC1200 / 2.4, 5      USB3  Yes  Long      Multi

COMFAST CF-WU782AC [2]       mt7612u / AC1300 / 2.4, 5      USB3  Yes  Long      Multi

Netgear A6210 [1]            mt7612u / AC1200 / 2.4, 5      USB3  Yes  Medium    Single

Linksys AE6000 [1]           mt7610u / AC580  / 2.4, 5      USB2  Yes  Medium    Single

Alfa AWUS036ACHM [1]         mt7610u / AC600  / 2.4, 5      USB2  Yes  Very Long Single

Panda PAU09                  rt5572  / N600   / 2.4, 5      USB2  Yes  Long      Single

Panda PAU06                  rt5372  / N300   / 2.4         USB2  Yes  Medium    Single

Panda PAU05                  rt5372  / N300   / 2.4         USB2  Yes  Medium    Single

Panda PAU03 [1] (nano)       rt5370  / N150   / 2.4         USB2  Yes  Short     Single        

Alfa AWUS036NHA              ar9271  / N150   / 2.4         USB2  Yes  Long      Single

WiFi Nation WN-H3            ar9271  / N150   / 2.4         USB2  Yes  Long      Single

Panda PAU08                  rt3070  / N150   / 2.4         USB2  Yes  Long      Single

Alfa AWUS036NEH              rt3070  / N150   / 2.4         USB2  Yes  Long      Single

DM-Digital [1] [3]           mt7601u / N150   / 2.4         USB2  Yes  Medium    Single

EDUP EP-8551 [1] [3]         mt7601u / N150   / 2.4         USB2  Yes  Long      Single
```

-----

[Click here for online links to all of the above adapters. The list is rather long so please scroll until you find what you want. Good luck.](https://github.com/morrownr/USB-WiFi)

-----

```
[1] I have first hand experience with this adapter.
[2] Excellent for 5 GHz AP mode (works well with a Raspberry Pi 4B)
[3] Only supports managed and monitor modes. (low cost)

Criteria to make The Short List: 

1. Uses an In-kernel driver (adapter is plug and play).
2. Has either a well documented track record or my own testing experience.
3. Is available to purchase as a new product.

USB WiFi adapters come in various shapes, sizes and speeds. Their capabilities
can vary greatly. The adapter that you pick needs to be chosen based on its
ability to do the job that you need it to do. Below are some recommendations
based on specific use cases:

- If you want to build your own WiFi Router/Access Point/Hotspot: (master (AP) mode)

5 GHZ: Alfa AWUS036ACM, COMFAST CF-WU785AC, COMFAST CF-WU782AC, TEROW ROW02FD

2.4 GHz only: Alfa AWUS036NHA, Alfa AWUS036NEH,  Panda PAU06


- If you do pen or security testing: (monitor mode)

Note: ALL adapters in the main list work well with Kali linux and Aircrack-ng

5 GHZ: Alfa AWUS036ACHM (very long range), Alfa AWUS036ACM, Panda PAU09 

2.4 GHz only: Alfa AWUS036NHA, Alfa AWUS036NEH


- If you are looking for a portable adapter to take on the road (managed (client) mode)

5 GHZ: Linksys AE6000, Netgear A6210 

2.4 GHz only: Panda PAU03, EDUP EP-8551

```
-----

Commentary: An internet search for "best adapter for Kali Linux" will yield a lot of results. Almost every result will list some adapters that are likely to result in frustration. Do the authors of these sites not test the adapters that they are recommending? I see numerous recommendations for adapters based on Realtek chipsets. The ALFA AWUS1900, based on the rtl8814au chipset, is often recommended but I can tell you from first hand experience with maintaining a [driver for the rtl8814au](https://github.com/morrownr/8814au) that the driver and support from Realtek is simply bad. Really bad. There is no other way to put it. The same thing applies to adapters based on the rtl8811au chipset. Realtek does not support in-kernel drivers for their modern USB WiFi chipsets, which is unfortunate because the development model of Linux makes out-of-kernel drivers problematic in many ways. Then there is the issue of broken or missing features. There many good USB WiFi adapters that use Linux in-kernel drivers that are Linux Wireless Standards compliant so my recommendation is to avoid adapters based on chipsets from Realtek. 

The Best USB WiFi Adapter List for Kali Linux is right here.

-----
