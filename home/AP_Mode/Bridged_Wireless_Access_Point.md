Warning: 2024-07-26: I am currently working on this guide and I may break it while working it. I recommend that you do not use the guide until this message is removed.

Forword: This guide was recently updated for use with RasPiOS 2024-03-15 and later. Numerous updates had to be made to this guide due to changes in RasPiOS. After completing this update and looking at the changes that would be required to make the guide work on versions of the RasPiOS that were based versions of Debian prior to v12, I decided not to support use on older versions of RasPiOS. I had aleady been recommending that users start this guide with a freshly installed/burned RasPiOS so as to eliminate problems. I hope everyone understands this decision as it will save me time that I can use to make the guide better. This guide should work with Debian 12 as well if you ignore the RasPiOS specific issues. It can work on other distros but you may need to make some changes to the networking for it to work so a knowledge of Linux networking would be required if not using RasPiOS or Debian 12. I hope you enjoy this guide and find it useful.

## How to build a bridged wireless access point

What you will learn:

- Linux networking with `systemd-networkd`

- Establishing one or more APs with `hostapd`

A bridged wireless access point (aka dumb AP) works within an existing ethernet network to add WiFi capability where it does not exist or to extend the network to WiFi capable computers and devices in areas where the WiFi signal is weak or otherwise does not meet expectations. Another common use is add another SSID that is on a different channel so as to reduce the load on an existing SSID. One big advantage of this setup is that it can cost far less than many of the Mesh kits that are available. Another advantage this setup has is that the Raspberry Pi is a general purpose computer so it can be used for additional tasks while performing as a bridged wireless access point.

```
                                                  ((((( tablet    
                                                 ╱
INTERNET >>>>>>> modem/router >>>>>>> RasPi ))))) ((((( laptop/desktop
                (cable)         ╱                ╲
                (fiber)       CAT 5e+             ((((( phone
                (dsl)         Powerline AV2        ╲
                (satellite)   Ethernet Over Coax    ((((( IoT
 ```

Note: In a situation where only another SSID is needed on a different channel or when adding WiFi capability is all that is needed, a very short CAT 5e+ cable may be all that is required as the RasPi can be plugged directly into the modem or router.

Note: In a situation where the RasPi needs to be located a long distance from the modem or router, the connection from the router to the RasPi is best served by a CAT 5e or greater ethernet cable but alternatives exist. One alternative is to use your existing electrical wiring by using Powerline AV2 adapters. These adapters are also called Homeplug AV2 adapters and come in a variety of speeds and prices. I have had success with Powerline AV2 adapters but success depends on the quality and setup of the electrical wiring to be used. Another option is Ethernet Over Coax (MoCa). Anyone considering Powerline AV2 or Ethernet Over Coax (MoCa) should research the products and be prepared to return the products if expectations are not met.

Note: If you are looking to set up a Routed Wireless Access Point, my recommendation is to use OpenWRT. Here is a video that may be helpful:

https://www.youtube.com/watch?v=_pBf2hGqXL8

Information that is helpful with OpenWRT if you intend to use a USB WiFi adapter: OpenWRT has driver packages for several Mediatek/Ralink chipsets to include the mt7921u, mt7612u and mt7610u. These drivers work well but do not support DFS channels for AP mode on the 5 GHz band. Realtek out-of-kernel drivers are a real challenge on OpenWRT and are best avoided.

#### Single Band or Dual Band - Your Choice

This document outlines single band and dual band WiFi setups using a Raspberry Pi 4B with AC600 USB2 and AC1200 USB3 WiFi adapters for 5 GHz band and either an additional external USB WiFi adapter or internal WiFi for 2.4 GHz band. There is a lot of flexibility and capability available with this type of setup.

Important: USB WiFi adapters contain only one internal radio. For a dual band setup, you need two usb wifi adapters or one usb wifi adapter and the RasPi internal wifi active. I do not recommend the internal wifi on RasPi's as the quality of the drivers is suspect.

