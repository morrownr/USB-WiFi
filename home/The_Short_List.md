2022-10-10

The Short List - Superstar USB WiFi Adapters for Linux

"I plugged it in and it just works™" 

Note: I have noticed that armbian.com has a link to this page. This is not a good entry point to this site
as it does not give a full list of adapters with in-kernel drivers nor does it provide links to adapters.
The best link into this site is to the Main Menu:

https://github.com/morrownr/USB-WiFi

-----

```
Adapter                      Chipset / Class  / Bands       USB  WPA3  Range      State (single state is preferred)
```
-----

```
ALFA AWUS036ACM [1] [2]      mt7612u / AC1200 / 2.4, 5      USB3  Yes  Long       Single

TEROW ROW02CD [1] [2]        mt7612u / AC1200 / 2.4, 5      USB3  Yes  Long       Single
```

-----

```
ALFA AWUS036ACHM [1] [2] [3] mt7610u / AC600  / 2.4, 5      USB2  Yes  Very Long  Single

ANDDEAR MT761003             mt7610u / AC600  / 2.4, 5      USB2  Yes  Medium     Single

Linksys AE6000 [1]           mt7610u / AC580  / 2.4, 5      USB2  Yes  Medium     Single
```

-----

```
Panda PAU09                  rt5572  / N600   / 2.4, 5      USB2  Yes  Long       Single

WTXUP RT3572                 rt3572  / N600   / 2.4, 5      USB2  Yes  Long       Single

CHANEVE RT3572               rt3572  / N600   / 2.4, 5      USB2  Yes  Medium     Single
```
-----

```
CanaKit BC19675              rt5370  / N150   / 2.4         USB2  Yes  Short      Single

Panda PAU03 [1] (nano)       rt5370  / N150   / 2.4         USB2  Yes  Short      Single

EDUP EP-MS8551 [1] [4]       mt7601u / N150   / 2.4         USB2  Yes  Very Long  Single

Zibo-6467115 [1] [4] (nano)  mt7601u / N150   / 2.4         USB2  Yes  Short      Single

ALFA AWUS036NHA              ar9271  / N150   / 2.4         USB2  Yes  Long       Single

WiFi Nation WN-H3            ar9271  / N150   / 2.4         USB2  Yes  Long       Single

Panda PAU08 [1]              rt3070  / N150   / 2.4         USB2  Yes  Very Long  Single
```

-----

```
[1] I have first hand experience with this adapter.
[2] Excellent for 5 GHz AP mode (works well with a Raspberry Pi 4B)
[3] Outstanding for 2.4 GHz AP mode
[4] Use only for client (managed) mode. No AP mode. Limited monitor mode.

Criteria to make The Short List: 

1. Uses an In-kernel driver (adapter is plug and play).
2. Has either a documented track record or my own testing experience.
3. Is available to purchase as a new product.

USB WiFi adapters come in various shapes, sizes and speeds. Their capabilities
can vary greatly. The adapter that you pick needs to be chosen based on its
ability to do the job that you need it to do.
```

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
