## USB WiFi adapter performance comparison

2021-05-31

The USB WiFi adapters are listed in order by `link quality`.

Note: The adapters selected for testing are considered to be high quality adapters. 

-----
```
Adapter                       Chipset/Class               USB Capability       WPA3 Support
Heavy Load Power Usage        Device ID                   Visible Antennas
iperf3 Test                   Link Quality                Signal Level
```
-----
```
Alfa AWUS036ACHM              mt7610u / AC600             USB2                 Yes
380 mA                        ID 0e8d:7610                1
137 Mb/s                      93/100 (A)                  -45 dBm

Alfa AWUS036ACH               rtl8812au / AC1200          USB3                 Yes, if distro has updated wpa_supplicant
800 mA                        ID 0bda:8812                2                    and Network Manager
281 Mb/s                      91/100 (A)                  -46 dBm

EDUP EP-AC1605GS              rtl8812bu / AC1300          USB3                 Yes, if distro has updated wpa_supplicant
520 mA                        ID 0bda:b812                2                    and Network Manager
305 Mb/s                      84/100 (B)                  -51 dBm

Alfa AWUS036ACM               mt7612u / AC1200            USB3                 Yes
380 mA                        ID 0e8d:7612                2
237 Mb/s                      79/100 (B)                  -55 dBm

Alfa AWUS036ACS               rtl8811au / AC600           USB2                 Yes, if distro has updated wpa_supplicant
270 mA                        ID 0bda:0811                1                    and Network Manager
157 Mb/s                      77/100 (B)                  -56 dBm

Netgear A6210                 mt7612u / AC1200            USB3                 Yes
420 mA                        ID: 0846:9053               1
171 Mb/s                      64/100 (C)                  -65 dBm

```
-----

Note: Additional adapters were tested but were eliminated if their Signal
Level was worse than -65 dBm.

Notes about the Netgear A6210 adapter: It likely appears at the end of
the list because of its design. It is designed for portability, not long
range. Build quality seems to be very good and it can push iperf3 to
show rates of 300-400 Mb/s at close to medium range. It was able to 
maintain a good link with a reasonable speed even given the difficult
conditions of this test. All adapters that I documented in this test are
adapters that I consider well above average adapters.

Notes about excluded adapters: I excluded adapters based on the rtl8814au
chipset based on the very poor quality of the driver provided by Realtek.
I also excluded multi-state adapters.

-----

Test conditions:

Link Quality and Signal Level tested using 5 Ghz from a distance to AP
of about 45 feet. The signal had to travel through 3 walls. This test was
designed to be a challenge.

AP set on channel 149, channel width 80.

iperf3 runs on a Raspberry Pi 4b connected to the main AP via CAT 6
ethernet cable.

Adapters were connected to a rear USB port on a Dell Optiplex 9020
with an i7 processor running Linux Mint 20.1.

Utilities used: lsusb, wavemon and iperf3.

iperf3 test: $ iperf3 -c 192.168.1.4 -t 120

Link quality grading scale: A (outstanding) = 100-90, B (excellent) = 89-75, C (good)= 74-60

Analysis:

The adapters used in this comparison were selected to provide a cross section
of high quality adapters that would satisfy various use cases for Linux users.
The test conditions presented a challenge but all adapters were able to reliably
communicate for sustained periods without dropping offline.

```The link quality (and range) of the Alfa AWUS036ACHM and Alfa AWUS036ACH is impressive.```

Alfa  advertises both as MAX RANGE products and the data shows that to be the case
as they have smoked everything that I have compared them to. The ACHM sells for
around $40 USD while the ACH sells for $60 - $70 USD depending on whether you are
looking at the model with USB-C or Micro USB3 ports. They are premium quality
adapters and their price reflects as much. Both are a pleasure to use.

Note: There are additional factors beyond link quality that need to be taken into
account before making a purchase decision.

- The drivers for the mt761xu based adapters are located in and maintained in the
Linux kernel which means using the adapter is plug and play. The drivers are Linux
Wireless standards compliant. Their support for AP and Monitor modes is outstanding.

- The drivers for the rtl88xx based dual band adapters are not in the Linux kernel so
users will first have to locate a version of the driver that will work with the Linux
kernel they are using. This is NOT an easy task and often leads to frustration. If you are
able to find and install a driver for Realtek based adapters, as your Linux distro is
upgraded, the driver may stop working because the driver is not being upgraded with
changes made in new kernels. Lastly, the Realtek drivers are not Linux Wireless standards
compliant. Do not disregard or underestimate the aggravation that Realtek based adapters
can cause. You have been warned.