Note: Tri Band should work but I have not tested it.

#### Tested Setup

Raspberry Pi 4B (4gb)

Raspberry Pi OS (with Desktop) (64 bit) - Strongly recommend that you start with a fresh installation.

Ethernet cable or Powerline AV2 providing internet connectivity

USB WiFi Adapter(s)

Case

Right Angle USB Extender

Power Supply

SD Card

Note: I use the case upside down with little stick-on rubber feet. There are several little things that work better with the case upside down and no negatives that I can find.

Note: Very few Powered USB 3 Hubs will work well with Raspberry Pi hardware. The problems seem to stem from multiple reasons:

Backfeeding of current into the Raspberry Pi USB subsystem.
Bugs in the USB3 hub chipset. (Raspberry Pi leadership has a history of making bad hardware decisions)

Another problem with the Raspberry Pi 4B USB subsystem is that it is designed to supply a maximum of 1200 mA of power. This is WELL BELOW the specification which calls for 2800 mA in a setup such as on the RasPi4B. It is very easy to exceed this 1200 mA limit.

Note: The rtl88XXxu chipset based USB3 WiFi adapters require from 504 mA of power up to well over 800 mA of power depending on the adapter. Beware of the power hungry Realtek USB WiFi adapters.

Let me repeat: The Raspberry Pi 3B, 3B+ and 4B USB subsystems are only able to supply a total of 1200 mA of power total to be divided between all attached devices.

Note: The Alfa AWUS036ACM adapter, a mt7612u based adapter, requests a maximum of 400 mA from the USB subsystem during initialization. Testing with a meter shows actual usage of 360 mA during heavy load and usage of 180 mA during light loads. This is much lower power usage than most AC1200 class adapters which makes this adapter a good choice for a Raspberry Pi based access points. Other mt7612u and mt7610u chipset based adapters also show low power usage. Even the newer mt7921au chipset is a low power chipset so will work well with this setup. Another adapter that is very good for use in this setup is the Alfa AWUS036ACHM which is an AC600 class adapter that has very impressive range.

#### Setup Steps

USB WiFi adapter driver installation, if required, should be performed prior to continuing.

Note: For USB3 adapters based on the Realtek rtl8812au, rtl8812bu and rtl8814au chipsets, the following module parameters may be needed for best performance when the adapter is set to support 5 GHz band: (if using a rtl8812bu based adapter with a Raspberry Pi 4B or 400, you may need to limit USB mode to USB2 due to a bug, probably in the Raspberry Pi OS, that causes dropped connections-- rtw_switch_usb_mode=2)

rtw_vht_enable=2 rtw_switch_usb_mode=1

Note: For USB2 adapters based on the Realtek rtl8811au and rtl8821cu chipset, the following module parameters may be needed for best performance when the adapter is set to support 5 GHz band:

rtw_vht_enable=2

Note: For USB3 adapters based on the Realtek rtl8812au, rtl8812bu and rtl8814au chipsets, the following module parameters may be needed for best performance when the adapter is set to support 2.4 GHz band:

rtw_vht_enable=1 rtw_switch_usb_mode=2

Note: For USB2 adapters based on the Realtek rtl8811au and rtl8821cu chipset, the following module parameters may be needed for best performance when the adapter is set to support 2.4 GHz band:

rtw_vht_enable=1

Note: For USB3 adapters based on Mediatek mt7612u or mt7921au chipsets, the following module parameter may be needed for best performance:

disable_usb_sg=1

Note: Here is a quick way to set the disable_usb_sg parameter:

sudo -i
echo "options mt76_usb disable_usb_sg=1" > /etc/modprobe.d/mt76_usb.conf
exit

Note: More information is available at the following site:

https://github.com/morrownr/7612u

-----

#### Update, upgrade and clean up the operating system.

```
sudo apt update && sudo apt upgrade && sudo apt autoremove
```

Note: Upgrading the operating system is not mandatory for this installation but it is a good idea.

