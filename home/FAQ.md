Frequently Asked Questions (FAQ)

Question: I am having problems with my Alfa AXML or Alfa AXM or Comfast CF-953AX. The wifi is not working. It seems to crash when coming up. What can I do?

Answer: This is a known problem that started in early 2024 around the time kernel 6.7 was released. There have been unsuccessful attempts to fix this problem. It is a strange problem in that it seems that bluetooth is involved. Most adapters with the mt7921au chipset do not have this problem. The 3 adapters listed in the question are the only 3 known to have this problem so it appears that something specific to these 3 adapters is causing the problem. Right now all that can be offered is a workaround.

This workaround was posted by @ZerBea :

Use one of the following Linux kernels:

$ uname -r

6.6.x

or

$ uname -r

6.12.x

Make sure you're running latest WiFi firmware:

[18615.766176] mt7921u 1-9.3:1.3: WM Firmware Version: ____010000, Build Time: 20241106151045

Disable BT stack:

echo "install btusb /bin/false" >> /etc/modprobe.d/local-dontload.conf

reboot or unload btusb

connect the AXML to an USB2 port or a USB2 hub

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
test monitor mode and packet injection:
```

$ sudo hcxdumptool --rcascan=active --tot=1 -c 1a

...

^C
132 Packet(s) captured by kernel
0 Packet(s) dropped by kernel
57 PROBERESPONSE(s) captured

exit on sigterm

$ sudo dmesg

```
[21146.046337] mt7921u 1-9.3:1.3 wlp22s0f0u9u3i3: entered promiscuous mode
[21153.630136] mt7921u 1-9.3:1.3 wlp22s0f0u9u3i3: left promiscuous mode
```

Monitor mode (device entered promiscuous mode) and packet injection (57 PROBERESPONSE(s) captured) is working!
