## The Short List - Superstar USB WiFi adapters for Linux

"I plugged it in and it just works™" 

Note: [The Plug and Play List](./USB_WiFi_Adapters_that_are_supported_with_Linux_in-kernel_drivers.md) has many more adapters listed as well as reviews and links to online sources.

| Adapter                                      | Chipset   | Class   | Bands     | USB Version | WPA3 | Range     | State[^state] |
|----------------------------------------------|-----------|---------|-----------|-------------|------|-----------|---------------|
| ALFA AWUS036AXML                             | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Long      | Single        |
| Netgear A8000                                | mt7921au  | AXE3000 | 2.4, 5, 6 | 3           | Yes  | Long      | Single        |
| ALFA AWUS036ACM[^firsthand][^5GHz]           | mt7612u   | AC1200  | 2.4, 5    | 3           | Yes  | Long      | Single        |
| TEROW ROW02CD[^firsthand][^5GHz]             | mt7612u   | AC1200  | 2.4, 5    | 3           | Yes  | Long      | Single        |
| ALFA AWUS036ACU[^firsthand][^kernel6.3]      | rtl8812bu | AC1200  | 2.4, 5    | 3           | Yes  | Long      | Single        |
| ALFA AWUS036ACHM[^firsthand][^5GHz][^2.4GHz] | mt7610u   | AC600   | 2.4, 5    | 2           | Yes  | Very Long | Single        |
| Panda PAU0B                                  | mt7610u   | AC600   | 2.4, 5    | 2           | Yes  | Long      | Single        |
| Linksys AE6000[^firsthand]                   | mt7610u   | AC580   | 2.4, 5    | 2           | Yes  | Medium    | Single        |
| Panda PAU09                                  | rt5572    | N600    | 2.4, 5    | 2           | Yes  | Long      | Single        |
| Panda PAU03[^firsthand] (nano)               | rt5370    | N150    | 2.4       | 2           | Yes  | Short     | Single        |
| Panda PAU04                                  | rt5370    | N150    | 2.4       | 2           | Yes  | Medium    | Single        |
| CanaKit BC19675                              | rt5370    | N150    | 2.4       | 2           | Yes  | Short     | Single        |
| EDUP EP-MS8551[^firsthand][^client]          | mt7601u   | N150    | 2.4       | 2           | Yes  | Very Long | Single        |
| Zibo-6467115[^firsthand][^client] (nano)     | mt7601u   | N150    | 2.4       | 2           | Yes  | Short     | Single        |
| ALFA AWUS036NHA                              | ar9271    | N150    | 2.4       | 2           | Yes  | Long      | Single        |
| WiFi Nation WN-H3                            | ar9271    | N150    | 2.4       | 2           | Yes  | Long      | Single        |

[^firsthand]: I have first hand experience with this adapter.
[^5GHz]: Excellent for 5 GHz AP mode (works well with a Raspberry Pi 4B)
[^2.4GHz]: Outstanding for 2.4 GHz AP mode
[^client]: Use only for client (managed) mode. No AP mode. Limited monitor mode.
[^state]: Single state is preferred.
[^kernel6.3]: In-kernel driver available with kernel 6.3 or later.

Criteria to make The Short List: 

1. Uses an In-kernel driver (adapter is plug and play).
2. Has either a documented track record or my own testing experience.
3. Is available to purchase as a new product.

USB WiFi adapters come in various shapes, sizes and speeds. Their capabilities
can vary greatly. The adapter that you pick needs to be chosen based on its
ability to do the job that you need it to do.
