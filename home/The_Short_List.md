## The Short List - Superstar USB WiFi adapters for Linux

"I plugged it in and it just works™" 

Note: [The Plug and Play List](./USB_WiFi_Adapters_that_are_supported_with_Linux_in-kernel_drivers.md) has many more adapters listed as well as reviews and links to online sellers.

Note: All listed adapters are single-state (no Windows driver onboard) and single-function (wifi only).

| Adapter                                      | Chipset   | Class   | Bands     | USB Version | WPA3 | Range     |
|----------------------------------------------|-----------|---------|-----------|-------------|------|-----------|
| EDUP EP-AX1672[1][2]                         | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Long      |
| Netgear A8000                                | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Medium    |
| Panda PAU0F                                  | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Medium    |
| ALFA AWUS036AXM                              | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Long      |
| Edimax EW-7822UTC[1]                         | rtl8822bu | AC1200  | 2.4, 5    | 3           | Yes  | Short[5]  |
| ALFA AWUS036ACM[1][2]                        | mt7612u   | AC1200  | 2.4, 5    | 3           | Yes  | Long      |
| Panda PAU0D                                  | mt7612u   | AC1200  | 2.4, 5    | 3           | Yes  | Long      |
| ALFA AWUS036ACHM[1][2][3]                    | mt7610u   | AC600   | 2.4, 5    | 2           | Yes  | Very Long |
| Asus USB-AC51                                | mt7610u   | AC600   | 2.4, 5    | 2           | Yes  | Medium    |
| Panda PAU0B                                  | mt7610u   | AC600   | 2.4, 5    | 2           | Yes  | Long      |
| Panda PAU09                                  | rt5572    | N600    | 2.4, 5    | 2           | Yes  | Long      |
| Panda PAU03[1] (nano)                        | rt5370    | N150    | 2.4       | 2           | Yes  | Short     |
| Panda PAU04                                  | rt5370    | N150    | 2.4       | 2           | Yes  | Medium    |
| CanaKit BC19675                              | rt5370    | N150    | 2.4       | 2           | Yes  | Short     |
| EDUP EP-MS8551[1][4]                         | mt7601u   | N150    | 2.4       | 2           | Yes  | Very Long |
| Zibo-6467115[1][4] (nano)                    | mt7601u   | N150    | 2.4       | 2           | Yes  | Short     |
| ALFA AWUS036NHA                              | ar9271    | N150    | 2.4       | 2           | Yes  | Long      |

```
[1]: I have first hand experience with this adapter.
[2]: Excellent for 5 GHz AP mode (works well with a Raspberry Pi 4B)
[3]: Outstanding for 2.4 GHz AP mode
[4]: Use only for client (managed) mode. No AP mode. Limited monitor mode.
[5]: Wireless range is roughly estimated.
```

Criteria to make The Short List: 

1. Uses an In-kernel driver (adapter is plug and play).
2. Has either a documented track record or my own testing experience.
3. Is available to purchase as a new product.

USB WiFi adapters come in various shapes, sizes and speeds. Their capabilities
can vary greatly. The adapter that you pick needs to be chosen based on its
ability to do the job that you need it to do.