-----

#### Reduce overall power consumption.

Note: All items in this step are optional and some items are specific to the Raspberry Pi 4B. If installing to other Raspberry Pi hardware, you will need to use the appropriate settings for that hardware.

```
sudo nano /boot/firmware/config.txt
```

Note: The config.txt file may be located as shown below in older versions of the RasPiOS.

```
sudo nano /boot/config.txt
```

Change:

```
# turn off onboard audio if audio is not required
#dtparam=audio=on
Add:

# disable Power LED (activate if desired)
dtparam=pwr_led_trigger=default-on
dtparam=pwr_led_activelow=off

# turn off Mainboard LEDs
dtoverlay=act-led

# disable Activity LED
dtparam=act_led_trigger=none
dtparam=act_led_activelow=off

# turn off Ethernet port LEDs
dtparam=eth_led0=4
dtparam=eth_led1=4

# turn off Bluetooth
dtoverlay=disable-bt

# turn off onboard WiFi
dtoverlay=disable-wifi
```

-----

Overclock the CPU a modest amount.

Note: This step is optional and is specific to the Raspberry Pi 4B.

```
sudo nano /boot/firmware/config.txt
```

Note: The config.txt file may be located as shown below in older versions of the RasPiOS.

```
sudo nano /boot/config.txt
```

Add:

```
# overclock CPU
# (may not be required with later versions of the RasPi4B)
over_voltage=2
arm_freq=1800
```

-----

#### Predictable network interface names

The Raspberry Pi OS currently does not use predictable network interface names. WiFi interface names will appear as wlan0, wlan1, etc.

Note: While this step is optional, problems can arise without it on dual band setups. Some Linux distros have this capability enabled by default but not the Raspberry Pi OS. My recommendation is that you activate Predictable Network Interface Names.

To enable predictable network interface names on the Raspberry Pi OS:

```
sudo raspi-config
```

Select: Advanced options > A4 Network Interface Names > Yes

Reboot system.

```
sudo reboot
```

-----

#### How to handle Network Manager or Netplan

If your Linux distro uses Network Manager or Netplan (Ubuntu), they need to be configured to not manage the interface that you plan to use as an AP. If you are using Ubuntu, there is a section at the end of this guide that shows you how to remove Netplan as well as Network Manager. 

How to keep Network Manager from causing problems.

Tell Network Manager to ignore specific devices.

```
sudo nano /etc/NetworkManager/NetworkManager.conf
```

add

```
[keyfile]
unmanaged-devices=interface-name:wlan0
```

Note: Ensure that you change `wlan0` to the name of your
wireless interface.

Save the file.

#### Determine name and state of the network interfaces.

```
ip a
```

You may need to additionally run the following command to help to determine which adapter, in a dual band setup, has which interface name.

```
iw dev
```

Note: If the interface names are not eth0, wlan0 and wlan1, then the interface names used in your system will have to replace eth0, wlan0 and wlan1 for the remainder of this document.

-----

#### Install hostapd package.

```
sudo apt install hostapd
```

-----

#### Enable systemd-networkd service. Website - [SystemdNetworkd](https://wiki.debian.org/SystemdNetworkd)

Note: Right tools for the job. Network Manager will be disabled and systemd-networkd, systemd-resolved and hostapd will be enabled and configured in order to allow maximum performance.
```
sudo systemctl enable systemd-networkd
```

```
sudo apt install systemd-resolved
```

```
sudo systemctl enable systemd-resolved
```

```
sudo systemctl start systemd-resolved
```

Once started, systemd-resolved will create its own resolv.conf somewhere under /run/systemd directory. However, it is a common practice to store DNS resolver information in /etc/resolv.conf, and many applications still rely on /etc/resolv.conf. Thus for compatibility reason, create a symlink to /etc/resolv.conf as follows.

```
sudo rm /etc/resolv.conf
```

```
sudo ln -s /run/systemd/resolve/resolv.conf /etc/resolv.conf
```

