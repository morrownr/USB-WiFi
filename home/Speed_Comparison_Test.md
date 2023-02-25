## USB WiFi Adapter Speed Comparison Test

Note: This is a test using a capability that all of the tested adapters have.
All adapters were tested from the same location connected to the same AP.

Test setup:

```
WiFi 5
AC
5 GHz
Channel 116 DFS - clear air (no other APs on the channel)
80 MHz channel width
WiFi Router: ZyXEL NBG6817 (Wave 2) (running OpenWRT 22.03, iperf3 -s)
WPA3
Distance: about 7 meters (20 ft)
Obstacles: 2 walls
Client: Desktop i7 running kernel 6.1 (Xubuntu 22.10, iperf3 -c 192.168.1.1)
```

The adapters and results are listed in order with fastest first.

-----

```
WiFi Adapter: Comfast CF-951AX
Capability: Wifi 6e - AXE3000
Chipet: mt7921au
ID 0e8d:7961 MediaTek Inc. Wireless_Device
Note: Do not take the inclusion of this specific adapter in this test as a
recommendation. There are better adapters with this chipset. The mt7921au
chipset and the mt7921u driver are proving to be fast and stable.
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.185 port 52582 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  72.8 MBytes   611 Mbits/sec    0   1.89 MBytes
[  5]   1.00-2.00   sec  75.0 MBytes   629 Mbits/sec    0   1.89 MBytes
[  5]   2.00-3.00   sec  75.0 MBytes   629 Mbits/sec    0   1.89 MBytes
[  5]   3.00-4.00   sec  73.8 MBytes   619 Mbits/sec    0   1.89 MBytes
[  5]   4.00-5.00   sec  77.5 MBytes   650 Mbits/sec    0   1.89 MBytes
[  5]   5.00-6.00   sec  73.8 MBytes   619 Mbits/sec    0   1.89 MBytes
[  5]   6.00-7.00   sec  75.0 MBytes   629 Mbits/sec    0   1.89 MBytes
[  5]   7.00-8.00   sec  75.0 MBytes   629 Mbits/sec    0   1.89 MBytes
[  5]   8.00-9.00   sec  75.0 MBytes   629 Mbits/sec    0   1.89 MBytes
[  5]   9.00-10.00  sec  75.0 MBytes   629 Mbits/sec    0   1.89 MBytes

[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   748 MBytes   627 Mbits/sec    0             sender
[  5]   0.00-10.01  sec   746 MBytes   625 Mbits/sec                  receiver
```

-----

```
WiFi Adapter: Comfast CF-958AC
Capability: Wifi 5 - AC1900
Chipet: rtl8814au
ID 0bda:8813 Realtek Semiconductor Corp. RTL8814AU 802.11a/b/g/n/ac Wireless Adapter
Note: The driver for this adapter is old and is missing features. You do not
want this adapter or any adapter with this chipset.
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.124 port 59926 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  55.3 MBytes   464 Mbits/sec    0   1.16 MBytes
[  5]   1.00-2.00   sec  71.2 MBytes   598 Mbits/sec    0   1.81 MBytes
[  5]   2.00-3.00   sec  77.5 MBytes   650 Mbits/sec    0   1.81 MBytes
[  5]   3.00-4.00   sec  77.5 MBytes   650 Mbits/sec    0   1.81 MBytes
[  5]   4.00-5.00   sec  77.5 MBytes   650 Mbits/sec    0   1.81 MBytes
[  5]   5.00-6.00   sec  76.2 MBytes   640 Mbits/sec    0   1.81 MBytes
[  5]   6.00-7.00   sec  77.5 MBytes   650 Mbits/sec    0   1.81 MBytes
[  5]   7.00-8.00   sec  78.8 MBytes   661 Mbits/sec    0   1.81 MBytes
[  5]   8.00-9.00   sec  77.5 MBytes   650 Mbits/sec    0   1.81 MBytes
[  5]   9.00-10.00  sec  77.5 MBytes   650 Mbits/sec    0   1.81 MBytes

[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   747 MBytes   626 Mbits/sec    0             sender
[  5]   0.00-10.01  sec   745 MBytes   624 Mbits/sec                  receiver
```

