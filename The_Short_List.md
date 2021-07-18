2021-07-13

The Short List - Superstar USB WiFi Adapters for Linux

-----

```
    Adapter                      Chipset / Class  / Bands       USB  WPA3  Range
```

-----

```
1.  Alfa AWUS036ACM [1] [3]      mt7612u / AC1200 / 2.4, 5      USB3  Yes  L

2.  TEROW ROW02FD [1] [3]        mt7612u / AC1200 / 2.4, 5      USB3  Yes  L

3.  COMFAST CF-WU782AC [3]       mt7612u / AC1200 / 2.4, 5      USB3  Yes  L

4.  Netgear A6210 [1]            mt7612u / AC1200 / 2.4, 5      USB3  Yes  M

5.  Alfa AWUS036ACHM [1] [2]     mt7610u / AC600  / 2.4, 5      USB2  Yes  VL

6.  Cable Matters 202043 [1]     mt7610u / AC600  / 2.4, 5      USB3  Yes  S

7.  Linksys AE6000 [1]           mt7610u / AC580  / 2.4, 5      USB2  Yes  M

8.  Panda PAU09                  rt5572  / N600   / 2.4, 5      USB2  Yes  L

9.  Panda PAU06                  rt5372  / N300   / 2.4         USB2  Yes  M

10. Panda PAU03 (nano) [1]       rt5370  / N150   / 2.4         USB2  Yes  S

11. Alfa AWUS036NHA              ar9271  / N150   / 2.4         USB2  Yes  L

12. K2-544DW [1]                 ar9271  / N150   / 2.4         USB2  Yes  M 

13. Alfa AWUS036NEH              rt3070  / N150   / 2.4         USB2  Yes  L

14. DM-Digital [1] [4]           mt7601u / N150   / 2.4         USB2  Yes  M

15. EDUP EP-8551 [1] [4]         mt7601u / N150   / 2.4         USB2  Yes  L

Range: VL = Very Long, L = Long, M = Medium, S = Short
```

-----

```
[1] I have first hand experience with this adapter.
[2] Longest range of any adapter that I have ever tested.
[3] Excellent for 5 GHz AP mode (works well with a Raspberry Pi 4B)
[4] Only supports managed and monitor modes. Low cost.

Criteria to make The Short List: 

1. Uses an In-kernel driver (adapter is plug and play).
2. Has either a well documented track record or my own testing experience.
3. Is available to purchase as a new product.

USB WiFi adapters come in various shapes, sizes and speeds. Their capabilities
can vary greatly. The adapter that you pick needs to be chosen based on its
ability to do the job that you need it to do. Below are some recommendations
based on specific use cases:

- If you want to build your own WiFi Router/Access Point/Hotspot: (AP mode)

5 GHZ: Alfa AWUS036ACM, TEROW ROW02FD, COMFAST CF-WU782AC

2.4 GHz only: Alfa AWUS036NHA, K2-544DW, Panda PAU06, Alfa AWUS036NEH

- If you do pen testing: (monitor mode)

Note: ALL listed adapters work well with Kali linux and Aircrack-ng

5 GHZ: Alfa AWUS036ACHM, Alfa AWUS036ACM, Panda PAU09 

2.4 GHz only: Alfa AWUS036NHA, Alfa AWUS036NEH, EDUP EP-8551

- If you are looking for a portable adapter to take on the road (managed (client))

5 GHZ: Netgear A6210, Linksys AE6000

2.4 GHz only: Panda PAU03, EDUP EP-8551

```
-----

Links to the above adapters can be found [here](https://github.com/morrownr/USB-WiFi).

-----
