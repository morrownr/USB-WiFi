
## USB Ports can be a source of problems with USB WiFi adapters

Maintained by: @morrownr

Updated on: 2026-05-18

I've been helping users of USB WiFi adapters for some years now and I
have noticed that problems are generally first blamed on the driver in
use. I get that. However, our USB WiFi adapters depend on support from
multiple stacks (USB and WiFi). There is also the issue of hardware
compatibility which may require that you change one or more BIOS / UEFI
settings. Sometimes updating the BIOS can help.

Below is an example of using an older USB WiFi adapter on a new system.
The post is from a Debian forum:

https://forums.debian.net/viewtopic.php?t=159402

Note that this user was able to stabilize his USB WiFi adapter after
changing BIOS / UEFI settings and switching to a different port.

#### USB related problems that I have noticed over the years

- USB 3.x ports on some AMD CPU based systems can be problematic but
the problem is not specific to Linux. Here is an article for more details:

https://www.tomshardware.com/news/amd-investigating-usb-connectivity-issues-with-ryzen-pcs

The issues seem confined to Ryzen 3000 and 5000 series CPUs in 500-series
motherboards (i.e., X570 and B550) and consist of random dropouts for
USB-connected devices.

New systems and motherboards with the problematic AMD chipsets are still
being sold as of 2026-05 so beware. Recommend installing updated BIOS,
if available.

- USB ports wear over time and various things can happen if contacts are
not solid and clean.

- It is always a good idea to try a different USB port if you have a
problem.

- There are problematic USB 3 hub chips and problematic USB drivers.

- When in doubt, if you have a USB 2 port, give it a try. USB 2 is
simply more stable than USB 3 and in many use cases, it is fast enough.

- If you are using band 1 (2.4 Ghz) and you have a USB 2 port available,
use it. USB 3 can emit signals that interfer with band 1. I have seen many
users complain of poor band 1 performance when using a USB 3 capable
adapter in a USB 3 port while using band 1. 

 - Powered USB hubs and extension cables can be problematic. Plug the
adapter directly into a port to test if this could be a problem.

- Some USB subsystems do not provide spec power leaving you in a low
power condition. I am looking at you RasPi. This low power issue
is more common with Realtek based USB adapters as Mediatek based
adapters tend to use less power.

- There are USB BIOS / UEFI settings that can cause problems.

### Specific BIOS / UEFI settings for USB WiFi adapters

Note: When troubleshooting, it is a best practice to only change one
setting at a time and then test. If the test does not provide the
desired result, return the setting to its previous state. Also, be
aware that BIOS's may not contain all of the settings shown below.

-----

- Legacy USB Support  [enabled /  disabled]

Recommended setting: disabled

Legacy USB support enabled allows older USB devices to work on newer
operating systems, and vice versa. It's also known as USB Keyboard or
USB Mouse support. It allows older USB devices to be recognized,
initialized, and configured during the boot process. Enabling Legacy
USB Support can cause a variety of problems with modern hardware. Only
enable this setting if you absolutely need it.

-----

- xHCI Hand-off  [enabled /  disabled]

Recommended setting: enabled

xHCI Hand-off enabled means that the BIOS / UEFI lets the operating
system handle the driver support of your onboard USB 3.0 ports.

Note: There is a lot of confusion about this setting. It appears that
some motherboard makers document this setting wrong or support is coded
for it wrong so you may simply have to try both settings to see which
one works best in your setup.

-----

- eHCI Hand-off  [enabled /  disabled]

Recommended setting: disabled

eHCI Hand-off enabled means that the BIOS / UEFI lets the operating
system handle the driver support of your onboard USB 2.0 ports.

-----

- USB transfer time-out  [1, 5, 10, 20]

Recommended setting: 5

To optimize USB transfer time-out in your BIOS / UEFI , set it to the
lowest value that still allows your devices to function properly,
typically around 5-10 seconds; this ensures faster data transfer while
preventing unnecessary delays if a device takes longer to respond.  If
you are using older or slower USB devices, you might need to increase
the timeout to prevent transfer errors. 

-----

- Device reset time-out [10, 20, 30, 40]

Recommended setting: 10

The "best" BIOS / UEFI setting for "Device reset time-out" depends on
your specific hardware and needs, but generally, a timeout of 10-20
seconds is recommended to ensure proper device recognition and prevent
potential boot issues. If you have a lot of USB devices USB devices
connected and have problem, increase the setting. If the timeout is too
short, your computer might not fully recognize a device, leading to boot
errors or issues with peripherals, especially if they take a bit longer
to initialize.

-----

- Device power-up delay  [Auto, Manual]

Recommended setting: Manual

Manual will allow you to control the delay in order to test for the
setting that works best for your system.

-----

- Device power-up delay in seconds  [ ]

Recommended setting: 2 (increase this setting if you see unexplained
problems with a device)

This setting controls the amount of time your computer waits after power
is turned on before it starts powering up connected devices, giving them
a brief window of time to initialize properly. If you have devices that
sometimes don't initialize quickly or if you see unexplained problems
with a device, a slightly longer delay may help prevent errors. 

If you frequently need to access your BIOS settings, a small delay (like
1-2 seconds) might be beneficial to give you enough time to press the
BIOS access key (usually Del or F2) upon power-up. 

-----

- Fast Boot

Recommended setting: disabled

Fast Boot is a setting that skips some hardware checks and initialization processes to make your system boot more quickly. It can disable USB devices during startup, so your keyboard or mouse might not work until the operating system loads completely and some devices may not be initialized at all.

-----

-  PCI Express Configuration 

Recommended setting: This can depend on your hardware and BIOS. The
setting to try is to lower the PCIe version. For exaple: If your
system is set to PCIe 4.0, try PCIe 3.0

-----

- USB Configuration

Recommended setting: If you are having problems and your USB ports are
set to USB Gen 3.2, you might want to try a setting of USB 3 or USB 3.1

-----

I hope this helps. If you have additional information that should be
added, please post in Issues.

@morrownr 