-----

#### Create bridge interface br0.

```
sudo nano /etc/systemd/network/10-create-bridge-br0.netdev
```

File contents

```
[NetDev]
Name=br0
Kind=bridge
```

Bind ethernet interface.

```
sudo nano /etc/systemd/network/20-bind-ethernet-with-bridge-br0.network
```

File contents

```
[Match]
Name=eth0

[Network]
Bridge=br0
```

#### Configure bridge interface.

```
sudo nano /etc/systemd/network/30-config-bridge-br0.network
```

Note: The contents of the Network block below should reflect the needs of your network.

File contents

```
[Match]
Name=br0

[Network]
DHCP=yes
#Address=192.168.1.24/24
#Gateway=192.168.1.1
#DNS=8.8.8.8
```

-----

#### Enable the wireless access point service and set it to start when your Raspberry Pi boots.

```
sudo systemctl unmask hostapd
```

```
sudo systemctl enable hostapd
```

-----

#### Create hostapd configuration file(s)

Note: The below steps include creating two hostapd configurations files but only one is needed if using a single band setup.

Note: Shown below are hostapd.conf examples for WiFi 4 and WiFi 5 adapters. An example for WiFi 6 is shown at [`./hostapd-WiFi6.conf`](./hostapd-WiFi6.conf).

Create hostapd configuration file for 5 GHz band.

```
sudo nano /etc/hostapd/hostapd-WiFi5.conf
```

File contents

