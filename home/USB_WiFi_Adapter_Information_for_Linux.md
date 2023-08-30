## USB WiFi adapter information for Linux

-----

Disclaimer: The authors and contributors to this site cannot be responsible for the results of your use of the information contained in or linked from this site. We attempt to provide accurate information but many factors that are beyond our control can contribute to less than expected results. You are responsible for ensuring the accuracy and applicability of any information you use to make a decision.

Foreword: There are many USB WiFi adapters that work without the need to install a driver in Linux. These [adapters](https://github.com/morrownr/USB-WiFi/blob/main/home/USB_WiFi_Adapters_that_are_supported_with_Linux_in-kernel_drivers.md) use drivers that are already in the Linux kernel. The in-kernel drivers are maintained in the kernel without the need for user intervention. With adapters that use in-kernel drivers, simply plug the adapter in and it will work (applies to most desktop/laptop distros as many server distros do not include wifi support but it can be added). Many people find that using adapters with in-kernel drivers is a better solution than using an adapter that requires drivers to be found (not easy to find the right driver), downloaded, compiled (confusing for those that are not developers) and installed (problematic, depending on the Linux distro and other factors).

-----

USB WiFi adapters provide flexibility as they are easily moved from one location to another and from one computer to another and can even be taken on the road. They come in models for USB 2 and USB 3 and often provide better reception than internal wifi cards. Some of the larger adapters work well for desktop use and the smaller adapters, including "nano" adapters, work well for laptops and travel. It is important that you pick an adapter to match the expected usage. If you are going to be traveling with the adapter, the adapters with long antennas may not not work well as the adapter may be broken. Many adapters with large antennas allow you to remove the antennas for travel but then you will have more things to keep track of. On the other hand, if you need an adapter for a desktop system that is a long distance from the AP/WiFi Router in your home or workplace, you probably need the better signal capability of the larger antennas. It is a good idea to research the issue before buying.

USB WiFi is viewed by the makers of WiFi hardware as a niche market within the wifi industry. Many wifi hardware makers do not supply USB WiFi chipsets. This means that choice is more limited than with other computer related product lines. There are only 2 companies currently supplying chipsets for USB Wifi adapters - Mediatek and Realtek. Intel is not supplying USB capable chipsets and Atheros is not supplying modern USB capable chipsets. Of the two suppliers that do provide USB Wifi chipsets, Mediatek supports drivers for their chipsets the right way, in-kernel. Mediatek drivers are Linux Wireless Standards compliant and are updated constantly without users having to worry about it. Realtek does not support their modern USB Wifi chipsets with in-kernel drivers. Realtek does make non-standards compliant Linux drivers but does not publicly release them or take problem reports. A very limited number of vendors post Realtek USB WiFi drivers at very irregular intervals. These drivers are released in source code format and must be compiled to be used. The Realtek drivers do not keep up with the needed changes as new kernels are released. This job seems to rest with folks like myself in the community. Am I a fan of how the Realtek USB team supports the Linux community? No. What do I recommend? Buy adapters based on chipsets from the company that is doing it right - Mediatek. The biggest problem most Linux users have when looking to purchase a USB WiFi adapter is being able to reliably identify which adapters have in-kernel support and that is the primary reason for this site. Spreading this information far and wide is key to having happy Linux users so please spread this information.

This [document](https://github.com/morrownr/USB-WiFi/blob/main/home/USB_WiFi_Adapters_that_are_supported_with_Linux_in-kernel_drivers.md) attempts to identify currently available adapters that use in-kernel driver support. Links are provided to online products. Information regarding out-of-kernel drivers and their quality is also provided in a separate [document](https://github.com/morrownr/USB-WiFi/blob/main/home/USB_WiFi_Adapter_out-of-kernel_drivers_for_Linux.md). The hope is that this information is of benefit to Linux users, experienced and new.

Important: While there are Realtek out-of-kernel drivers maintained at this site, having these drivers is not a recommendation for Linux users to buy USB WiFi adapters based on Realtek chipsets that are not supported with in-kernel drivers. Realtek out-of-kernel wifi drivers, such as the ones maintained here, are designed to be used by skilled programmers producing products such as embedded systems. Users of desktop distros such as Ubuntu, Debian, Manjaro, Fedora, Raspberry Pi OS and other mainline desktop distros will likely find adapters that use 
in-kernel drivers to be more stable and much more trouble-free. The following link will provide more information:

[USB WiFi adapters that are supported with Linux in-kernel drivers](https://github.com/morrownr/USB-

[Linux Wireless - Mediatek](https://wireless.wiki.kernel.org/en/users/drivers/mediatek) is a good place to get an idea of the various Mediatek wifi chipsets that are supported in the Linux kernel. If you want to look in the kernel to see the drivers, [look here](https://github.com/torvalds/linux/tree/master/drivers/net/wireless/mediatek). One of the biggest advantages of using adapters with in-kernel drivers is that any of us can report [bugs](https://wireless.wiki.kernel.org/en/users/documentation/reporting_bugs) and submit fixes. I recommend that you report bugs/issues here before taking the problem to the kernel devs as they are very busy and may ignore your report if the issue is not worked to the point where it is for sure something that requires a code change in the kernel drivers.

Warning: It is common for online retailers to post "Linux support." It is best to ignore "Linux support" in online ads as this statement is often misleading at best and false at worst. Most inexperienced users do not understand that the Linux kernel is under constant development which makes it necessary for drivers to be regularly updated in order to work on newer kernels. Out-of-kernel drivers sitting on a CD or on an adapter seller's web site do not get regular updates. Rule of thumb: Never attempt to install a Linux driver from a CD. Only consider downloading a Linux driver from an adapter seller's website if you confirm it supports the kernel you are using. The out-of-kernel drivers on that CD or seller's webisite will likely be old and will likely do nothing more than make a mess of your system. Remember that `sudo` is a weapon of mass destruction if used without knowing what you are doing. Another rule of thumb: Don't take hardware advice from Windows and MAC users. All major Linux distributions have active forums with users ready to give advice. Don't take advice from a single user but seek advice from several users and always ask if the adapter uses in-kernel drivers.

Some USB WiFi adapters have proprietary Windows drivers onboard. When plugged in, they act like a flash drive or CDROM and on Windows will attempt to start installing the Windows driver. That won't work on Linux or MAC or any other non-Windows OS so the adapter sits there in flash drive or CDROM mode. The problem is that the state of the adapter has to be changed for the adapter to show up as the device that you expect, in this case, a WiFi adapter. Most modern Linux distributions ship with a utility called [usb-modeswitch](https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Modeswitch.md) that will handle this issue for you if it has the correct information for your adapter. It is a good utility but if you buy adapters that are "multi-state," that is one more potential headache you may have to deal with when something goes wrong. Often you can identify adapters that are "multi-state" as they are advertised as "free driver" or "free installation driver." If you are looking to buy a USB WiFi adapter for use on Linux, MAC OS, NIX or anything besides Windows, it is a good idea to give preference to single-state adapters.

Warning: I will not list any products made by TP-Link and D-Link. Both companies regularly change chipsets while keeping the same model number on their products. This makes it very difficult for Linux users to identify products with a specific chipset with any degree of certainty. This also makes it difficult for me to post links and recommendations so I will not do so but that is okay because there are many good adapters available from other companies such as Alfa and Panda. TP-Link and D-Link's Linux support is very poor as their product support sites generally only contain very old Linux drivers that won't work with modern distros... if they post any drivers at all and neither company does a good job of supplying adapters that use in-kernel drivers. We know that Linux cannot be properly supported in the manner that both companies use. This is sad because both companies have made a lot of money from Linux by using it inside many of their products, yet they do not return the support. My recommendation is to avoid TP-Link and D-Link USB WiFi adapters.

On the other hand, I have to give a shout out to 2 companies that do an excellent job making adapters that work well with Linux: Alfa and Panda. Alfa makes very high quality adapters. Selected adapters use in-kernel drivers. They have Linux information on their website which provides tech support and links to out-of-kernel drivers for the adapters that do not use an in-kernel driver. Panda has a long history of only making USB adapters that use Linux in-kernel drivers. It is hard to go wrong with USB WiFi adapters from either company.

WPA3-SAE support: My testing over the last couple of years has shown very positive results for WPA3 as far as in-kernel drivers are concerned. I have tested USB WiFi adapters ranging from N150 to AXE3000. It appears that all of the adapters that use Mediatek/Ralink and Atheros chipsets and in-kernel drivers are working well regarding WPA3. Keep in mind that your Linux distro must support WPA3 for WPA3 to work. As of mid-2022, all distros that I use and test with are working well with WPA3. This includes Ubuntu 22.04 LTS and later as well as all of the official and unofficial versions of Ubuntu.

There is a question that is asked frequently by users of the Realtek out-of-kernel drivers that are maintained at this site. The question is `why don't you submit this driver to be included in the Linux kernel?` Answer: The Realtek out-of-kernel drivers are not Linux standards compliant, we don't have enough documentation and Realtek will not help. It would likely be easier to create new drivers but that would be a monumental task that is beyond the resources that are available in the user community. 

USB extension cables with cradles can be very useful with USB WiFi adapters as they will allow you to position the adapter for best performance. Cables for USB2 and USB3 are available. The following cables are not recommended but are shown as examples:

[StarTech.com 5ft USB 2.0 Extension Cable](https://www.amazon.com/5ft-Desktop-USB-Extension-Cable/dp/B001K9BFB8)

[Cablecc USB 3.0 Type-A Male to Female Extension Dock Station Docking Cable](https://www.amazon.com/Cablecc-Female-Extension-Station-Docking/dp/B07SH4RZ6S)

[WiFi Adapter Extension Cable with Pedestal](https://smile.amazon.com/gp/product/B08R2Y53QK?ref=em_1p_0_im&ref_=pe_3681270_598503160)

Note: Some adapters won't work with some extension cables and cradles. It is best to buy from retailers that will let you return their products as it seems the only way to know is trial and error.

[Right angle usb adapters](https://www.amazon.com/dp/B07S6B5X76) can be very handy when using USB WiFi adapters. This is especially true if you are using a Raspberry Pi or other small system with horizontal usb ports. Unlike extension cables, I have never seen a compatibility problem with right angle usb adapters.

-----

Summary: The Golden Rules to help you find the USB WiFi Adapter(s) that meets your needs

- You must research before buying. There are adapters of many sizes and capabilities. You need to define what capabilities and size you want before starting your search. Some questions to help you decide the capabilities and size you need:

```
Do you need long range?
Which channel bands do you need?
Which modes need to be supported? managed, monitor, AP, etc.
Are there specific capabilities that need to be supported? active monitor mode, etc.
```

- Avoid multi-state adapters. As previously noted, there are adapters that will first come up as flash drives or CD's so as to load a driver in Windows. This is an unnecessary feature that can cause problems...even for Windows users... who is going to update that Windows driver on the adapter as time passes? Nobody!

- Avoid multi-function adapters. Some adapters also have bluetooth capability. You do not want this. I have seen many problems with this over the years and bluetooth will likely limit the wifi to USB2 speeds. If you need bluetooth capability, go get a seaparate bluetooth adapter.

- A good quality adapter can save you a lot of anguish. There are a lot of poor quality adapters on the market. 

- Extension cables/stands and right angle usb adapters can greatly enhance the performance of your adapter. Use the shortest extension cable that will meet your needs.

- Avoid products by certain companies as they make things difficult for Linux users. See paragraph earlier in this document for details.

- Prefer adapters that are supported with Linux in-kernel drivers. Main Menu item 2 contains a LONG list of adapters and chipsets that are supported with in-kernel drivers.

![image](https://github.com/morrownr/USB-WiFi/assets/69053122/191306b2-f36c-4369-8944-de2bec784ba5)

-----

If there is additional information that you think would be helpful, please post in `Issues`.

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
