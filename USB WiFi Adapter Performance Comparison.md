2021-05-19 (Testing is in progress. The below information is subject to change until this round of testing is complete.)

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
137 Mb/s                      93/100 (A)                  -45 dBm

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
-----

Notes about the Cudy WU1400: I am debating removing this adapter as
testing is causing me to question whether this adapter is of above
average quality.

Notes about the Netgear A6210 adapter: It likely appears at the end of
the list because of its design. It is designed for portability, not long
range. Build quality seems to be above average and it can push iperf3 to
show rates of 300-400 Mb/s at close to medium range.

Notes about excluded adapters: I exclused adapters based on the rtl8814au
chipset based on the very poor quality of the driver provided by Realtek.

-----

Test conditions:

Link Quality and Signal Level tested using 5 Ghz from a distance to AP
of about 45 feet. The signal had to travel through 3 walls. This test was
designed to be a challenge.

AP set on channel 149, channel width 80.

iperf3 runs on a Raspberry Pi 4b connected to the main AP via CAT 6
ethetnet cable.

Adapters were connected to a rear USB port on a Dell Optiplex 9020
with an i7 processor running Linux Mint 20.1.

Utilities used include wavemon, lsusb and iperf3.

iperf3 test: $ iperf3 -c 192.168.1.4 -t 120

Link quality grading scale: A = 100-90, B = 89-75, C = 74-60

Analysis:

The adapters used in the comparison were selected to provide a cross section
of above average quality adapters that would satisfy various use cases for
Linux users. The test conditions presented a challenge but all adapters were
able to reliably communicate for sustained periods without dropping offline.

The link quality of the Alfa AWUS036ACHM and Alfa AWUS036ACH is impressive. They
are premium quality adapters and their price reflects that.

Note: There are additional factors beyond link quality that need to be taken into
account before making a purchase decision. The drivers for the mt761xu based adapters
are located and maintained in the Linux kernel. They are Linux Wireless standards
compliant and support WPA3. The drivers for the rtl88xx based adapters are not in the
Linux kernel so users will first have to locate a version of the driver that will work
with the Linux kernel they are using. As your Linux distro is upgraded, the driver
may stop working because it is not being upgraded with new kernels. Lastly, the
Realtek drivers are not Linux Wireless standards compliant nor do they support WPA3.

Paying for a good quality USB WiFi adapter can make a lot of difference in your 
experience. Cheap, poor quality adapters can lead to a bad experience.

My opinion, based on experience using the tested adapters, is shown in following
categories:

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

Master (AP) mode opertion:
```
Alfa AWUS036ACM
Alfa AWUS036ACH
Alfa AWUS036ACHM
```
Note: AP mode requires a high degree of stability which depends on very good quality drivers as well as good quality hardware. 

-----

Monitor mode operation:
```
Alfa AWUS036ACHM
Alfa AWUS036ACM
Alfa AWUS036ACH
```
-----

Low power usage:
(important for use with a Raspberry Pi or other use cases that require low power required adapters)
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
