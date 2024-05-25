## Compiling the Linux Kernel

Purpose: Facilitate Activating, Testing or Patching in-kernel Drivers

Maintained by @morrownr

2023-02-20

### Prerequisites

1. A system running Linux (only Ubuntu is tested).
1. Access to the terminal/command line.
1. A user account with sudo/root privileges.
1. 12GB of available space on the hard drive.

> [!NOTE]
> This checklist has only been tested on Ubuntu 22.10 but will likely work, possibly with minor modifications, on numerous distros.
> However you should check with your distro documentation or user support forums to confirm.

### Step 1: Download Source Code

1. Download the Source Code tarball from <https://www.kernel.org/>.
   For example, when downloading version 6.2 of the kernel one would download `linux-6.2.tar.xz`.
1. `cd` into the directory where the source code was downloaded.
   For example, if downloaded into `~/Downloads` then run `cd ~/Downloads`.
1. Extract the Source Code:

   ``` shell
   tar xvf linux-6.2.tar.xz
   ```

### Step 2: Install Dependencies

Install build dependencies.
For Debian-based distros such as Ubuntu, this can be done by running:

``` shell
sudo apt install git fakeroot build-essential ncurses-dev xz-utils libssl-dev bc flex libelf-dev bison
```

### Step 3: Configure the Kernel

> [!NOTE]
> You may want to research this topic so as to have a better understanding of what this short guide provides.

1. Navigate to directory where the source code was extracted, e.g. `cd linux-6.2`.
1. Copy the existing configuration file:

   ``` shell
   cp -v /boot/config-$(uname -r) .config
   ```

1. Make changes to the configuration file.

   1. Run make:

      ``` shell
      make menuconfig
      ```

      The command launches several scripts that open the configuration menu.

      The configuration menu includes options such as firmware, file system, network, and memory settings.
      Use the arrows to make a selection or choose Help to learn more about the options.
      When you finish making the changes, select Save, and then exit the menu.

    1. For example:
       To turn on support for the rtl8822bu, rtl8812bu, rtl8821cu and rtl8811cu chipsets, select 8822BU and 8821CU per the example below:

       ``` text
       Device Drivers  --->

       -*- Network device support  --->

       [*]   Wireless LAN  --->

       <M>     Realtek 802.11ac wireless chips support  --->

       --- Realtek 802.11ac wireless chips support
                <M>   Realtek 8822BE PCI wireless network adapter
                < >   Realtek 8822BU USB wireless network adapter (NEW)
                <M>   Realtek 8822CE PCI wireless network adapter
                < >   Realtek 8822CU USB wireless network adapter (NEW)
                <M>   Realtek 8723DE PCI wireless network adapter
                < >   Realtek 8723DU USB wireless network adapter (NEW)
                <M>   Realtek 8821CE PCI wireless network adapter
                < >   Realtek 8821CU USB wireless network adapter (NEW)
       ```

       In the section above, there are 4 new drivers that will not compile unless you select them.
       Once finished, select Save, and then exit the menu.

1. Prevent errors related to certs.

   If you are compiling the kernel on Ubuntu or on any distros based on Ubuntu, you may receive the following error that interrupts the building process:

   > No rule to make target debian/canonical-certs.pem

   To prevent the above problem, disable the conflicting security certificates by executing the two commands below:
   
   1. `scripts/config --disable SYSTEM_TRUSTED_KEYS`
   1. `scripts/config --disable SYSTEM_REVOCATION_KEYS`

1. Now is the time to patch any files if you are going to test.

1. Compile the kernel:

   ``` shell
   make -j$(nproc)
   ```

   The process of compiling the Linux kernel takes some time to complete.

    > [!TIP]
    > If the compile stops, make selections or take the default and hit Enter until compiling starts again (this is related new stuff and the cert stuff above).

1. Install the required modules:

   ``` shell
   sudo make modules_install
   ```

1. Install the kernel:

   ``` shell
   sudo make install
   ```

1. Reboot and check kernel:

   ``` shell
   uname -r
   ```
   
### Step 4 (Optional): Uninstalling a Kernel Installed from Source

To uninstall a kernel that had been installed from source, run the following commands.
In each command, replace `${kernel_version}` with the version you want to remove, e.g. `6.2`.

1. `sudo rm -rf /lib/modules/${kernel_version}`
1. `sudo rm -f /boot/vmlinuz-${kernel_version}*`
1. `sudo rm -f /boot/initrd.img-${kernel_version}*`
1. `sudo rm -f /boot/config-${kernel_version}*`
1. `sudo rm -f /boot/System.map-${kernel_version}*`
1. Update the GRUB menu to remove the outdated entry: `sudo update-grub`

-----

Happy compiling!
