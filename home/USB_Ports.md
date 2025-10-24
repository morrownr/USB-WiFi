
## USB Ports can be a source of problems with USB WiFi adapters

I've been helping users of USB WiFi adapters for some years now and I
have noticed that problems are generally first blamed on the driver in
use. I get that. However, our USB WiFi adapters depend on support from
multiple stacks (USB and WiFi). There is also the issue of hardware
compatibility which may require that you change one or more BIOS / UEFI
settings.

Below is an example of using an older USB WiFi adapter on a new system.
The post is from a Debian forum:

https://forums.debian.net/viewtopic.php?t=159402

Note that this user was able to stabilize his USB WiFi adapter after
changing BIOS / UEFI settings and switching to a different port.

#### USB related problems that I have noticed over the last few years

- USB 3.2 gen 2 ports can be problematic, especially with older
adapters such as the one in the forum post above. The mt7612u is a
favorite chip among Linux users but it was initially released over
10 years ago and could not be tested with modern USB 3.2 gen 2 ports
because they did not exist at the time.

- USB ports wear over time and various things can happen if contacts are
not solid.

- It is always a good idea to try a different USB port if you have a
problem.

- There are problematic USB 3 hub chips and problematic USB drivers.

- There are USB BIOS / UEFI settings that can cause problems.

- When in doubt, if you have a USB 2 port, give it a try. USB 2 is
simply more stable than USB 3 and in most cases, it is fast enough for
the use case.

- Powered USB hubs and extension cables can be problematic. Plug the
adapter directly into a port to test if this could be a problem.

- Some USB subsystems do not provide spec power leaving you in a low
power condition. I am looking at you RasPi.

### Specific BIOS / UEFI settings for USB WiFi adapters

Note: When troubleshooting, it is a best practice to only change one
setting at a time and then test. If the test does not provide the
desired result, return the setting to its previous state.

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

I hope this helps. If you have additional information that should be
added, please post in Issues.

@morrownr 