-----

```
WiFi Adapter: Alfa AWUS036AXER
Capability: Wifi 6 - AX1800
Chipet: rtl8832bu
ID 0bda:b832 Realtek Semiconductor Corp. 802.11ax WLAN Adapter
Note: This is a multi-state adapter. You do not want this adapter.
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.165 port 44936 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  64.6 MBytes   541 Mbits/sec    0   1.87 MBytes
[  5]   1.00-2.00   sec  68.8 MBytes   577 Mbits/sec    0   1.87 MBytes
[  5]   2.00-3.00   sec  70.0 MBytes   587 Mbits/sec    0   1.87 MBytes
[  5]   3.00-4.00   sec  70.0 MBytes   587 Mbits/sec    0   1.87 MBytes
[  5]   4.00-5.00   sec  68.8 MBytes   577 Mbits/sec    0   1.87 MBytes
[  5]   5.00-6.00   sec  68.8 MBytes   577 Mbits/sec    0   1.87 MBytes
[  5]   6.00-7.00   sec  70.0 MBytes   587 Mbits/sec    0   1.87 MBytes
[  5]   7.00-8.00   sec  68.8 MBytes   577 Mbits/sec    0   1.87 MBytes
[  5]   8.00-9.00   sec  70.0 MBytes   587 Mbits/sec    0   1.87 MBytes
[  5]   9.00-10.00  sec  68.8 MBytes   577 Mbits/sec    0   1.87 MBytes
- - - - - - - - - - - - - - - - - - - - - - - - -
[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   688 MBytes   577 Mbits/sec    0             sender
[  5]   0.00-10.01  sec   687 MBytes   576 Mbits/sec                  receiver
```

-----

```
WiFi Adapter: Cudy WU1400
Capability: Wifi 5 - AC1300
Chipet: rtl8812bu
ID 0bda:b812 Realtek Semiconductor Corp. RTL88x2bu
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.109 port 43290 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  65.2 MBytes   547 Mbits/sec    0   1.73 MBytes
[  5]   1.00-2.00   sec  66.2 MBytes   556 Mbits/sec    0   1.82 MBytes
[  5]   2.00-3.00   sec  66.2 MBytes   556 Mbits/sec    0   1.82 MBytes
[  5]   3.00-4.00   sec  66.2 MBytes   556 Mbits/sec    0   1.82 MBytes
[  5]   4.00-5.00   sec  66.2 MBytes   556 Mbits/sec    0   1.82 MBytes
[  5]   5.00-6.00   sec  66.2 MBytes   556 Mbits/sec    0   1.82 MBytes
[  5]   6.00-7.00   sec  67.5 MBytes   566 Mbits/sec    0   1.82 MBytes
[  5]   7.00-8.00   sec  66.2 MBytes   556 Mbits/sec    0   1.82 MBytes
[  5]   8.00-9.00   sec  66.2 MBytes   556 Mbits/sec    0   1.82 MBytes
[  5]   9.00-10.00  sec  66.2 MBytes   556 Mbits/sec    0   1.82 MBytes

[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   663 MBytes   556 Mbits/sec    0             sender
[  5]   0.00-10.01  sec   661 MBytes   554 Mbits/sec                  receiver
```

-----

