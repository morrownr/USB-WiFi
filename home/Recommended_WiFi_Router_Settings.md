## Recommended WiFi Router/ Access Point Settings

2021-11-12

Note: This documentment is aimed at Linux users that have WiFi adapters and cards that use in-kernel drivers.

Note: These are general recommendations, some of which may not apply to your specific situation.

Security: Set `WPA3-SAE` or `WPA3-SAE/WPA2-AES Mixed` or `WPA2-AES`. Do not set `WPA2 Mixed` or `WPA` or `WEP` or `TKIP`.

Channel width for 2.4G: Set 20 MHz fixed width. Do not use 40 MHz or 20/40 automatic.

Channels for 2.4G: Set channel 1 or 6 or 11 depending on the congestion at your location. Do not set automatic channel selection.

Mode for 2.4G: For best performance, set "N only" if you no longer use B or G capable devices.

Network names: Do not set the 2.4G Network and the 5G Network to the same name. Note: Unfortunately many routers come with both networks set to the same name. If both networks are set to the same name, I recommend you change one to ensure different network names.

Channels for 5G: Not all devices are capable of using DFS channels. Roku TV devices are a good example. It may be necessary to set a fixed channel in the range of 36 to 48 or 149 to 161 in order for all of your devices to work on 5g. (for US, other countries may vary)  Since 5G WiFi channels are often very lightly used, you could consider moving devices that can't use to 5G DFS channels to 2.4G so that the remaining 5G devices can enjoy uncongested operation. I do this and it works great.

Best location for the wifi router/ access point: Near center of apartment or house, at least a couple of feet away from walls, in an elevated location.

Check congestion: There are apps available for smart phones that allow you to check the congestion levels on wifi channels. The apps generally go by the name of WiFi Analyzer or something similar.

After making and saving changes, reboot the router.
