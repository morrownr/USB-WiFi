2022-01-08

How to Modeswitch ( https://www.draisberghof.de/usb_modeswitch )

Purpose: Provide the steps to add modeswitch capability for specified multi-state
USB WiFi adapters.

"multi-state" adapters will initially show up as a CDROM or flash drive when
plugged into a USB port. If you run Windows, there will an attempt to install
a driver. In any OS besides Windows, the adapter will continue to be seen as a
CDROM or flash drive and no driver will be installed. For the WiFi adapter to
show up, the adapter has to be told to switch state.

Most mainsteam distros of Linux include a utility call `usb-modeswitch`. It
will execute the switch for you if it has the information about your adapter
in its data files. If it is not installed or the data for your adapter is
not in its data files then follow the instructions for the specified adapters
below.

Note: To clarify, almost all recent distros, such as Ubuntu 20.04 and later,
Linux Mint 20 and later and the current version Manjaro do not require you
to do anything. usb-modeswitch is installed and set up and works automatically.
However, not all distros are updated in a timely manner and new adapters are
released so if you find yourself in a situation where plugging in a usb wifi
adapter gives you nothing more than a flashdrive or CDROM on your desktop, you may
have a multi-state adapter on your hands.

There are multiple sections for different adapters below. You need to scroll down
to see if your adapter is listed.

-----

2021-04-20

For: TEROW_ROW02FD USB WiFi adapter

For: COMFAST CF-WU782AC USB WiFi adapter

For: COMFAST CF-WU785AC USB WiFi adapter

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


2021-12-08

For: D-Link DWA-X1850

```
Ensure usb-modeswitch is installed

$ sudo apt install usb-modeswitch usb-modeswitch-data


Execute usb-modeswitch in a terminal to see if it works

$ sudo usb_modeswitch -K -W -v 0bda -p 1a2b


If successful, set it up to run automatically

edit the following file

$ sudo nano  /lib/udev/rules.d/40-usb_modeswitch.rules

below the following line

SUBSYSTEM!="usb", ACTION!="add",, GOTO="modeswitch_rules_end"

add two lines

# D-Link DWA-X1850 WiFi Dongle
ATTR{idVendor}=="0bda", ATTR{idProduct}=="1a2b", RUN+="usb_modeswitch '/%k'"

save the file ( Ctrl + X, Y, Enter )

create the file /usr/share/usb_modeswitch/0bda:1a2b

$ sudo nano /usr/share/usb_modeswitch/0bda:1a2b

put the following inside:

# D-Link DWA-X1850 WiFi Dongle
TargetVendor=0x0bda
TargetProductList="8852"
StandardEject=1

save the file ( Ctrl + X, Y, Enter ) and reboot
```

-----

How to deactivate usb_modeswitch

$ sudo nano /etc/usb_modeswitch.conf

Change

DisableSwitching=0

to

DisableSwitching=1

then reboot

-----