```
WiFi Adapter: ALFA AWUS036ACH
Capability: Wifi 5 - AC1200
Chipet: rtl8812au
ID 0bda:8812 Realtek Semiconductor Corp. RTL8812AU 802.11a/b/g/n/ac 2T2R DB WLAN Adapter
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.188 port 38814 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  59.8 MBytes   502 Mbits/sec    0   1.66 MBytes
[  5]   1.00-2.00   sec  58.8 MBytes   493 Mbits/sec    0   1.76 MBytes
[  5]   2.00-3.00   sec  60.0 MBytes   503 Mbits/sec    0   1.87 MBytes
[  5]   3.00-4.00   sec  57.5 MBytes   482 Mbits/sec    0   1.87 MBytes
[  5]   4.00-5.00   sec  57.5 MBytes   482 Mbits/sec    0   1.87 MBytes
[  5]   5.00-6.00   sec  57.5 MBytes   482 Mbits/sec    0   1.87 MBytes
[  5]   6.00-7.00   sec  56.2 MBytes   472 Mbits/sec    0   1.87 MBytes
[  5]   7.00-8.00   sec  57.5 MBytes   482 Mbits/sec    0   1.87 MBytes
[  5]   8.00-9.00   sec  56.2 MBytes   472 Mbits/sec    0   1.87 MBytes
[  5]   9.00-10.00  sec  58.8 MBytes   493 Mbits/sec    0   1.87 MBytes

[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   580 MBytes   486 Mbits/sec    0             sender
[  5]   0.00-10.01  sec   577 MBytes   484 Mbits/sec                  receiver
```

-----

```
WiFi Adapter: ALFA AWUS036ACM
Capability: Wifi 5 - AC1200
Chipet: mt7612u
ID 0e8d:7612 MediaTek Inc. MT7612U 802.11a/b/g/n/ac Wireless Adapter
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.228 port 58404 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  49.4 MBytes   414 Mbits/sec    0    757 KBytes
[  5]   1.00-2.00   sec  46.2 MBytes   388 Mbits/sec    2    568 KBytes
[  5]   2.00-3.00   sec  47.5 MBytes   398 Mbits/sec    0    646 KBytes
[  5]   3.00-4.00   sec  47.5 MBytes   398 Mbits/sec    0    700 KBytes
[  5]   4.00-5.00   sec  46.2 MBytes   388 Mbits/sec    0    735 KBytes
[  5]   5.00-6.00   sec  46.2 MBytes   388 Mbits/sec    0    769 KBytes
[  5]   6.00-7.00   sec  46.2 MBytes   388 Mbits/sec    2    585 KBytes
[  5]   7.00-8.00   sec  46.2 MBytes   388 Mbits/sec    0    619 KBytes
[  5]   8.00-9.00   sec  46.2 MBytes   388 Mbits/sec    0    639 KBytes
[  5]   9.00-10.00  sec  46.2 MBytes   388 Mbits/sec    0    650 KBytes

[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   468 MBytes   393 Mbits/sec    4             sender
[  5]   0.00-10.01  sec   466 MBytes   390 Mbits/sec                  receiver
```

-----

```
WiFi Adapter: EDUP EP-AC1635
Capability: Wifi 5 - AC600
Chipet: rtl8811cu
ID 0bda:c811 Realtek Semiconductor Corp. 802.11ac NIC
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.103 port 56144 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  32.7 MBytes   274 Mbits/sec    0    870 KBytes
[  5]   1.00-2.00   sec  32.5 MBytes   273 Mbits/sec    0   1.06 MBytes
[  5]   2.00-3.00   sec  32.5 MBytes   273 Mbits/sec    0   1.18 MBytes
[  5]   3.00-4.00   sec  32.5 MBytes   273 Mbits/sec    0   1.26 MBytes
[  5]   4.00-5.00   sec  33.8 MBytes   283 Mbits/sec    0   1.33 MBytes
[  5]   5.00-6.00   sec  32.5 MBytes   273 Mbits/sec    0   1.33 MBytes
[  5]   6.00-7.00   sec  32.5 MBytes   273 Mbits/sec    0   1.33 MBytes
[  5]   7.00-8.00   sec  32.5 MBytes   273 Mbits/sec    0   1.33 MBytes
[  5]   8.00-9.00   sec  32.5 MBytes   273 Mbits/sec    0   1.33 MBytes
[  5]   9.00-10.00  sec  31.2 MBytes   262 Mbits/sec    0   1.40 MBytes

[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   325 MBytes   273 Mbits/sec    0             sender
[  5]   0.00-10.01  sec   323 MBytes   271 Mbits/sec                  receiver
```

