## USB WiFi adapters and Realtek `out-of-kernel` drivers

Important: Starting with WiFi 7 drivers, all Linux WiFi drivers must be Linux Standards Compliant (mac80211). Code has been merged into the Linux kernel to prevent WiFi 7 drivers that are not standards compliant from working. I view this as a very good thing and hope it prompts Realtek to develop and maintain standards compliant USB drivers. Mediatek released their WiFi 7 mt7925e chip during mid-2024 and cards were on the market shortly thereafter. The first mt7925u based USB WiFi adapter was released in July 0f 2025 by Netgear. It is called the A9000 and is shown in The Plug and Play List. The standards compliant mt7925e and mt7925u drivers were merged into Linux kernel 6.7 in early 2024. I have an M.2 card based on the mt7925 chip that works well and I now have a Netgear A9000 that I am testing.

At this time, 2025-09-07, my overall recommendation for WiFi 6 and WiFi 7 is to seek out adapters and modules based on Mediatek chips. See the Plug and Play  List. This recommendation may be ammended later this year.

WiFi 5 Status: During 2024, a major effort was undertaken to eliminate the need for the Realtek WiFi 5 out-of-kernel drivers. The Realtek out-of-kernel USB drivers are not good for general public use so an effort was started to write new and enhance existing WiFi 5 drivers that are standards compliant and will be maintained in the Linux mainline kernel. This effort was started by Larry Finger, Bitterblue Smith and Nick Morrow. Larry Finger passed away in May of 2024 but we pressed on. Many enhancements had to be made to the existing rtw88 USB drivers and along the way, new drivers for the rtl8812au, rtl8821/11au and rtl8814au chips were written. The rtl8812au and rtl8821/11au drivers were merged into kernel 6.14. The rtl8814au driver was merged into kernel 6.16.

If you are interested in helping test and make the rtw88 WiFi 5 drivers better, please proceed to the following site:

https://github.com/lwfinger/rtw88

Note: If you want to use the new drivers for rtl8812au and rtl8821/11au (kernel 6.14) or the new driver for rtl8814au (kernel 6.16) on kernels that are earlier than the ones where support started, the above repo above is your best option.

The overall list of USB WiFi 5 chipsets that are supported:

```
USB : RTW8814AU, RTW8812AU, RTW8821AU, RTW8811AU, RTW8822BU, RTW8812BU
USB : RTW8822CU, RTW8812CU, RTW8821CU, RTW8811CU, RTW8723DU
```

Given this news, my plan is to discontinue maintenance on the Realtek WiFi 5 out-of-kernel drivers maintained at this site with kernel 6.14.

WiFi 6 and 7 Status: Early in 2025, a major effort was undertaken to eliminate the need for the Realtek WiFi 6 out-of-kernel drivers and to add a WiFi 7 driver. The Realtek out-of-kernel USB drivers are not good for general public use so an effort was started to write new WiFi 6 drivers that are standards compliant and will be maintained in the Linux mainline kernel. This effort was started by Bitterblue Smith. The rtl8851bu and rtl8852bu drivers were merged into kernel 6.17 with plans for rtl8852au, rtl8852cu and rtl8922au in action.

If you are interested in helping test and make the rtw89 WiFi 6 and 7 drivers better, please proceed to the following site:

[https://github.com/lwfinger/rtw88](https://github.com/morrownr/rtw89)

Note: If you want to use the new drivers for rtl8851bu and rtl852bu (kernel 6.17) on kernels that are earlier than the ones where support started, the above repo above is your best option.

Given this news, my plan is to discontinue maintenance on the Realtek WiFi 6 rtl8852/32bu driver with kernel 6.16. No plan for discontonuing support for the rtl8852/32cu is planned for now.

-----

The following Realtek WiFi 6 drivers are maintained at this site. They are not standards compliant but this is all that we had until the above repo came online this year:

rtl8852/32bu : https://github.com/morrownr/rtl8852bu-20240418

rtl8852/32cu : https://github.com/morrownr/rtl8852cu-20240510

Regards and enjoy your wifi,

@morrownr




