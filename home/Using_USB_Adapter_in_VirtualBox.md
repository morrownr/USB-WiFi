## Using a USB WiFi Adapter with VirtualBox

Updated: 2025-01-28

Important first step: add your username to the "vboxuser" group.

To add your username to the "vboxuser" group, open a terminal and run
the command "sudo usermod -aG vboxusers your_username"; this will add
your username to the vboxusers group. Keep in mind that `sudo` requires
elevated privileges, meaning you need administrator access.

Much of the information below is borrowed from Josh, an Amazon Customer
that bought a Panda USB WiFi adapter that uses an mt7612u chipset. This
guide should apply broadly to the task of making a USB WiFi adapter work
with VirtualBox. .

This guide is intended for those who are facing issues when using an
adapter with Kali as it is common for beginning Kali users to have
problems if running in a VM. However, the priciples in this guide should
work for most Linux distros.

USB WiFi adapters are not set up automatically in VM's. If you are
running Kali on VirtualBox from a Windows host and experiencing
problems, here are some troubleshooting steps to help you out:

1. Make sure you have VirtualBox and Extension Pack installed before
proceeding.

2. Configure USB settings:

- Plug the adapter into your Windows host system.

- In your Kali VM settings, go to Settings > USB.

- Check "Enable USB Controller."

- Select "USB 3.0 (xHCI) Controller" from the list, if your adapter is
a USB3 capable adapter.

- Under "USB Device Filters," add a new USB filter and choose your
adapter (if your adapter uses a Mediatek chip, it should appear as
something like "MediaTek Inc. Wireless").

- Click OK to apply the changes.

3. Verify the adapter connection:

- Start Kali and run "ip addr" from the terminal.

- You should see the adapter listed as "wlan0." Keep in mind that your
adapter may be assigned a different number than 0 or, if you have turned
on predictable network interface names, then your wireless interface
name may be some thing like "wlx0035bc05649".

4. Further troubleshooting (if necessary):

If the adapter still doesn't appear, follow these additional steps:


- Shutdown Kali and press Windows + E to open File Explorer.

- Press the ALT + D shortcut and go to C:\Windows\System32\drivers.

- Use the Ctrl + F shortcut to search for "vbox.sys."

- If you find the five "vbox.sys" drivers with dates older than the
current year, uninstall VirtualBox. Note that updating the VirtualBox
doesn't always update these drivers. Your configured VMs should remain
intact.

- After uninstalling, delete the old "vbox.sys" drivers from the
mentioned directory.

- Go to Step 1: Install VirtualBox and the Extension Pack and then
continue with the additional steps.

- Launch Kali, and the adapter should now function correctly.

By following these steps, you should be able to resolve any issues with
the adapter's compatibility with Kali on VirtualBox.

If you have ideas to improve this guide, please post in `Issues`.
