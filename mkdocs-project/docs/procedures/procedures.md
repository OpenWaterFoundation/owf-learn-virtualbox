# VirtualBox / Procedures #

The following are standard procedures referenced in this documentation.

*   [Procedure to add a user on Linux VM](#procedure-to-add-a-user-on-Linux-vm)
*   [Procedure to change hostname on Linux VM](#procedure-to-change-hostname-on-linux-vm)

-------------------------

## Procedure to add a user on Linux VM ##

It is often necessary to add a new user on a Linux VM,
for example a developer that needs to work on software products,
or a support person that is troubleshooting a support issue using a VM.
To add a user (tested on Debian Jessie VM):

1.  Start the VM.
2.  Login as a user that has `sudo` permissions.
3.   `$ sudo adduser user`
    *   In the above `user` is the login name for the user.
    *   The command will prompt for additional information.
4.  Optionally, add the user to the `sudo` group so that administrative tasks can be done (in the following,
    `user` is the login name for the user to be added to `sudo` group):
    *   `$ sudo adduser user sudo`

## Procedure to change hostname on Linux VM ##

A VM that was cloned, imported as an appliance, or otherwise created may have a hostname that needs to be changed.
For example, the hostname may need to be changed to avoid duplicating a similar hostname on the local network.

To change the hostname (tested on Debian Jessie VM):

1.  Start the VM.
2.  Open a terminal on the VM.
3.  Change the hostname by editing system files:
    1.  `$ sudo vi /etc/hostname`
        *   Change the single value.
    2.  `$ sudo vi /etc/hosts`
        *   Change multiple values.
        *   Also change the domain in the above, if necessary.
    3.  `$ sudo vi /etc/ssh/ssh_host_rsa_key.pub`
        *   Change the hostname at the end of the very long line.
    4.  `$ sudo vi /etc/ssh/ssh_host_dsa_key.pub`
        *   Change the hostname at the end of the very long line.
        *   This is used on Debian jessie.
    5.  `$ sudo vi /etc/ssh/ssh_host_ecdsa_key.pub`
        *   Change the hostname at the end of the very long line.
        *   This is used on Debian stretch.
4.  Restart the system:  `$ sudo reboot`
5.  Test that the new settings are in effect:
    *   `$ hostname`
