ALFA_AWUS036ACHM

A WiFi 5 long range USB 2 adapter

- Chipset: mt7610u
- usb-modeswitch not required. This is a single-state device.
- WPA3-SAE: yes
- Power requirement: Heavy load: ~420 mA

``` console
$ lsusb -vt | grep -E 'mt76|MediaTek'
    |__ Port 2: Dev 5, If 0, Class=Vendor Specific Class, Driver=mt76x0u, 480M
        ID 0e8d:7610 MediaTek Inc.
```

``` console
$ sudo lsusb -v -d 0e8d:7610 | grep -E 'bcdUSB|idVendor|iProduct|MaxPower'
  bcdUSB               2.01
  idVendor           0x0e8d MediaTek Inc.
  iProduct                2 WiFi
    MaxPower              160mA
```

``` console
$ iwconfig |& grep -Eo 'Tx-Power=.*dBm'
Tx-Power=14 dBm
(25.12 mW)
```

``` console
$ uname -a
Linux raspberrypi 5.10.52-v7l+ #1441 SMP Tue Aug 3 18:11:56 BST 2021 armv7l GNU/Linux
```

``` console
$ iw list
Wiphy phy0
	max # scan SSIDs: 4
	max scan IEs length: 2243 bytes
	max # sched scan SSIDs: 0
	max # match sets: 0
	Fragmentation threshold: 2304
	RTS threshold: 2304
	Retry short limit: 7
	Retry long limit: 4
	Coverage class: 0 (up to 0m)
	Device supports RSN-IBSS.
	Device supports AP-side u-APSD.
	Device supports T-DLS.
	Supported Ciphers:
		* WEP40 (00-0f-ac:1)
		* WEP104 (00-0f-ac:5)
		* TKIP (00-0f-ac:2)
		* CCMP-128 (00-0f-ac:4)
		* CCMP-256 (00-0f-ac:10)
		* GCMP-128 (00-0f-ac:8)
		* GCMP-256 (00-0f-ac:9)
		* CMAC (00-0f-ac:6)
		* CMAC-256 (00-0f-ac:13)
		* GMAC-128 (00-0f-ac:11)
		* GMAC-256 (00-0f-ac:12)
	Available Antennas: TX 0x1 RX 0x1
	Configured Antennas: TX 0x1 RX 0x1
	Supported interface modes:
		 * IBSS
		 * managed
		 * AP
		 * AP/VLAN
		 * monitor
		 * mesh point
		 * P2P-client
		 * P2P-GO
	Band 1:
		Capabilities: 0x17e
			HT20/HT40
			SM Power Save disabled
			RX Greenfield
			RX HT20 SGI
			RX HT40 SGI
			RX STBC 1-stream
			Max AMSDU length: 3839 bytes
			No DSSS/CCK HT40
		Maximum RX AMPDU length 65535 bytes (exponent: 0x003)
		Minimum RX AMPDU time spacing: No restriction (0x00)
		HT TX/RX MCS rate indexes supported: 0-7
		Bitrates (non-HT):
			* 1.0 Mbps (short preamble supported)
			* 2.0 Mbps (short preamble supported)
			* 5.5 Mbps (short preamble supported)
			* 11.0 Mbps (short preamble supported)
			* 6.0 Mbps
			* 9.0 Mbps
			* 12.0 Mbps
			* 18.0 Mbps
			* 24.0 Mbps
			* 36.0 Mbps
			* 48.0 Mbps
			* 54.0 Mbps
		Frequencies:
			* 2412 MHz [1] (2.0 dBm)
			* 2417 MHz [2] (2.0 dBm)
			* 2422 MHz [3] (2.0 dBm)
			* 2427 MHz [4] (2.0 dBm)
			* 2432 MHz [5] (2.0 dBm)
			* 2437 MHz [6] (2.0 dBm)
			* 2442 MHz [7] (2.0 dBm)
			* 2447 MHz [8] (2.0 dBm)
			* 2452 MHz [9] (2.0 dBm)
			* 2457 MHz [10] (2.0 dBm)
			* 2462 MHz [11] (2.0 dBm)
			* 2467 MHz [12] (disabled)
			* 2472 MHz [13] (disabled)
			* 2484 MHz [14] (disabled)
	Band 2:
		Capabilities: 0x17e
			HT20/HT40
			SM Power Save disabled
			RX Greenfield
			RX HT20 SGI
			RX HT40 SGI
			RX STBC 1-stream
			Max AMSDU length: 3839 bytes
			No DSSS/CCK HT40
		Maximum RX AMPDU length 65535 bytes (exponent: 0x003)
		Minimum RX AMPDU time spacing: No restriction (0x00)
		HT TX/RX MCS rate indexes supported: 0-7
		VHT Capabilities (0x31800120):
			Max MPDU length: 3895
			Supported Channel Width: neither 160 nor 80+80
			short GI (80 MHz)
			RX antenna pattern consistency
			TX antenna pattern consistency
		VHT RX MCS set:
			1 streams: MCS 0-9
			2 streams: not supported
			3 streams: not supported
			4 streams: not supported
			5 streams: not supported
			6 streams: not supported
			7 streams: not supported
			8 streams: not supported
		VHT RX highest supported: 0 Mbps
		VHT TX MCS set:
			1 streams: MCS 0-9
			2 streams: not supported
			3 streams: not supported
			4 streams: not supported
			5 streams: not supported
			6 streams: not supported
			7 streams: not supported
			8 streams: not supported
		VHT TX highest supported: 0 Mbps
		Bitrates (non-HT):
			* 6.0 Mbps
			* 9.0 Mbps
			* 12.0 Mbps
			* 18.0 Mbps
			* 24.0 Mbps
			* 36.0 Mbps
			* 48.0 Mbps
			* 54.0 Mbps
		Frequencies:
			* 5180 MHz [36] (16.0 dBm)
			* 5200 MHz [40] (16.0 dBm)
			* 5220 MHz [44] (16.0 dBm)
			* 5240 MHz [48] (16.0 dBm)
			* 5260 MHz [52] (16.0 dBm) (radar detection)
			* 5280 MHz [56] (16.0 dBm) (radar detection)
			* 5300 MHz [60] (15.0 dBm) (radar detection)
			* 5320 MHz [64] (15.0 dBm) (radar detection)
			* 5500 MHz [100] (14.0 dBm) (radar detection)
			* 5520 MHz [104] (14.0 dBm) (radar detection)
			* 5540 MHz [108] (14.0 dBm) (radar detection)
			* 5560 MHz [112] (14.0 dBm) (radar detection)
			* 5580 MHz [116] (13.0 dBm) (radar detection)
			* 5600 MHz [120] (13.0 dBm) (radar detection)
			* 5620 MHz [124] (13.0 dBm) (radar detection)
			* 5640 MHz [128] (13.0 dBm) (radar detection)
			* 5660 MHz [132] (13.0 dBm) (radar detection)
			* 5680 MHz [136] (13.0 dBm) (radar detection)
			* 5700 MHz [140] (13.0 dBm) (radar detection)
			* 5720 MHz [144] (12.0 dBm) (radar detection)
			* 5745 MHz [149] (12.0 dBm)
			* 5765 MHz [153] (12.0 dBm)
			* 5785 MHz [157] (12.0 dBm)
			* 5805 MHz [161] (13.0 dBm)
			* 5825 MHz [165] (13.0 dBm)
			* 5845 MHz [169] (disabled)
			* 5865 MHz [173] (disabled)
	Supported commands:
		 * new_interface
		 * set_interface
		 * new_key
		 * start_ap
		 * new_station
		 * new_mpath
		 * set_mesh_config
		 * set_bss
		 * authenticate
		 * associate
		 * deauthenticate
		 * disassociate
		 * join_ibss
		 * join_mesh
		 * remain_on_channel
		 * set_tx_bitrate_mask
		 * frame
		 * frame_wait_cancel
		 * set_wiphy_netns
		 * set_channel
		 * set_wds_peer
		 * tdls_mgmt
		 * tdls_oper
		 * probe_client
		 * set_noack_map
		 * register_beacons
		 * start_p2p_device
		 * set_mcast_rate
		 * connect
		 * disconnect
		 * channel_switch
		 * set_qos_map
		 * set_multicast_to_unicast
	software interface modes (can always be added):
		 * AP/VLAN
		 * monitor
	valid interface combinations:
		 * #{ IBSS } <= 1, #{ managed, AP, mesh point, P2P-client, P2P-GO } <= 2,
		   total <= 2, #channels <= 1, STA/AP BI must match
	HT Capability overrides:
		 * MCS: ff ff ff ff ff ff ff ff ff ff
		 * maximum A-MSDU length
		 * supported channel width
		 * short GI for 40 MHz
		 * max A-MPDU length exponent
		 * min MPDU start spacing
	Device supports TX status socket option.
	Device supports HT-IBSS.
	Device supports SAE with AUTHENTICATE command
	Device supports low priority scan.
	Device supports scan flush.
	Device supports AP scan.
	Device supports per-vif TX power setting
	Driver supports full state transitions for AP/GO clients
	Driver supports a userspace MPM
	Device supports active monitor (which will ACK incoming frames)
	Device supports configuring vdev MAC-addr on create.
	max # scan plans: 1
	max scan plan interval: -1
	max scan plan iterations: 0
	Supported TX frame types:
		 * IBSS: 0x00 0x10 0x20 0x30 0x40 0x50 0x60 0x70 0x80 0x90 0xa0 0xb0 0xc0 0xd0 0xe0 0xf0
		 * managed: 0x00 0x10 0x20 0x30 0x40 0x50 0x60 0x70 0x80 0x90 0xa0 0xb0 0xc0 0xd0 0xe0 0xf0
		 * AP: 0x00 0x10 0x20 0x30 0x40 0x50 0x60 0x70 0x80 0x90 0xa0 0xb0 0xc0 0xd0 0xe0 0xf0
		 * AP/VLAN: 0x00 0x10 0x20 0x30 0x40 0x50 0x60 0x70 0x80 0x90 0xa0 0xb0 0xc0 0xd0 0xe0 0xf0
		 * mesh point: 0x00 0x10 0x20 0x30 0x40 0x50 0x60 0x70 0x80 0x90 0xa0 0xb0 0xc0 0xd0 0xe0 0xf0
		 * P2P-client: 0x00 0x10 0x20 0x30 0x40 0x50 0x60 0x70 0x80 0x90 0xa0 0xb0 0xc0 0xd0 0xe0 0xf0
		 * P2P-GO: 0x00 0x10 0x20 0x30 0x40 0x50 0x60 0x70 0x80 0x90 0xa0 0xb0 0xc0 0xd0 0xe0 0xf0
		 * P2P-device: 0x00 0x10 0x20 0x30 0x40 0x50 0x60 0x70 0x80 0x90 0xa0 0xb0 0xc0 0xd0 0xe0 0xf0
	Supported RX frame types:
		 * IBSS: 0x40 0xb0 0xc0 0xd0
		 * managed: 0x40 0xb0 0xd0
		 * AP: 0x00 0x20 0x40 0xa0 0xb0 0xc0 0xd0
		 * AP/VLAN: 0x00 0x20 0x40 0xa0 0xb0 0xc0 0xd0
		 * mesh point: 0xb0 0xc0 0xd0
		 * P2P-client: 0x40 0xd0
		 * P2P-GO: 0x00 0x20 0x40 0xa0 0xb0 0xc0 0xd0
		 * P2P-device: 0x40 0xd0
	Supported extended features:
		* [ VHT_IBSS ]: VHT-IBSS
		* [ RRM ]: RRM
		* [ FILS_STA ]: STA FILS (Fast Initial Link Setup)
		* [ CQM_RSSI_LIST ]: multiple CQM_RSSI_THOLD records
		* [ CONTROL_PORT_OVER_NL80211 ]: control port over nl80211
		* [ TXQS ]: FQ-CoDel-enabled intermediate TXQs
```

``` console
$ cat hostapd.conf
* ht_capab=[HT40+][HT40-][GF][SHORT-GI-20][SHORT-GI-40][RX-STBC-1]
* vht_capab=[MAX-A-MPDU-LEN-EXP3][SHORT-GI-80][RX-STBC-1][RX-ANTENNA-PATTERN][TX-ANTENNA-PATTERN]
```