```
# /etc/hostapd/hostapd-WiFi5.conf
# Documentation: https://w1.fi/cgit/hostap/plain/hostapd/hostapd.conf
# 2022-09-25

# SSID
ssid=myPI-WiFi5
# PASSPHRASE
wpa_passphrase=myPW1234
# Band: a = 5GHz & 6GHz (a/n/ac/ax), g = 2Ghz (b/g/n)
hw_mode=a
# Channel
channel=36
# Channel width (0 = 40 MHz. 1 = 80 Mhz)
vht_oper_chwidth=1
# VHT center channel (chan + 6)
vht_oper_centr_freq_seg0_idx=42
# Country code
country_code=US
# Advertises the country_code and the set of allowed channels and transmit power levels
ieee80211d=1
# Enables support for 5GHz DFS channels (requires ieee80211d=1)
ieee80211h=1

# Bridge interface
bridge=br0
# WiFi interface
interface=wlan0

# Set hostapd driver (nl80211 is used with all Linux mac80211 (in-kernel) and modern Realtek drivers)
driver=nl80211

#ctrl_interface=/var/run/hostapd
#ctrl_interface_group=0

# Various settings
#beacon_int=100
#dtim_period=2
#max_num_sta=32
macaddr_acl=0
#rts_threshold=2347
#fragm_threshold=2346
#send_probe_response=1

# Security
# auth_algs=3 is required for WPA3-SAE and WPA3-SAE Transition mode
auth_algs=1
ignore_broadcast_ssid=0
# wpa=2 is required for WPA2 and WPA3 (read the docs)
wpa=2
rsn_pairwise=CCMP
# only one wpa_key_mgmt= line should be active.
# wpa_key_mgmt=WPA-PSK is required for WPA2-AES
wpa_key_mgmt=WPA-PSK
# wpa_key_mgmt=SAE WPA-PSK is required for WPA3-SAE Transition mode
#wpa_key_mgmt=SAE WPA-PSK
# wpa_key_mgmt=SAE is required for WPA3-SAE
#wpa_key_mgmt=SAE
#wpa_group_rekey=1800
# ieee80211w=1 is required for WPA3-SAE Transition mode
# ieee80211w=2 is required for WPA3-SAE
#ieee80211w=1
# if parameter is not set, 19 is the default value.
#sae_groups=19 20 21 25 26
# sae_require_mfp=1 is required for WPA3-SAE Transition mode
#sae_require_mfp=1
# if parameter is not 9 set, 5 is the default value.
#sae_anti_clogging_threshold=10

# Note: Capabilities can vary even between adapters with the same chipset.
#
# Note: Only one ht_capab= line and one vht_capab= should be active. The
# content of these lines is determined by the capabilities of your adapter.
#
# IEEE 802.11n
ieee80211n=1
wmm_enabled=1
#
# generic setting
ht_capab=[HT40+][HT40-][SHORT-GI-20][SHORT-GI-40]
#
# mediatek chipsets
# mt7612u - mt7610u
#ht_capab=[HT40+][HT40-][GF][SHORT-GI-20][SHORT-GI-40]
# mt7921au
##ht_capab=[LDPC][HT40+][HT40-][GF][SHORT-GI-20][SHORT-GI-40][TX-STBC][RX-STBC1][MAX-AMSDU-7935]
#
# realtek chipsets
# rtl8812au - rtl8811au - rtl8811cu
#ht_capab=[HT40+][HT40-][SHORT-GI-20][SHORT-GI-40][MAX-AMSDU-7935]
# rtl8812bu
#ht_capab=[LDPC][HT40+][HT40-][SHORT-GI-20][SHORT-GI-40][MAX-AMSDU-7935]
# rtl8814au
#ht_capab=[LDPC][HT40+][HT40-][SHORT-GI-20][SHORT-GI-40][MAX-AMSDU-7935][DSSS_CCK-40]
#

# IEEE 802.11ac
ieee80211ac=1
#
# generic setting
vht_capab=[SHORT-GI-80]
#
# mt7610u
#vht_capab=[SHORT-GI-80][MAX-A-MPDU-LEN-EXP3][RX-ANTENNA-PATTERN][TX-ANTENNA-PATTERN]
# mt7612u
#vht_capab=[RXLDPC][SHORT-GI-80][TX-STBC-2BY1][RX-STBC-1][MAX-A-MPDU-LEN-EXP3][RX-ANTENNA-PATTERN][TX-ANTENNA-PATTERN]
# mt7921au (VHT Cap. 339071b2)
#vht_capab=[MAX-MPDU-11454][RXLDPC][SHORT-GI-80][TX-STBC-2BY1][RX-STBC-1][SU-BEAMFORMEE][BF-ANTENNA-4][MAX-A-MPDU-LEN-EXP7][RX-ANTENNA-PATTERN][TX-ANTENNA-PATTERN]
#
# rtl8812au - rtl8812bu
#vht_capab=[MAX-MPDU-11454][SHORT-GI-80][TX-STBC-2BY1][RX-STBC-1][HTC-VHT][MAX-A-MPDU-LEN-EXP7]
# rtl8814au
#vht_capab=[MAX-MPDU-11454][RXLDPC][SHORT-GI-80][TX-STBC-2BY1][RX-STBC-1][HTC-VHT][MAX-A-MPDU-LEN-EXP7]
# rtl8811au
#vht_capab=[MAX-MPDU-11454][SHORT-GI-80][RX-STBC-1][HTC-VHT][MAX-A-MPDU-LEN-EXP7]
# rtl8811cu
#vht_capab=[MAX-MPDU-11454][SHORT-GI-80][HTC-VHT][MAX-A-MPDU-LEN-EXP7]
#
# Note: [TX-STBC-2BY1] may cause problems with some Realtek drivers

# end of hostapd-WiFi5.conf
```

Create the WiFi4 hostapd configuration file.

```
sudo nano /etc/hostapd/hostapd-WiFi4.conf
```

File contents

