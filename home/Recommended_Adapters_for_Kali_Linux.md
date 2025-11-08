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

Note: Specific Realtek WiFi 5 based adapters are being added to this
list. The addition of these Realtek adapters is based on the use of the
new, MODERN, mac80211, drivers that are in the Linux kernel as the rtw88
driver series as of the following schedule: Realtek rtl8812au,
rtl8821/11au chips (kernel 6.14) and the rtl8814au chip (kernel 6.16).
If you have an earlier kernel, it is possible to install the rtw88 driver
series by going to:

https://github.com/lwfinger/rtw88

Note: All listed adapters are 1) single-state (no Windows driver onboard), 2) single-function (wifi only) and 3) use Linux standards-compliant, in-kernel drivers. These 3 characteristics contribute to the adapters being stable, reliable and easy to use.

| Adapter                                      | Chipset   | Class   | Bands     | USB Version | WPA3 | Range     |
|----------------------------------------------|-----------|---------|-----------|-------------|------|-----------|
| ALFA AWUS036ACS [1] [4]                      | rtl8811au | AC600   | 2.4, 5    | 2           | Yes  | Long      |
| ALFA AWUS036ACHM [1] [2]                     | mt7610u   | AC600   | 2.4, 5    | 2           | Yes  | Very Long |
| Panda PAU0B [1] [2]                          | mt7610u   | AC600   | 2.4, 5    | 2           | Yes  | Very Long |
| ASUS USB-AC51 [2]                            | mt7610u   | AC600   | 2.4, 5    | 2           | Yes  | Medium    |
| ALFA AWUS036ACH [1] [4]                      | rtl8812au | AC1200  | 2.4, 5    | 3           | Yes  | Very Long |
| ALFA AWUS036ACM [1] [2]                      | mt7612u   | AC1200  | 2.4, 5    | 3           | Yes  | Long      |
| Panda PAU0D  [2]                             | mt7612u   | AC1200  | 2.4, 5    | 3           | Yes  | Long      |
| ALFA AWUS1900 [1] [4]                        | rtl8814au | AC1900  | 2.4, 5    | 3           | Yes  | Long      |
| EDUP EP-AX1672 [1] [3]                       | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Long      |
| Panda PAU0F [3]                              | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Long      |
| ALFA AWUS036AXML [1] [3]                     | mt7921aun   | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Long      |
| Netgear A8000 [3]                            | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Long      |

Note: The new Netgear A9000, mt7925 chip, WiFi 7, is available and I am testing this adapter. Range appears to be very good. I will try to make a decision as to whether this new adapter will be included here by the end of this year.

Note: Information about and links to most of the above adapters can be found in the [Plug and Play List](https://github.com/morrownr/USB-WiFi/blob/main/home/USB_WiFi_Adapters_that_are_supported_with_Linux_in-kernel_drivers.md).

[1] I have first hand experience with this adapter.

[2] Supports Active Monitor Mode.

[3] Monitor mode works well, very well, but Active Monitor Mode appears to be broken for now (2024-09-15). Active Monitor Mode is a feature within Monitor Mode that only a few users need it so it may not be an issue for you. Edit on 2025-01-15: I am seeing some reports that Active Monitor mode is now working on the mt7921au chip with kernel 6.12 and later. I have not confirmed this myself so further user reports would be helpful.

[4] Support for the rtl8812au and rtl8821/11au chipsets was merged into kernels 6.13 and 6.14, therefore, kernel 6.14 is needed to use these chipsets unless you are willing to compile and install a driver. Support for the rtl8814au chipset was merged into kernels 6.15 and 6.16, therefore, kernel 6.16 is needed to use these chipsets unless you are willing to compile and install a driver. If you are willing to compile and install a driver that is based on the same source as the in-kernel driver, go to the following repo and follow the instructions:

https://github.com/lwfinger/rtw88

Note: Your input to maintain this list is welcome. Please report the results of your testing in `issues`.
