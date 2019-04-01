# VirtualBox / Procedures #

The following are standard procedures referenced in this documentation.

* [Procedure to add a user on Linux VM](#procedure-to-add-a-user-on-Linux-vm)
* [Procedure to change hostname on Linux VM](#procedure-to-change-hostname-on-linux-vm)

-------------------------

## Procedure to add a user on Linux VM ##

It is often necessary to add a new user on a Linux VM,
for example a developer that needs to work on software products,
or a support person that is troubleshooting a support issue using a VM.
To add a user (tested on Debian Jessie VM):

1. Start the VM.
2. Login as a user that has `sudo` permissions.
3. `$ sudo adduser user`
	1. In the above `user` is the login name for the user.
	2. The command will prompt for additional information.
4. Optionally, add the user to the `sudo` group so that administrative tasks can be done:  `$ sudo adduser user sudo`
	1. In the above `user` is the login name for the user to be added to `sudo` group.

## Procedure to change hostname on Linux VM ##

A VM that was cloned, imported as an appliance, or otherwise created may have a hostname that needs to be changed.
For example, the hostname may need to be changed to avoid duplicating a similar hostname on the local network.

To change the hostname (tested on Debian Jessie VM):

1. Start the VM.
2. Open a terminal on the VM.
3. Change the hostname by editing system files:
	1. `$ sudo vi /etc/hostname`
		1. Change the single value.
	2. `$ sudo vi /etc/hosts`
		1. Change multiple values.
		2. Also change the domain in the above, if necessary.
	3. `$ sudo vi /etc/ssh/ssh_host_rsa_key.pub`
		1. Change the hostname at the end of the very long line.
	4. `$ sudo vi /etc/ssh/ssh_host_dsa_key.pub`
		1. Change the hostname at the end of the very long line.
4. Restart the system:  `$ sudo reboot`
5. Test that the new settings are in effect:
	1. `$ hostname`
