2023-05-05 (cinco de mayo)

Upgrade hostapd to support WiFi 6

Compile and install hostapd v2.11-devel on Raspberry Pi OS

Purpose: As of this date, the Raspberry Pi OS uses hostapd v2.9
and we need a later version to work with WiFi 6 and WiFi 6e.

Tested on: Raspberry Pi OS 64 bit, the 2023-05-03 version.

Install hostapd (if not already installed):

```
sudo apt install hostapd
```

Activate hostapd (if not already activated):

```
sudo systemctl unmask hostapd
```

```
sudo systemctl enable hostapd
```

Install git:

```
sudo apt install git
```

Clone hostapd:

Note: I use a directory call `src` in my home directory.

```
mkdir -p ~/src
```

```
cd ~/src
```

```
git clone git://w1.fi/srv/git/hostap.git
```

Move to hostapd directory:

```
cd hostap/hostapd
```

Copy default settings to .config:

```
cp defconfig .config
```

Edit .config:

```
nano .config
```

or

```
geany .config
```

or
  use your favorite text editor


Activate the following: (uncomment, if not already uncommented)

```
CONFIG_DRIVER_HOSTAP=y
CONFIG_DRIVER_NL80211=y
CONFIG_LIBNL32=y
CONFIG_RSN_PREAUTH=y
CONFIG_OCV=y
CONFIG_EAP=y
CONFIG_ERP=y
CONFIG_EAP_MD5=y
CONFIG_EAP_TLS=y
CONFIG_EAP_MSCHAPV2=y
CONFIG_EAP_PEAP=y
CONFIG_EAP_GTC=y
CONFIG_EAP_TTLS=y
CONFIG_IPV6=y

CONFIG_IEEE80211R=y
CONFIG_WNM=y
CONFIG_IEEE80211AC=y
CONFIG_IEEE80211AX=y
CONFIG_IEEE80211BE=y
CONFIG_SAE=y
CONFIG_SAE_PK=y
CONFIG_DEBUG_FILE=y
CONFIG_NO_RANDOM_POOL=y
CONFIG_GETRANDOM=y
CONFIG_ELOOP_EPOLL=y
CONFIG_ACS=y
CONFIG_NO_TKIP=y
```

Save the file

Get and install dependencies

```
apt show hostapd
```

Pre-Depends: init-system-helpers (>= 1.54~)
Depends: libc6 (>= 2.34), libnl-3-200 (>= 3.2.7), libnl-genl-3-200 (>= 3.2.7), libnl-route-3-200 (>= 3.2.7), libssl3 (>= 3.0.0~~alpha1), lsb-base

Note: Some of the below packages may already be installed.

```
sudo apt install -y build-essential init-system-helpers libc6 lsb-base
```

```
sudo apt install -y libnl-3-200 libnl-genl-3-200 libnl-route-3-200
```

```
sudo apt install -y libnl-3-dev libnl-genl-3-dev libssl-dev

```

Compile hostapd:

```
make
```

Copy hostapd executable over installed executable:

```
sudo cp hostapd_cli /usr/sbin/hostapd_cli
```

```
sudo systemctl disable hostapd
```

```
sudo reboot
```

```
cd ~/src/hostap/hostapd
```

```
sudo cp hostapd /usr/sbin/hostapd
```

```
sudo systemctl enable hostapd
```

```
sudo reboot
```

Check:

```
hostapd -v
```
