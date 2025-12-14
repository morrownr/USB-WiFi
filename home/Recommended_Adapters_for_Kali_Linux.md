2025-12-14

Maintained by @morrownr

## Recommended Adapters for Kali Linux

Kali and other distros used for pen testing, security analysis and other
monitor mode work need usb wifi adapters that have drivers
that do an excellent job of supporting monitor mode. This list of
adapters is based on many conversations and a lot of testing. There are
other adapters that may work but this list is designed to be a list of
the best adapters that are available for purchase new at this time at
reasonable prices.

Note: The adapter that best meets your needs can depend on exactly what
you plan to do so asking questions is a good idea.

VERY IMPORTANT: All information in this document concerns the in-kernel,
mac80211, Linux drivers as are available in the Linux kernel in the
various series of driver known as mt76, rtw88 and rtw89. The old,
depreciated Realtek out-of-kernel drivers have never done a good
job with monitor mode and will not be considered in this document. Here
is a short rundown of some of the monitor mode features in the mentioned
series of drivers:

mt76 - supports monitor mode, packet injection, VIF and active monitor
mode (2025-12-14 - monitor mode is current brokden in the mt7921u
driver as of kernel 6.18 and possibly some earlier kernels).

rtw88 - support monitor mode and packet injection. Does not support
active monitor mode or VIF.

rtw88 - support monitor mode, packet injection and VIF. Does not support
active monitor mode.

Note: Specific Realtek WiFi 5 based adapters have been added to this
list. The addition of these Realtek adapters is based on the use of the
new, MODERN, mac80211, drivers that are in the Linux kernel as the rtw88
driver series as of the following schedule: Realtek rtl8812au,
rtl8821/11au chips (kernel 6.14) and the rtl8814au chip (kernel 6.16).
If you have an earlier kernel, it is possible to install the rtw88 driver
series by going to:

https://github.com/lwfinger/rtw88

Note: All listed adapters are 1) single-state (no Windows driver onboard), 2) single-function (wifi only) and 3) use Linux standards-compliant, in-kernel drivers. These 3 characteristics contribute to the adapters being stable, reliable and easy to use.

Note: I am currently in the process of testing drivers and specific adapter for monitor mode performance. You can go down to [10] to see the reports as I am able to post them.

| Adapter                                      | Chipset   | Class   | Bands     | USB | VIF | Active | WPA3 | Range     |
|----------------------------------------------|-----------|---------|-----------|-----|-----|--------|------|-----------|
| ALFA AWUS036ACS [1] [4] (WiFi 5)             | rtl8811au | AC600   | 2.4, 5    | 2   | No  | No     | Yes  | Long      |
| ALFA AWUS036ACHM [1] (WiFi 5)                | mt7610u   | AC600   | 2.4, 5    | 2   | Yes | Yes    | Yes  | Very Long |
| Panda PAU0B [1] (WiFi 5)                     | mt7610u   | AC600   | 2.4, 5    | 2   | Yes | Yes    | Yes  | Very Long |
| ASUS USB-AC51 (WiFi 5)                       | mt7610u   | AC600   | 2.4, 5    | 2   | Yes | Yes    | Yes  | Medium    |
| ALFA AWUS036ACH [1] [4] (WiFi 5)             | rtl8812au | AC1200  | 2.4, 5    | 3   | No  | No     | Yes  | Very Long |
| ALFA AWUS036ACM [1] (WiFi 5)                 | mt7612u   | AC1200  | 2.4, 5    | 3   | Yes | Yes    | Yes  | Long      |
| Panda PAU0D (WiFi 5)                         | mt7612u   | AC1200  | 2.4, 5    | 3   | Yes | Yes    | Yes  | Long      |
| ALFA AWUS1900 [1] [4] (WiFi 5)               | rtl8814au | AC1900  | 2.4, 5    | 3   | No  | No     | Yes  | Long      |
| EDUP EP-AX1672 [1] [3] (WiFi 6)              | mt7921au  | AXE3000 | 2.4, 5, 6 | 3   | Yes | ?      | Yes  | Long      |
| Panda PAU0F [3] (WiFi 6)                     | mt7921au  | AXE3000 | 2.4, 5, 6 | 3   | Yes | ?      | Yes  | Long      |
| ALFA AWUS036AXML [1] [3] (WiFi 6)            | mt7921aun | AXE3000 | 2.4, 5, 6 | 3   | Yes | ?      | Yes  | Long      |
| Netgear A8000 [3] (WiFi 6)                   | mt7921au  | AXE3000 | 2.4, 5, 6 | 3   | Yes | ?      | Yes  | Long      |
| Brostrend AX9L [1] [3] (WiFi 6)              | mt7921au  | AXE3000 | 2.4, 5, 6 | 3   | Yes | ?      | Yes  | Long      |
| Netgear A9000 [1] (WiFi 7)                   | mt7925u   | BE6500  | 2.4, 5, 6 | 3   | Yes | Yes    | Yes  | Long      |

