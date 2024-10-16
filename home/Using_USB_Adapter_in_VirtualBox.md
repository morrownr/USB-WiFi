Using a USB WiFi Adapter with VirtualBox

Borrowed from Josh, an Amazon Customer that bought a Panda USB WiFi
adapter that uses an mt7612u chipset. This guide should apply to
any USB3 capable adapter.

This guide is intended for those who are facing issues when using an
adapter with Kali. If you are running Kali on VirtualBox from a
Windows host and experiencing problems, here are some troubleshooting
steps to help you out:

1. Make sure you have the latest VirtualBox and Extension Pack installed
before proceeding.

2. Configure USB settings:

- Plug the adapter into your Windows host system.

- In your Kali VM settings, go to Settings > USB.

- Check "Enable USB Controller."

- Select "USB 3.0 (xHCI) Controller" from the list.

- Under "USB Device Filters," add a new USB filter and choose your
adapter (if your adapter uses a Mediatek chip, it should appear as
something like "MediaTek Inc. Wireless").

- Click OK to apply the changes.

3. Verify the adapter connection:

- Start Kali and run "ip addr" from the terminal.

- You should see the adapter listed as "wlan0." Keep in mind that your
adapter may be assigned a different number than 0 or if you have turned
on predictable network interface names then your wireless interface
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

- Install the latest version of VirtualBox and the Extension Pack.

- Repeat the USB settings configuration mentioned earlier, if necessary.

- Launch Kali, and the adapter should now function correctly.

By following these steps, you should be able to resolve any issues with
the adapter's compatibility with Kali on VirtualBox. Also, you're
welcome for the shortcuts ;)

If you have ideas to improve the above guide, please in `Issues`.
