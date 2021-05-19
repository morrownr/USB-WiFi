2021-05-17 (New Tests in Progress)

USB WiFi Adapter Performance Comparison (listed in order by link quality)

```
Adapter                       Chipset/Class               USB Capability
Heavy Load Power Usage        Device ID                   Visible Antennas
iperf3 Test                   Link Quality                Signal Level
```
-----
```
Alfa AWUS036ACHM              mt7610u / AC600             USB2
380 mA                        ID 0e8d:7610                1
137 Mb/s - Retr 0             96/100                      -43 dBm

Alfa AWUS036ACH               rtl8812au / AC1200          USB3
800 mA                        ID 0bda:8812                2
281 Mb/s - Retr 184           91/100                      -46 dBm

Generic (brown box)           rtl8814au / AC1900          USB3
830 mA                        ID 0bda:8813                2
204 Mb/s                      86/100                      -50 dBm

Alfa AWUS036ACM         	mt7612u / AC1200	USB3
380 mA                   	ID 0e8d:7612            2
237 Mb/s                	Link Quality=79/100     Signal level=-55 dBm

*Alfa AWUS036ACS         	rtl8811au / AC600	USB2
270 mA         	          	ID 0bda:0811            1
157 Mb/s                	Link Quality=77/100     Signal level=-56 dBm

Netgear A6210             mt7612u / AC1200        USB3
420 mA                    ID: 0846:9053           1
148 Mb/s - Retr 7         Link Quality=63/100     Signal level=-66 dBm

Generic (brown box)       rtl8812bu / AC1200      USB3
520 mA                    ID 0bda:b812            2
144 Mb/s - Retr 0         Link Quality=60/100     Signal level=-68 dBm
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

In progress...

Categories:

In progress...

-----

Price:
```

```
-----

Quality construction:
```

```
-----

Signal strength:
```

```
-----

Driver quality:
```

```
-----

Master (AP) mode quality:
```

```
-----

Monitor mode quality:
```

```
-----

Low power usage:
(important for use with a Raspberry Pi)
```

```
-----

Driver is in-kernel:
```

```
-----

Driver is Linux Wireless standards compliant:
```

```
-----

Clear path to report driver problems:
```

```
-----