```
# /etc/hostapd/hostapd-WiFi4.conf
# Documentation: https://w1.fi/cgit/hostap/plain/hostapd/hostapd.conf
# 2022-08-08

# SSID
ssid=myPI-WiFi4
# PASSPHRASE
wpa_passphrase=myPW1234
# Band: a = 5Ghz (a/n/ac), g = 2Ghz (b/g/n)
hw_mode=g
# Channel
channel=6
# Country code
country_code=US

# Bridge interface
bridge=br0
# WiFi interface
interface=wlan1

# nl80211 is used with all Linux mac80211 (in-kernel) and modern Realtek drivers
driver=nl80211
#ctrl_interface=/var/run/hostapd
#ctrl_interface_group=0

beacon_int=100
dtim_period=2
max_num_sta=32
rts_threshold=2347
fragm_threshold=2346
#send_probe_response=1

# security
# auth_algs=3 is required for WPA3-SAE and WPA3-SAE Transition mode
auth_algs=1
macaddr_acl=0
ignore_broadcast_ssid=0
wpa=2
wpa_pairwise=CCMP
# WPA2-AES
wpa_key_mgmt=WPA-PSK
# WPA3-SAE
#wpa_key_mgmt=SAE
#wpa_group_rekey=1800
rsn_pairwise=CCMP
# ieee80211w=2 is required for WPA3-SAE
#ieee80211w=2
# If parameter is not set, 19 is the default value.
#sae_groups=19 20 21 25 26
#sae_require_mfp=1
# If parameter is not 9 set, 5 is the default value.
#sae_anti_clogging_threshold=10

# IEEE 802.11n
ieee80211n=1
wmm_enabled=1
#
# Note: Only one ht_capab= line should be active. The content of these lines is
# determined by the capabilities of your adapter.
#
# generic 20 MHz setting
ht_capab=[SHORT-GI-20]
#
# generic 40 MHz setting
#ht_capab=[HT40+][HT40-][SHORT-GI-20][SHORT-GI-40]
#
# RasPi4B internal wifi
#ht_capab=[HT40+][HT40-][SHORT-GI-20][SHORT-GI-40][DSSS_CCK-40]
#
# rt5370 - rt3070
#ht_capab=[HT40+][HT40-][GF][SHORT-GI-20][SHORT-GI-40][RX-STBC1]
#
# ar9271
#ht_capab=[HT40+][HT40-][SHORT-GI-20][SHORT-GI-40][RX-STBC1][DSSS_CCK-40]
#
# mt7612u - mt7610u
#ht_capab=[HT40+][HT40-][GF][SHORT-GI-20][SHORT-GI-40]
#
# rtl8812au - rtl8811au -  rtl8812bu - rtl8811cu
#ht_capab=[HT40+][HT40-][SHORT-GI-20][SHORT-GI-40][MAX-AMSDU-7935]
# rtl8814au
#ht_capab=[LDPC][HT40+][HT40-][SHORT-GI-20][SHORT-GI-40][MAX-AMSDU-7935][DSSS_CCK-40]

# End of hostapd-WiFi4.conf
```

-----

#### Modify hostapd.service file.

```
sudo cp /usr/lib/systemd/system/hostapd.service /etc/systemd/system/hostapd.service
```

```
sudo nano /etc/systemd/system/hostapd.service
```

Only change the lines shown.

If ConditionFileNotEmpty=/etc/hostapd/hostapd.conf line is present, comment it as shown below

```
#ConditionFileNotEmpty=/etc/hostapd/hostapd.conf
```

Add the Environment=DAEMON_OPTS= line as shown below (remember to change <your_home>)

```
Environment=DAEMON_OPTS="-d -K -f /home/<your_home>/hostapd.log"
```

Change RestartSec=0 line as shown below

```
RestartSec=3
```

Comment the EnvironmentFile= line as shown below

```
#EnvironmentFile=-/etc/default/hostapd
```

Add the below line before the the ExecStart= line

```
ExecStartPre=/bin/sleep 6
```

Change the ExecStart= line as shown below

```
ExecStart=/usr/sbin/hostapd -B -P /run/hostapd.pid -B $DAEMON_OPTS $DAEMON_CONF
```

Select one of the following options.

Dual band option:

Change the Environment=DAEMON_CONF= line as shown below

```
Environment=DAEMON_CONF="/etc/hostapd/hostapd-WiFi5.conf /etc/hostapd/hostapd-WiFi4.conf"
```

