# VirtualBox / Troubleshooting #

The following are useful resources for troubleshooting.

*   [Debian Linux Guest](#debian-linux-guest)
    +   [Debian Linux: General](#debian-linux-general)
    +   [Debian Linux: Installation](#debian-linux-installation)
    +   [Debian Linux: Network](#debian-linux-network)

---

## Debian Linux Guest ##

The following troubleshooting issues have occurred on a Debian Linux guest.

### Debian Linux: General ###

**Issue: Mouse does not move beyond the VM window boundary**

*   **Possible Solution**:
    +   The mouse is captured by the guest VM.  Use the ***Right-ctrl*** key to toggle this behavior.
        Fix by installing and configuring guest additions.

**Issue:  On Debian Stretch, display shows black after some period of time and does not respond to mouse or keyboard input**

*   **Symptoms**:
    +   Entire Linux desktop displays in black and is nonresponsive to keyboard or mouse input.
    +   VirtualBox menus in menu bar for the VM are functional.
    +   Can `ssh` into the VM.
+   **Possible Solution**:
    +   Make sure that screen saver software is installed, for example `xscreensaver`.

**Issue:  The VM becomes nonresponsive to keyboard input**

*   **Symptoms**:
    +   Has been seen on Debian Jessie.
    +   The keyboard becomes nonresponsive.
    +   In a terminal window it is necessary to hold down a key for a period of time in order for the character to appear.
    +   The issue is specific to a single VM - other VMs behave as usual.
*   **Work-around** (solution below is recommended rather than work-around):
    +   Right-click on the ***USB Settings*** icon at the bottom of the VM window and select the keyboard,
        for example Microsoft Natural Ergonomic Keyboard 4000.
        This seems to assign the keyboard to the VM and it won't be recognized by other VMs.
    +   Reboot the VM.
+   **Information**:
    +   Holding a key down, for example in a terminal window, causes the VM to go into "slow keys" mode.
        Apparently this is to allow people with disabilities to use keyboards
        without multiple characers displaying due to slow keystrokes.
        This can be accidentally triggered, for example when using `vim` editor and holding a key down
        for awhile, or becoming distracted and holding a key down.
+   **Possible Solution**:
    +   To fix, change mouse focus to the VM for a terminal window and hold the ***Shift*** key down for several seconds
        until ***Slow keys are disabled*** popup shows.
        Apparently the threshold for toggling the setting is a time that would not normally occur
        and can therefore clearly be used to indicate the toggle.

### Debian Linux: Installation ###

**Issue: Installing the Extension Pack shows error `Cannot install extension pack` (Windows 10)**

*   Note:  Installing the extension pack is not usually needed and is only free for personal and evaluation use.
*   This may be because the attempt to install the extension pack did not use an
    account with administrator priveleges.
    Try installing by running the installer from a command prompt window that is run as administrator.

**Issue:  While installing the operating system software, an error is shown about not being able access repository (see image below)**

*   This is usually due to changes on servers, such as phasing out a mirror for old distributions.
*   It could be due to a temporary internet outage.
*   Try a different mirror for downloads.
*   The operating system may have moved from active/supported to a different state, such as archive.
    This requires changing the `apt` `sources.list` file so that software is retrieved from the appropriate server.
    For example, for Debian, older versions such as jessie must use archive mirror.

**<p style="text-align: center;">
![Debian download error](images/error-debian-site.png)
</p>**

**<p style="text-align: center;">
Debian Download Error (<a href="../images/error-debian-site.png">see full-size image</a>)
</p>**

**Issue: After installing guest additions, screen is black after startup**

*   If using Debian Jessie and Virtual Box 6, try using the ***Display / Graphics Controller*** setting
    of `VBoxVGA`.
Enabling ***3D Acceleration*** in ***Display*** settings can also cause issues.

### Debian Linux: Network ###

**Issue:  Running the VM appliance says
could not start the machine because a physical network device is missing.**

**<p style="text-align: center;">
![Debian missing network interface error](images/error-debian-missing-network-interface-1.png)
</p>**

Clicking on ***Change Network Settings*** shows the following.
Press ***OK*** to save and all seems OK.

**<p style="text-align: center;">
![Debian network configuration](images/error-debian-missing-network-interface-2.png)
</p>**

**Issue:  Error communicating on the network**

The VM may exhibit issues such as not being able to download software using `apt`.
The VM may show other than the normal network address such as `127.0.0.1`.
It may be necessary to turn off IPv6 on the Windows host machine using
***Settings / Network & Internet / Change adapter options***.
Right-click on ***Wi-Fi*** and open the ***Properties*** and uncheck
***Internet Protocol Version 6 (TCP/IpV6)*** as shown below.
Note that disabling IP 6 may have other impacts on the computer but IP 4 is often the default.

**<p style="text-align: center;">
![Debian missing network interface error](images/error-debian-windows-ip6.png)
</p>**
