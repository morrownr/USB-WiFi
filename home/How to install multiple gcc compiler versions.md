How to install multiple GCC compiler versions on Ubuntu based distros

Note: With slight modifications, this guide will likely work for
most distros but you may need to consult your distro documentation
or support forums to confirm.

Maintained by @morrownr

Step 1

Setup the build environment if not already done:

```
sudo apt install build-essential
```

Step 2

Install multiple C compiler versions (only install the ones you want to
add to your system):


```
sudo apt -y install gcc-10 gcc-11 gcc-12
```

Step 3

Use the `update-alternatives` tool to create a list of multiple GCC
compiler alternatives:

```
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-10 10
```

```
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-11 11
```

```
sudo update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-12 12
```

Step 4

Check the available C compilers list on your Ubuntu system:

```
sudo update-alternatives --config gcc
```

```
  Selection    Path            Priority   Status
------------------------------------------------------------
  0            /usr/bin/gcc-11 11         auto mode
  1            /usr/bin/gcc-10 10         manual mode
* 2            /usr/bin/gcc-11 11         manual mode
  3            /usr/bin/gcc-12 12         manual mode
```

Press `Enter` to keep the current choice `[*]` or type selection number.

Step 5

Check your currently selected compiler version:

```
gcc --version
```

Happy compiling!

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----