Single band option for WiFi5:

Change the Environment=DAEMON_CONF= line as shown below

```
Environment=DAEMON_CONF="/etc/hostapd/hostapd-WiFi5.conf"
```

Single band option for WiFi4:

Change the Environment=DAEMON_CONF= line as shown below

```
Environment=DAEMON_CONF="/etc/hostapd/hostapd-WiFi4.conf"
```

Save the file.

-----

#### Ensure WiFi radio not blocked.

```
sudo rfkill unblock wlan
```

-----

Reboot system.

```
sudo reboot
```

-----

## End of installation

-----

The following sections contain good to know information.

Restart systemd-networkd service.

```
sudo systemctl restart systemd-networkd
```

-----

Check status of the hostapd and systemd-networkd services.

```
systemctl status hostapd
```

```
systemctl status systemd-networkd
```

-----

Disable hostapd.service

```
sudo systemctl disable hostapd
```

-----

Enable hostapd.service

```
sudo systemctl enable hostapd
```

-----

Install and autostart iperf3.

```
sudo apt install iperf3
```

```
sudo nano /etc/systemd/system/iperf3.service
```

File contents

```
[Unit]
Description=iPerf3 Service
After=syslog.target network.target auditd.service

[Service]
Type=simple
ExecStart=/usr/bin/iperf3 -s

[Install]
WantedBy=multi-user.target
sudo systemctl enable iperf3
sudo reboot
```

Check iperf3 status.

```
sudo systemctl status iperf3
```

-----

How to keep Network Manager from causing problems.

Option 1:

Tell Network Manager to ignore specific devices.

```
sudo nano /etc/NetworkManager/NetworkManager.conf
```

add

```
[keyfile]
unmanaged-devices=interface-name:wlan0
```

Note: Remember to replace wlan0 with your interface name.

Option 2:

Uninstall NetworkManager.

Note: For systems not running the Gnome desktop, purging Network Manager is the easiest solution.

```
sudo apt purge network-manager
```

Note: For systems running the Gnome desktop, use the following.

```
sudo systemctl stop NetworkManager.service
```

```
sudo systemctl disable NetworkManager.service
```

```
sudo systemctl stop NetworkManager-wait-online.service
```

```
sudo systemctl disable NetworkManager-wait-online.service
```

```
sudo systemctl stop NetworkManager-dispatcher.service
```

```
sudo systemctl disable NetworkManager-dispatcher.service
```

```
sudo systemctl stop network-manager.service
```

```
sudo systemctl disable network-manager.service
```

```
sudo reboot
```

Option 3:

Disable Network Manager service.

```
sudo systemctl disable NetworkManager
```

-----

Disable MAC address randomization.

Note: Disabling MAC address randomization may be needed to get a stable link.

```
sudo nano /etc/NetworkManager/NetworkManager.conf
```

add

```
[device]
wifi.scan-rand-mac-address=no
```

save the file with ctrl + o, enter and then exit nano with ctrl + x.

```
sudo reboot
```

-----

Disable Netplan.

Note: Netplan is the default network manager on Ubuntu server.

Disable and mask networkd-dispatcher.

Note: we are activating /etc/network/interfaces

```
sudo apt-get install ifupdown
```

```
sudo systemctl stop networkd-dispatcher
```

```
sudo systemctl disable networkd-dispatcher
```

```
sudo systemctl mask networkd-dispatcher
```

-----

Purge netplan.

```
sudo apt-get purge nplan netplan.io
```

```
sudo reboot
```

-----

How do I disable Wayland so that I can use VNC?

Note: Raspberry Pi OS 2023-10-10 uses Wayland by default but the included VNC server does not support Wayland so it is necessary to return to X11 if you want VNC to work.

Open Terminal on the Pi, or connect to it using SSH

Run the command: sudo raspi-config

Select Advanced Options, then select Wayland

Select X11 and confirm

Reboot the Pi when prompted
