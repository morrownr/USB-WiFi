2021-08-02

The Short List - Superstar USB WiFi Adapters for Linux

Note: This list is subject to change as new information becomes available.  If you
have an adapter that you think should be on this list but is not or you see an adapter
that you think should not be on the list but is, please use Issues to let me know. 

-----

```
Adapter                      Chipset / Class  / Bands       USB  WPA3  Range    State
```

-----

```
Alfa AWUS036ACM [1] [3]      mt7612u / AC1200 / 2.4, 5      USB3  Yes  Long     Single

TEROW ROW02FD [1] [3]        mt7612u / AC1200 / 2.4, 5      USB3  Yes  Long     Multi

COMFAST CF-WU782AC [3]       mt7612u / AC1300 / 2.4, 5      USB3  Yes  Long     Multi

Netgear A6210 [1]            mt7612u / AC1200 / 2.4, 5      USB3  Yes  Medium   Single

Linksys AE6000 [1]           mt7610u / AC580  / 2.4, 5      USB2  Yes  Medium   Single

Panda PAU09                  rt5572  / N600   / 2.4, 5      USB2  Yes  Long     Single

Panda PAU06                  rt5372  / N300   / 2.4         USB2  Yes  Medium   Single

Panda PAU03 (nano) [1]       rt5370  / N150   / 2.4         USB2  Yes  Short    Single        

Alfa AWUS036NHA              ar9271  / N150   / 2.4         USB2  Yes  Long     Single

Alfa AWUS036NEH              rt3070  / N150   / 2.4         USB2  Yes  Long     Single

DM-Digital [1] [2]           mt7601u / N150   / 2.4         USB2  Yes  Medium   Single

EDUP EP-8551 [1] [2]         mt7601u / N150   / 2.4         USB2  Yes  Long     Single
```

-----

```
[1] I have first hand experience with this adapter.
[2] Only supports managed and monitor modes. Low cost.
[3] Excellent for 5 GHz AP mode (works well with a Raspberry Pi 4B)

Criteria to make The Short List: 

1. Uses an In-kernel driver (adapter is plug and play).
2. Has either a well documented track record or my own testing experience.
3. Is available to purchase as a new product.

USB WiFi adapters come in various shapes, sizes and speeds. Their capabilities
can vary greatly. The adapter that you pick needs to be chosen based on its
ability to do the job that you need it to do. Below are some recommendations
based on specific use cases:

- If you want to build your own WiFi Router/Access Point/Hotspot: (master (AP) mode)

5 GHZ: Alfa AWUS036ACM, TEROW ROW02FD, COMFAST CF-WU782AC

2.4 GHz only: Alfa AWUS036NHA, Panda PAU06, Alfa AWUS036NEH


- If you do pen testing: (monitor mode)

Note: ALL listed adapters work well with Kali linux and Aircrack-ng

5 GHZ: Alfa AWUS036ACM, Panda PAU09 

2.4 GHz only: Alfa AWUS036NHA, Alfa AWUS036NEH, EDUP EP-8551


- If you are looking for a portable adapter to take on the road (managed (client) mode)

5 GHZ: Netgear A6210, Linksys AE6000

2.4 GHz only: Panda PAU03, EDUP EP-8551

```
-----

Links to the above adapters can be found [here](https://github.com/morrownr/USB-WiFi).

-----
