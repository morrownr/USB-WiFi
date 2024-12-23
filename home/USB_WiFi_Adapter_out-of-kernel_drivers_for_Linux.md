## USB WiFi adapters with Linux `out-of-kernel` drivers

Important: Starting with WiFi 7 drivers, all Linux WiFi drivers must be Linux Standards Compliant (mac80211). Code has been merged into the Linux kernel to prevent WiFi 7 drivers that are not standards compliant from working. I view this as a very good thing and hope it prompts Realtek to development and maintain standards compliant drivers. Mediatek released their WiFi 7 mt7925e chip during mid-2024 and has plans for the WiFi 7 USB version of the mt7925. The standards compliant mt7925e and mt7925u drivers were merged into Linux kernel 6.7 in early 2024. I have an M.2 card based on the mt7925 chip and it works well.

My overall recommendation for WiFi 6 and WiFi 7 is to seek out adapters and modules based on Mediatek chips. See the Plug and Play  List.

Back to topic: During 2024, a major effort was undertaken to eliminate the need to for these Realtek WiFi 5 out-of-kernel drivers. These Realtek drivers are not good for general public use so an effort was started to write new and enhance existing WiFi 5 drivers that are standards compliant and will be maintained in the Linux mainline kernel. This effort was started by Larry Finger, Bitterblue Smith and Nick Morrow. Larry Finger passed away in May of 2024 but we pressed on. Many enhancements had to be made to the existing rtw88 USB drivers and along the way, new drivers for the rtl8812au, rtl8821/11au and rtl8814au chips were written. The rtl8812au and rtl8821/11au driver were merged into kernel 6.13 and it is planned for the rtl8814au driver to be merged into kernel 6.15.

If you are interested in helping test and make the rtw88 WiFi 5 drivers better, please proceed to the following site:

https://github.com/lwfinger/rtw88

We have immediate need for rtl8814au testers. The overall list of USB WiFi 5 chipsets that are supported:

USB : RTW8814AU, RTW8812AU, RTW8821AU, RTW8811AU, RTW8822BU, RTW8812BU
USB : RTW8822CU, RTW8812CU, RTW8821CU, RTW8811CU, RTW8723DU

Given this news, my plan is to discontinue maintenance on the Realtek WiFi 5 out of kernel drivers with kernel 6.12. I plan to continue to support WiFi 6 Realtek drivers for the rtl8852/32bu and rtl8852/32cu chips. I will add links to these drivers soon.





