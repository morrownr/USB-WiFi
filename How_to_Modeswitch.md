2021-11-12

How to Modeswitch ( https://www.draisberghof.de/usb_modeswitch )

Purpose: Provide the steps to add modeswitch capability for specified multi-state
USB WiFi adapters.

Note: this document was tested on a Raspberry Pi 4b with the current version
of the Raspberry Pi OS.

Note: To clarify, almost all recent distros, such as Ubuntu 20.04 and later,
Linux Mint 20 and later and the current version Manjaro do not require you
to do anything. usb-modeswitch is installed and set up and works automatically.

Note: As of the date of this document, I am aware of 1 operating system that
requires the changes as outlined below:
```
- Raspberry Pi OS

```
2021-04-20

TEROW_ROW02FD USB WiFi adapter

COMFAST CF-WU782AC USB WiFi adapter

COMFAST CF-WU785AC USB WiFi adapter

"multi-state" adapters will initially show up as a CDROM or flash drive
when plugged into a USB port. If you run Windows, there will an attempt
to install a driver. In any OS besides Windows, the adapter will continue
to be seen as a CDROM or flash drive and no driver will be installed. For
the WiFi adapter to show up, the adapter has to be told to switch state.

Most mainsteam distros of Linux include a utility call 'usb-modeswitch". It
will execute the switch for you if it has the information about your adapter
in its data files. If it is not installed or the data for your adapter is
not in its data files then:

```
Ensure usb-modeswitch is installed

$ sudo apt install usb-modeswitch usb-modeswitch-data


Execute usb-modeswitch in a terminal to see if it works

$ sudo usb_modeswitch -K -W -v 0e8d -p 2870


If successful, set it up to run automatically

edit the following file

$ sudo nano  /lib/udev/rules.d/40-usb_modeswitch.rules

below the following line

SUBSYSTEM!="usb", ACTION!="add",, GOTO="modeswitch_rules_end"

add two lines

# COMFAST CF-WU782AC WiFi Dongle, TEROW ROW02FD WiFi Dongle, COMFAST CF-WU785AC WiFi Dongle
ATTR{idVendor}=="0e8d", ATTR{idProduct}=="2870", RUN+="usb_modeswitch '/%k'"

save the file ( Ctrl + X, Y, Enter )

create the file /usr/share/usb_modeswitch/0e8d:2870

$ sudo nano /usr/share/usb_modeswitch/0e8d:2870

put the following inside:

# COMFAST CF-WU782AC WiFi Dongle, TEROW ROW02FD WiFi Dongle, COMFAST CF-WU785AC WiFi Dongle
TargetVendor=0x0e8d
TargetProductList="7612"
StandardEject=1

save the file ( Ctrl + X, Y, Enter ) and reboot
```

-----