-----

```
WiFi Adapter: ALFA AWUS036ACS
Capability: Wifi 5 - AC600
Chipet: rtl8811au
ID 0bda:0811 Realtek Semiconductor Corp. Realtek 8812AU/8821AU 802.11ac
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.172 port 58436 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  32.3 MBytes   271 Mbits/sec    0    686 KBytes
[  5]   1.00-2.00   sec  30.0 MBytes   252 Mbits/sec    0    894 KBytes
[  5]   2.00-3.00   sec  30.0 MBytes   252 Mbits/sec    0    940 KBytes
[  5]   3.00-4.00   sec  30.0 MBytes   252 Mbits/sec    0    940 KBytes
[  5]   4.00-5.00   sec  30.0 MBytes   252 Mbits/sec    0    940 KBytes
[  5]   5.00-6.00   sec  30.0 MBytes   252 Mbits/sec    0    940 KBytes
[  5]   6.00-7.00   sec  30.0 MBytes   252 Mbits/sec    0    940 KBytes
[  5]   7.00-8.00   sec  30.0 MBytes   252 Mbits/sec    0    940 KBytes
[  5]   8.00-9.00   sec  30.0 MBytes   252 Mbits/sec    0   1.03 MBytes
[  5]   9.00-10.00  sec  30.0 MBytes   252 Mbits/sec    0   1.03 MBytes

[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   302 MBytes   254 Mbits/sec    0             sender
[  5]   0.00-10.01  sec   299 MBytes   251 Mbits/sec                  receiver
```

-----

```
WiFi Adapter: ALFA AWUS036ACHM
Capability: Wifi 5 - AC600
Chipet: mt7610u
ID 0e8d:7610 MediaTek Inc. WiFi
```

```
$ iperf3 -c 192.168.1.1
Connecting to host 192.168.1.1, port 5201
[  5] local 192.168.1.176 port 36664 connected to 192.168.1.1 port 5201
[ ID] Interval           Transfer     Bitrate         Retr  Cwnd
[  5]   0.00-1.00   sec  26.8 MBytes   225 Mbits/sec    0    732 KBytes
[  5]   1.00-2.00   sec  25.0 MBytes   210 Mbits/sec    0    775 KBytes
[  5]   2.00-3.00   sec  26.2 MBytes   220 Mbits/sec    0    812 KBytes
[  5]   3.00-4.00   sec  23.8 MBytes   199 Mbits/sec    0    854 KBytes
[  5]   4.00-5.00   sec  26.2 MBytes   220 Mbits/sec    0    854 KBytes
[  5]   5.00-6.00   sec  23.8 MBytes   199 Mbits/sec    0    854 KBytes
[  5]   6.00-7.00   sec  26.2 MBytes   220 Mbits/sec    0    894 KBytes
[  5]   7.00-8.00   sec  25.0 MBytes   210 Mbits/sec    0    898 KBytes
[  5]   8.00-9.00   sec  25.0 MBytes   210 Mbits/sec    0    898 KBytes
[  5]   9.00-10.00  sec  25.0 MBytes   210 Mbits/sec    0    947 KBytes

[ ID] Interval           Transfer     Bitrate         Retr
[  5]   0.00-10.00  sec   253 MBytes   212 Mbits/sec    0             sender
[  5]   0.00-10.02  sec   250 MBytes   209 Mbits/sec                  receiver
```

-----

Comments: I used adapters with many modern chipsets so as to show the relative
performance you can expect. Keep in mind that this is a speed test at short to
medium range, not a range test. The Alfa ACHM and ACH would run away from the
pack in a range test.

@morrownr
