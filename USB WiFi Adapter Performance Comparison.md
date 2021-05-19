2021-05-19 (New Tests in Progress)

USB WiFi Adapter Performance Comparison (listed in order by link quality)

-----
```
Adapter                       Chipset/Class               USB Capability
Heavy Load Power Usage        Device ID                   Visible Antennas
iperf3 Test                   Link Quality                Signal Level
```
-----
```
Alfa AWUS036ACHM              mt7610u / AC600             USB2
380 mA                        ID 0e8d:7610                1
137 Mb/s                      96/100 (A+)                 -43 dBm

Alfa AWUS036ACH               rtl8812au / AC1200          USB3
800 mA                        ID 0bda:8812                2
281 Mb/s                      91/100 (A)                  -46 dBm

Alfa AWUS036ACM               mt7612u / AC1200            USB3
380 mA                        ID 0e8d:7612                2
237 Mb/s                      79/100 (B)                  -55 dBm

Cudy WU1400                   rtl8812bu / AC1200          USB3
520 mA                        ID 0bda:b812                1
215 Mb/s                      79/100 (B)                  -55 dBm

Alfa AWUS036ACS               rtl8811au / AC600           USB2
270 mA                        ID 0bda:0811                1
157 Mb/s                      77/100 (B)                  -56 dBm

Netgear A6210                 mt7612u / AC1200            USB3
420 mA                        ID: 0846:9053               1
148 Mb/s                      63/100 (C)                  -66 dBm
```

Test conditions:

Link Quality and Signal Level tested using 5 Ghz from a distance to AP
of about 45 feet. The signal had to travel through 3 walls. This test was
designed to be a challenge.

AP set on channel 149, channel width 80.

iperf3 runs on a Raspberry Pi 4b connected to the main AP via CAT 6
ethetnet cable.

Adapters were connected to a rear USB port on a Dell Optiplex 9020
with an i7 processor running Linux Mint 20.1.

Utilities used include wavemon, iw and iperf3.

iperf3 test: $ iperf3 -c 192.168.1.41 -t 120

Analysis:

The adapters used in the comparison were selected to provide a variety
of size, cost and capability. The test conditions presented a challenge
but all adapters were able to reliably communicate. The link quality of
the Alfa AWUS036ACHM is impressive.

Categories:

In progress...

-----

Quality of Construction:
```
Alfa AWUS036ACH
Alfa AWUS036ACM
Alfa AWUS036ACHM
```
-----

Link Quality:
```
Alfa AWUS036ACHM
Alfa AWUS036ACH
Alfa AWUS036ACM

```
-----

Driver quality:
```
Alfa AWUS036ACM, Netgear A6210 - mt7612u
Alfa AWUS036ACHM - mt7610u
Alfa AWUS036ACH - rtl8812au
```
-----

Master (AP) mode quality:
```
Alfa AWUS036ACM
Alfa AWUS036ACH
Alfa AWUS036ACHM
```
-----

Monitor mode quality:
```
Alfa AWUS036ACHM
Alfa AWUS036ACM
Alfa AWUS036ACH
```
-----

Low power usage:
(important for use with a Raspberry Pi)
```
Alfa AWUS036ACS (AC600)
Alfa AWUS036ACM (AC1200)
Alfa AWUS036ACHM (AC600)
```
-----

Driver is in-kernel:
```
Alfa AWUS036ACM
Netgear A6210
Alfa AWUS036ACHM
```
-----

Driver is Linux Wireless standards compliant:
```
Alfa AWUS036ACM
Netgear A6210
Alfa AWUS036ACHM
```
-----

Clear path to report driver problems:
```
Alfa AWUS036ACM
Netgear A6210
Alfa AWUS036ACHM
```
-----
