Compiling_the_Linux_Mainline_Kernel

Purpose: Facilitate Testing or Patching Drivers

Maintained by @morrownr

2023-01-25

Prerequisites:

A system running Linux (only Ubuntu is tested).

Access to the terminal/command line.

A user account with sudo/root privileges.

12GB of available space on the hard drive.

-----

Note: This checklist has only been tested on Ubuntu 22.10
but will likely work, possibly with minor modifications,
on numerous distros, however you should check with your
distro documentation or user support forums to confirm.

-----

Step 1 Download the Source Code tarball from:

https://www.kernel.org/

linux-6.1.8.tar.xz

Note: The above name will change depending on the
version of the kernel you decide to compile. Adjust
accordingly.

Note: I make a directory called `src` in my home directory
and that is what I download the file to. Anywhere in your
home directory should work.

-----

Step 2 Extract the Source Code:

```
tar xvf linux-6.1.8.tar.xz
```

-----

3. Install Required Packages:

```
sudo apt-get install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc flex libelf-dev bison
```

Note: The above line is specific to Debian based distros such
as Ubuntu.

-----

4. Configure Kernel:

Note: You may want to research this issue  so as to have a
better understanding that what this short guide provides.

Navigate to the `linux-6.1.8` directory using the cd command:

```
cd linux-6.1.8
```

Copy the existing configuration file using the cp command:

```
cp -v /boot/config-$(uname -r) .config
```

To make changes to the configuration file, there are two options:

Option 1: Run make:

```
make menuconfig
```

The command launches several scripts that open the configuration menu.

The configuration menu includes options such as firmware, file system, network, and
memory settings. Use the arrows to make a selection or choose Help to learn more about the
options. When you finish making the changes, select Save, and then exit the menu.

Option 2: Edit `.config` directly with a text editor:

I use `geany`:

```
geany .config
```

If you are intested in turning on the new support
for the below listed new Mediatek driver, make sure
the following line is as below: (kernel 5.18 and later)

Search for `MT76`.

CONFIG_MT7921U=m

Save file and exit.

If you are intested in turning on the new support for the
below listed new Realtek drivers: (kernel 6.2 and later)

Search for `RTW88`.

To turn on support for the rtl8822bu, rtl8812bu, rtl8821cu and rtl8811cu
chipsets, make sure the following lines are as below:

```
CONFIG_RTW88=m
CONFIG_RTW88_CORE=m
CONFIG_RTW88_USB=m
CONFIG_RTW88_8822B=m
CONFIG_RTW88_8821C=m
CONFIG_RTW88_8822BU=m
CONFIG_RTW88_8821CU=m
```

Save file and exit.
---

5. Prevent errors related to certs:

If you are compiling the kernel on Ubuntu or on any distros based on Ubuntu,
you may receive the following error that interrupts the building process:

`No rule to make target debian/canonical-certs.pem`

To prevent the above problem, disable the conflicting security certificates
by executing the two commands below:

```
scripts/config --disable SYSTEM_TRUSTED_KEYS
scripts/config --disable SYSTEM_REVOCATION_KEYS
```

-----

6. Now is the time to patch any files if you are going to test.

-----

7. Compile the kernel:

```
make -j$(nproc)
```

The process of compiling the Linux kernel takes some time to complete.

Note: If the compile stops, make selections or take the default and
hit Enter until compiling starts again (this is related new stuff and
the cert stuff above).

---

8. Install the required modules:

```
sudo make modules_install
```

---

9. Install the kernel:

```
sudo make install
```

---

10. Reboot and check kernel:

```
uname -r
```

-----

For uninstalling the kernel installed from source, run:

```
sudo rm -rf /lib/modules/kernel_version
```
Example: $ sudo rm -rf /lib/modules/6.1.8

```
sudo rm -f /boot/vmlinuz-kernel_version*
```
Example: $ sudo rm -f /boot/vmlinuz-6.1.8*

```
sudo rm -f /boot/initrd.img-kernel_version*
```
Example: $ sudo rm -f /boot/initrd.img-6.1.8*

```
sudo rm -f /boot/config-kernel_version*
```
Example: $ sudo rm -f /boot/config-6.1.8*

```
sudo rm -f /boot/System.map-kernel_version*
```
Example: $ sudo rm -f /boot/System.map-6.1.8*

Finally, after uninstalling the kernel, run:

```
sudo update-grub
```

to update the grub menu.

-----

Happy compiling!

-----

[Return to Main Menu](https://github.com/morrownr/USB-WiFi)

-----
