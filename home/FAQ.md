USB-WiFi Frequently Asked Questions (FAQ)

Note: If you find that any of the answers below no longer work or are in need of an update, please let me know by posting a message in `issues`. Keeping the information on this site current is a challenge and can only work with your help. Thanks.

-----

No. 1

Question: I am having problems with my Alfa AXML or Alfa AXM or Comfast CF-953AX. The wifi is not working. It seems to crash when coming up. What can I do?

Answer: This is a known problem that started in early 2024 around the time kernel 6.7 was released. There have been unsuccessful attempts to fix this problem. It is a strange problem in that it seems that bluetooth is involved. Most adapters with the mt7921au chipset do not have this problem. The 3 adapters listed in the question are the only 3 known to have this problem so it appears that something specific to these 3 adapters is causing the problem. Right now all that can be offered is a workaround.

This workaround was posted by @ZerBea :

-----

Use one of the following Linux kernels if possible:

6.6.x (or earlier)

or

6.12.x (or later)

To check your kernel: $ uname -r

You may ask why? A tremendous amount of work over the last year or so had to do with adding WiFi 7 support to the Linux kernel. As time passes, the new drivers are becoming more and more complex. This has contributed greatly to overall problems. We have seen an abnormal amount of problems from kernel 6.7 through 6.11. I think kernel 6.8 was the worst of the bunch. You will be doing yourself a favor by avoiding kernels 6.7 to 6.11.

-----

Make sure you're running the latest WiFi firmware:

[18615.766176] mt7921u 1-9.3:1.3: WM Firmware Version: ____010000, Build Time: 20241106151045

Instructions for updating the firmware can be found at the following location:

https://github.com/morrownr/USB-WiFi/blob/main/home/How_to_Install_Firmware_for_Mediatek_based_USB_WiFi_adapters.md

-----

Disable BT stack:

Create the file: $ sudo nano /etc/modprobe.d/local-dontload.conf

Note: You can use your own favorite text editor in place of `nano` if you wish.

Add the following line to the file: install btusb /bin/false

Save the file - Ctrl + O, Enter, Ctrl + X

Reboot:

$ sudo reboot

-----

If WiFi is not working in a USB3 port, try a USB2 port or a USB2 hub

-----

The above solution, that shuts down bluetooth support, may not work
well for people that have other bluetooth support in their system and
they want to use it. In that case, simply delete BT firmware file for
your adapter.

-----

Now dmesg should print this:

```
[20844.686881] usb 1-9.3: new high-speed USB device number 12 using xhci_hcd
[20844.818337] usb 1-9.3: New USB device found, idVendor=0e8d, idProduct=7961, bcdDevice= 1.00
[20844.818343] usb 1-9.3: New USB device strings: Mfr=6, Product=7, SerialNumber=8
[20844.818346] usb 1-9.3: Product: Wireless_Device
[20844.818347] usb 1-9.3: Manufacturer: MediaTek Inc.
[20844.818349] usb 1-9.3: SerialNumber: 000000000
[20845.018645] usb 1-9.3: reset high-speed USB device number 12 using xhci_hcd
[20845.159101] mt7921u 1-9.3:1.3: HW/SW Version: 0x8a108a10, Build Time: 20241106151007a
[20845.420854] mt7921u 1-9.3:1.3: WM Firmware Version: ____010000, Build Time: 20241106151045
[20847.020857] mt7921u 1-9.3:1.3 wlp22s0f0u9u3i3: renamed from wlan0

```

test monitor mode and packet injection:

$ sudo hcxdumptool --rcascan=active --tot=1 -c 1a

...

^C

132 Packet(s) captured by kernel

0 Packet(s) dropped by kernel

57 PROBERESPONSE(s) captured

Monitor mode (device entered promiscuous mode) and packet injection (57 PROBERESPONSE(s) captured) is working!

exit on sigterm

$ sudo dmesg

```
[21146.046337] mt7921u 1-9.3:1.3 wlp22s0f0u9u3i3: entered promiscuous mode
[21153.630136] mt7921u 1-9.3:1.3 wlp22s0f0u9u3i3: left promiscuous mode

```

-----

No. 2

Question: My 6 GHz band shows as disabled when I run `iw list`. I want to be
able to use the 6 GHz band. How can I fix this?

Answer:  This may happen with MEDIATEK cards and adapters on Linux 6.7.x or
newer. There has been a lot of work on the WiFi support in Linux over the
last year. We have seen an uptick in WiFi problems as a result. As of kernel
6.12, things seem to be getting better but there is work to be done.