Note: Information about and links to most of the above adapters can be found in the [Plug and Play List](https://github.com/morrownr/USB-WiFi/blob/main/home/USB_WiFi_Adapters_that_are_supported_with_Linux_in-kernel_drivers.md).

[1] I have first hand experience with this adapter.

[3] Monitor mode works well, very well, but Active Monitor Mode appears to be broken for now (2024-09-15). Active Monitor Mode is a feature within Monitor Mode that only a few users need it so it may not be an issue for you. Edit on 2025-01-15: I am seeing some reports that Active Monitor mode is now working on the mt7921au chip with kernel 6.12 and later. I have not confirmed this myself so further user reports would be helpful.

[4] Support for the rtl8812au and rtl8821/11au chipsets was merged into kernels 6.13 and 6.14, therefore, kernel 6.14 is needed to use these chipsets unless you are willing to compile and install a driver. Support for the rtl8814au chipset was merged into kernels 6.15 and 6.16, therefore, kernel 6.16 is needed to use these chipsets unless you are willing to compile and install a driver. If you are willing to compile and install a driver that is based on the same source as the in-kernel driver, go to the following repo and follow the instructions:

https://github.com/lwfinger/rtw88

Note: Your input to maintain this list is welcome. Please report the results of your testing in `issues`.

[10] The following is a list of monitor mode testing results. It can take a lot of time to do this work. Expect me to be updating this list over the next few months.

The Netgear A9000 passes all monitor mode tests. It uses the mt7925u driver. Details as follows:

```
2025-12-07
Adapter: Netgear A9000 (WiFi 7, BE6500, tri-band)
state: single, no Windows driver onboard.
driver: mt7925u
version: 6.18.0-v8+
firmware-version: ____000000-20251124093023
VIF: valid interface combinations:
         * #{ managed, P2P-client } <= 2, #{ P2P-GO } <= 1, #{ P2P-device } <= 1,
           total <= 3, #channels <= 2
         * #{ managed, P2P-client } <= 2, #{ AP } <= 1, #{ P2P-device } <= 1,
           total <= 3, #channels <= 1
SSIDs deteched: sudo iw dev wlan0 scan | grep SSID:  - 12
SSIDs deteched: sudo nmcli dev wifi list - 28
*
Test 1: Is monitor mode and packet injection working?
Command line: sudo aireplay-ng --test wlan0mon
  Trying broadcast probe requests...
  Injection is working!
Result: Pass
*
Test 2: Is monitor mode and packet injection working?
Command line: sudo hcxdumptool --tot=2 --rcascan=active
  17815 Packet(s) captured by kernel
  663 Packet(s) dropped by kernel
  exit on TOT
Result: Pass
*
Test3: Is active monitor mode capability working:?
Command line: sudo hcxdumptool --tot=2 --rcascan=active -A
  12454 Packet(s) captured by kernel
  108 Packet(s) dropped by kernel
  exit on TOT
Result: Pass, device supports active monitor (which will ACK incoming frames)
iw list: shows support
*
Test4: How long does it take to successfully attack a target:
Command line: time sudo hcxdumptool --exitoneapol=14
  1494 Packet(s) captured by kernel
  0 Packet(s) dropped by kernel
  exit on EAPOL M1M2ROGUE
  real	0m19.336s
  user	0m0.005s
  sys	0m0.025s
*
```
