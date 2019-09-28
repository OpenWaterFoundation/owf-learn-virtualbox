# VirtualBox / Debian / Configuration #

This page describes minimal configuration that is typically needed for a Linux Debian VM.
These steps are performed after an appliance VM is imported.

* [Set Hostname](#set-hostname)
* [Add User](#add-user)
* [Install Needed Software](#install-needed-software)

-----------------------

## Set Hostname

The bare appliance hostname will initially match that of the original VM that was exported to create the appliance.
Consequently, the hostname needs to be changed to avoid confusion, in particular if
the original VM and imported VM exist on the same local network.  To change the hostname:

* `$ sudo vi /etc/hostname`
	+ Change the single hostname to the name that has been chosen.
* `$ sudo vi /etc/hosts`
	+ Change the multiple hostname values.
	+ Also change the domain name in the above, if necessary.
* `$ sudo vi /etc/ssh/ssh_host_rsa_key.pub`
	+ Change the hostname at the end of the very long line.
* `$ sudo vi /etc/ssh/ssh_host_dsa_key.pub`
	+ Change the hostname at the end of the very long line.
	+ This is used for Debian jessie.
* `$ sudo vi /etc/ssh/ssh_host_ecdsa_key.pub`
	+ Change the hostname at the end of the very long line.
	+ This is used for Debian stretch.

Restart the system:

```
$ sudo reboot
```

Then login and test that the hostname has been updated:

```
$ hostname
```

## Add User

A bare appliance will be distributed with a `root` and other user, as configured by the Linux installation.
The latter is typically added to the `sudo` group when preparing the appliance
so that administrative tasks can be performed
using the `sudo` command without logging into root.
The following example shows how to add a new user `auser` and add to the `sudo` group:

To add a user:

* Login as root or account that has `sudo` privileges.
* `$ sudo adduser auser`
	+ in the above `auser` is the login name for the new user
	+ the command will prompt for additional information
* `$ sudo adduser auser sudo`
	+ in the above `auser` is the login name for the new user

Once added, the `auser` user account can be used to run commands as root using:

```
$ sudo some-command
```

## Install Needed Software

The VM appliance will have minimal software installed, depending on the requirements for the VM.
Additional software will need to be installed using `apt-get`.
For example, to install the `gcc` compiler:

```
$ sudo apt-get install gcc
```