A new feature called "CLC (Country Location Control)" must be disabled in the
`mt7921_common` module in order to use the 6 GHz band (for now). Make a file
called `/etc/modprobe.d/mt7921.conf` containing `options mt7921_common disable_clc=1`.

Example:

Open a Terminal

Create the file: $ sudo nano /etc/modprobe.d/mt7921.conf

Note: You can use your own favorite text editor in place of `nano` if you wish.

Add the following line to the file: options mt7921_common disable_clc=1

Save the file - Ctrl + O, Ctrl + X

Reboot

Source: https://community.frame.work/t/responded-amd-rz616-wifi-card-doesnt-work-with-6ghz-on-kernel-6-7/43226

Information: https://bugzilla.kernel.org/show_bug.cgi?id=218731

-----

No. 3

Question: It appears that the Wireless Regulation information is not correct. How can I fix this?

Answer: When you run `$ iw reg get` you should be able to see the country setting of your system and the bands that you can use. Examples of what you may see if there is a problem: 5 GHz channels do not allow access point operation (iw list showing no-ir on all channels) and 6 GHz channels would be completely disabled.

If you see the wrong country or some bands that you would expect to work are not available, the following may help:

Open a Terminal interface - Ctrl + Alt + T

Create the file: $ sudo nano /etc/modprobe.d/cfg80211.conf

Note: You can use your own favorite text editor in place of `nano` if you wish.

Add the following line to the file:  options cfg80211 ieee80211_regdom=AU

Note: If your country code is not AU, you will need to replace AU with your country code

Save the file - Ctrl + O, Ctrl + X

Reboot

-----

No. 4

Question: Why do I see high levels of jitter with my mt7922 or mt7921 based wifi card (PCIe or M.2)?

Information: Variance in ping times is called "jitter" in networking terminology; it refers to the inconsistency in the arrival time of data packets, essentially measuring how much your ping fluctuates over time. 

Information: Both chips use the mt7921e driver.

Answer: You can try disabling power management for that card as follows:

Open a Terminal interface - Ctrl + Alt + T

Create the file: $ sudo nano /etc/modprobe.d/mt7921.conf

Note: You can use your own favorite text editor in place of `nano` if you wish.

Add the following line to the file:  options mt7921e disable_aspm=Y

Save the file - Ctrl + O, Ctrl + X

Reboot

-----

No. 5

Question: Why do I see high levels of jitter with my mt7921au based USB WiFi adapter?

Information: Variance in ping times is called "jitter" in networking terminology; it refers to the inconsistency in the arrival time of data packets, essentially measuring how much your ping fluctuates over time. 

Information: This chip uses the mt7921u driver.

Note: The solutions listed here should work for any USB WiFi adapter.

-----

Answer 1: First test to see if power_save is causing the issue:

Open a Terminal interface: Ctrl + Alt + T

Run the following command (remember to change wlan0 to the name of your wireless interface):

```
iw wlan0 set power_save off
```

Do not reboot as that will return power_save to on.

Test your system to see if there is improvement. If there is improvement, you may want to check the additional answers below for a persistent solution.

-----

Answer 2: If your system uses `Network Manager`, you can disable power_save for the adapter as follows:

Open a Terminal interface: Ctrl + Alt + T

Create the following file:

```
sudo nano /etc/NetworkManager/conf.d/wifi-power_save.conf
```

Note: You can use your own favorite text editor in place of `nano` if you wish.

Add the following lines to the file:

```
# Values are 0 (use default), 1 (ignore/don't touch), 2 (disable) or 3 (enable).
wifi.powersave = 2
```

Save the file - Ctrl + O, Enter, Ctrl + X

Reboot

```
sudo reboot
```

Answer 3:

If your system uses `systemd`, you can disable power_save for the adapter as follows:

Open a Terminal interface: Ctrl + Alt + T

Create the following file:

Note: You can use your own favorite text editor in place of `nano` if you wish.

```
sudo nano /lib/systemd/system/wifi-power_save.service
```

Add the following lines to the file (remember to change `wlan0` to the name of your wireless interface):

```
[Unit]
Description=Disable power_save for specific USB WiFi adapter
After=network.target

[Service]
Type=oneshot
ExecStart=/usr/bin/iw wlan0 set power_save off

[Install]
WantedBy=default.target
```

Run the following command to enable the new service:

```
sudo systemctl enable wifi-power_save.service
```

Run the following command to verify that the service is functioning properly after rebooting:

Note: remember to change `wlan0` to the name of your wireless interface.

```
iw wlan0 get power_save
```

Run the following command to disable the service:

```
sudo systemctl disable wifi-power_save.service
```

-----
