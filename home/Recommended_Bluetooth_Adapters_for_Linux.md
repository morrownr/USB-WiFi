## Recommended Bluetooth Adapters for Linux

I have started this list because of my strong recommendation to Linux users to avoid USB WiFi adapters that include bluetooth support. I have seen too many problems with combo adapters over the years. There are technical reasons for the problems that users see with combo adapters and problems happen on both Linux and Windows. I will explain this in detail on this page as I have time. It will take some time for this page to become as useful as we need and I could certainly use a partner to maintain this page. If interested, leave me a message in Issues.

@morrownr



| Adapter                         | Chipset   | Ver | Price    | Link                                                               |
|---------------------------------|-----------|-----|----------|--------------------------------------------------------------------|
| EDUP EP-B3536 [1] [4]           | rtl8761BU | 5.1 | 10 USD   | https://amazon.com/dp/B09KG7QQ5V                                   |
| Baseus BA04 [1]                 | rtl8761BU | 5.1 | 12 USD   | https://aliexpress.com/item/1005005187191049.html                  |
| EVEO [1] [2]                    | rtl8761BU | 5.1 | 10 USD   | https://www.amazon.com/EVEO-Bluetooth-Adapter-PC-5-1/dp/B0957NZNC2 |
| TP-Link UB500 Plus [3]          | rtl8761BU | 5.3 | 20 USD   | https://www.amazon.com/TP-Link-Adjustable-Controller-UB500-Plus/dp/B0DKFXGR21 |


[1] supported in kernel 5.14 and later.

[2] Review: https://bioslevel.com/review/the-best-usb-bluetooth-dongle-for-linux/

[3] The UB500 Plus shows as a v5.3 adapter while still using the rtl8761bu chipset. It is my understanding that the difference between BT 5.1 and 5.3 only requires additional driver/firmware support, not a new chipset. It appears that you may need to be using kernel 6.8 or later for this adapter.

[4] Review: I have been using the EDUP EP-B3536 for a few months now. It is a VERY reliable adapter with very long range for bluetooth. I have used it with a mouse, keyboard and headset with no compatibility problems. The Linux driver/firmware appear to be VERY GOOD.

Note: Your input to maintain this list is welcome.