Paying for a good quality USB WiFi adapter that is supported by in-kernel drivers can make
a lot of difference in your experience. Cheap, poor quality adapters or adapters that use
out-of-kernel drivers can lead to a bad experience.

My opinion, based on experience using the tested adapters, is shown in the following
categories: (the Top 3 are listed in order)

-----

Build Quality:
```
1. Alfa AWUS036ACH
2. Alfa AWUS036ACM
3. Alfa AWUS036ACHM
```
Note: There is very little difference in quality from 1 to 3. All 3 are excellent quality adapters.

-----

Link Quality:
```
1. Alfa AWUS036ACHM
2. Alfa AWUS036ACH
3. EDUP EP-AC1605GS

```
Note: The link quality and range of adapters 1 and 2 is very impressive.

-----

Driver Quality:
```
1. Alfa AWUS036ACM, Netgear A6210 - mt7612u
2. Alfa AWUS036ACHM - mt7610u
3. Alfa AWUS036ACH - rtl8812au
Honorable mention: Alfa AWUS036ACS
```

Note: The drivers for the
[rtl8812au](https://github.com/morrownr/8812au-20210629)
and
[rtl8821au](https://github.com/morrownr/8821au-20210708)
are the only Realtek dual mode drivers that I consider to
be reasonable quality for use in monitor mode and AP mode.

-----

Managed mode Operation:
```
1. EDUP EP-AC1605GS
2. Alfa AWUS036ACH
3. Alfa AWUS036ACM
```
-----

Master (AP) mode Operation:
```
1. Alfa AWUS036ACM
2. Alfa AWUS036ACHM
3. Alfa AWUS036ACH
Honorable mention: Alfa AWUS036ACS (short range)
```

Note: AP mode requires a high degree of stability which depends on very good quality drivers as well as good quality hardware. All 3 adapters do a good job with AP mode. Adapters 2 and 3 provide long range if that is important for your use case. Adapter 3 supports DFS channels in AP mode whereas adapters 1 and 2 currently do not. Here are the drivers for the [AWUS036ACH](https://github.com/morrownr/8812au-20210629) and the [AWUS036ACS](https://github.com/morrownr/8821au-20210708). Adapters 1 and 2 use in-kernel drivers which enhances their trouble free operation. 

-----

Monitor mode Operation:
```
1. Alfa AWUS036ACHM
2. Alfa AWUS036ACM
3. Alfa AWUS036ACH
Honorable mention: Alfa AWUS036ACS
```
Note: Penetration testers should take a look at adapters 1 and 2. Adapter 1 has exceptional range. Here are the drivers for the [AWUS036ACH](https://github.com/morrownr/8812au-20210629) and the [AWUS036ACS](https://github.com/morrownr/8821au-20210708).

-----

Low power usage:
(important for use with a Raspberry Pi or other use cases that require low power adapters)
```
1. Alfa AWUS036ACS (AC600)
2. Alfa AWUS036ACM (AC1200)
3. Alfa AWUS036ACHM (AC600)
```
Note: I use adapter 2 with a RasPi4b as an access point. The low power requirement makes it a very good match for Raspberry Pi hardware.

-----

Portability:
```
1. Netgear A6210
2. Alfa AWUS036ACS
3. Alfa AWUS036ACHM
```
-----

Driver is in-kernel:
```
1. Alfa AWUS036ACM, Netgear A6210, Alfa AWUS036ACHM
```
-----

Driver is Linux Wireless standards compliant:
```
1. Alfa AWUS036ACM, Netgear A6210, Alfa AWUS036ACHM
```
-----

Clear path to report driver problems:
```
1. Alfa AWUS036ACM, Netgear A6210, Alfa AWUS036ACHM
```
-----

WPA3 support:
```
1. Alfa AWUS036ACM, Netgear A6210, Alfa AWUS036ACHM
```
-----

Point system for above categories to help forecast the likelyhood
of Linux users being happy with their purchase over the long term:
```
First place = 3 points
Second place = 2 points
Third place = 1 point

Results:

1. Alfa AWUS036ACM  - 25
2. Alfa AWUS036ACHM - 24
3. Netgear A6210    - 15
4. Alfa AWUS036ACH  - 10
5. Alfa AWUS036ACS  -  5
6. EDUP EP-AC1605GS -  4
```

Final note: This is a limited test of a few selected adapters out of
many adapters that are available so please take this document
as general guidance that may prove to be useful.
