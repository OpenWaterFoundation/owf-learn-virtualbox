# VirtualBox / Debian / Configuration #

This page describes minimal configuration that is typically needed for a Linux Debian VM
for a single VM user, for example a software developer/tester.
These steps are performed after an appliance VM is imported.

*   [Introduction](#introduction)
*   [Save Snapshot Before Configuring](#save-snapshot-before-configuring)
*   [Set Hostname](#set-hostname)
*   [Add User](#add-user)
*   [Install Needed Software](#install-needed-software)
*   [Configure VM for User](#configure-vm-for-user)
*   [Save Snapshot After Configuring](#save-snapshot-after-configuring)
*   [Additional Configuration](#additional-configuration)

-----------------------

## Introduction ##

It is helpful to configure the VM for a user with as much general configuration as
possible and then take a snapshot so that the VM can be returned to that state if necessary.
If the VM is used for multiple users,
then a similar approach can be taken and the resulting VM can be exported as a new appliance for wider use.
If any of the setup steps need to be repeated, restore a previous snapshot,
configure as appropriate, and save another snapshot.
The final resulting snapshot can be used as a starting point for more complex configuration steps.

## Save Snapshot Before Configuring ##

It is useful to save a snapshot before any configuration in case subsequent configuration
causes problems and must be discarded.
See the [Snapshots](../../snapshots/snapshots.md)
documentation for information on creating and restoring snapshots.

## Set Hostname

The bare appliance hostname will initially match that of the original VM that was exported to create the appliance.
Consequently, the hostname needs to be changed to avoid confusion, in particular if
the original VM and imported VM exist on the same local network.
To change the hostname run the following commands as a user with `sudo` permissions
(or use the root account without `sudo`):

*   `$ sudo vi /etc/hostname`
    +   Change the single hostname to the name that has been chosen.
*   `$ sudo vi /etc/hosts`
    +   Change the multiple hostname values.
    +   Also change the domain name in the above, if necessary.
*   `$ sudo vi /etc/ssh/ssh_host_rsa_key.pub`
    +   Change the hostname at the end of the very long line.
*   If the VM is Debian stretch or later:
    +   `$ sudo vi /etc/ssh/ssh_host_ecdsa_key.pub`
        -   Change the hostname at the end of the very long line.
*   If the VM is Debian jessie (an older operating system):
    +   `$ sudo vi /etc/ssh/ssh_host_dsa_key.pub`
        -   Change the hostname at the end of the very long line.

Restart the system:

```
$ sudo reboot
```

Then login and test that the hostname has been updated:

```
$ hostname
```

## Add User

A bare appliance will be distributed with a `root` and "other user",
as configured when the VM was configured for an appliance.
The "other user" is typically added to the `sudo` group when preparing the appliance
so that administrative tasks can be performed
using the `sudo` command without logging into root.
For example, this might be a standard service account used for troubleshooting and support.
The root password and information for the "other user" will be provided
by the creator of the appliance.

The following example shows how to add an additional new user `someuser` and add to the `sudo` group.
This ensures that the `someuser` can be used for development without
using the `root` or "other user" that was originally distributed with the VM appliance.

To add a user:

*   Login as root or account that has `sudo` privileges.
    The `sudo` can be omitted from the following commands if the are executed by the root user.
*   `$ sudo adduser someuser`
    +   in the above `someuser` is the login name for the new user
    +   the command will prompt for additional information including the user name

To additionally grant `sudo` privileges to the user:

*   `$ sudo adduser someuser sudo`
    +   in the above `someuser` is the login name for the new user
*   Logout and log back in so that the Linux session recognizes
    that the user is in the `sudo` group.

Once added, the `someuser` user account can be used to run commands as root using:

```
$ sudo some-command
```

## Install Needed Software ##

It may make sense to configure the user's environment (see next section) before installing software.
However, sometimes the environment depends on installing the software first.

The VM appliance will have minimal software installed, depending on the requirements for the VM.
Additional software will need to be installed using `apt-get`.
For example, to install the `gcc` compiler:

```
$ sudo apt-get update
$ sudo apt-get install gcc
```

The first command updates the catalog of software packages and versions,
so that `apt` commands has up-to-date information to manage software installations.

The following are typical software tools that may be installed during VM configuration
so that they don't need to be reinstalled after restoring a snapshot.
These software packages will typically be installed in the system files
(e.g., `/usr/bin`), whereas the next section describes files that are installed in
user files (e.g., for the single user that uses the VM for software development).
Alternatively, the packages can be installed after a more basic snapshot
is restored.

Packages that are needed for a VM are typically indicated by a development team
and cannot be anticipated for this general documentation.

**<p style="text-align: center;">
Example Linux Packages to Install
</p>**

| **`apt-get` Software Package** | **Description** |
| -- | -- |
| `gcc` | C language compiler, used to compile many software tools. |
| `git` | Version control software. | 
| `kdiff3` | Software to visually compare differences between files. |
| `openjdk-8-jdk` | Java 8 standard development kit (or alternate version). |

## Configure VM for User ##

The user's environment can usually be configured before installing software (previous section).
However, some software, such as Git prompt scripts, need to be installed in order to test the user account configuration.

The previous section discussed installing useful software on the VM,
typically that is needed for one or more software development projects.
It may also be useful to configure a specific user environment so that such
configuration is available after a snapshot restore.

It can be useful to store user files in a Git repository and/or copy from another VM using shared folder,
which requires some back and forth in the order of configuration.
For example, define the VM user, then set up a shared folder,
then copy files from another VM, and finally, fine-tune on the new VM.

The following is a list of configuration tasks that might be performed.

1.  Configure `vim` text editor (or other editor):
    1.  Install a `~/.vimrc` file that has preferred settings.
2.  Configure terminal settings:
    1.  For example, after opening a terminal, use
        ***Edit / Profile Preferences / Colors*** and pick a suitable color theme
        such as ***White on black***.
    2.  Configure screen saver.
3.  Configure `~/.bashrc` and `~/.bash_profile`:
    1.  For example add Git prompt and Git completion scripts.
    2.  Add configuration for specific development tools.
    3.  Define useful command aliases.
4.  Configure shared folders for VM:
    1.  See [Shared Folder](../../vm-settings/shared-folders/shared-folders.md) instructions.

## Save Snapshot After Configuring ##

Once the VM has been configured by installing and configuring system software and
user environment, a snapshot can be made to preserve the state of the machine.
This allows the snapshot to be restored to that point,
for example if the machine has become cluttered with files or corrupted with non-working software.
See the [Snapshots](../../snapshots/snapshots.md)
documentation for information on creating and restoring snapshots.

## Additional Configuration ##

The previous sections discuss how to configure system and user files and save a snapshot for
the basic configuration.
Once a snapshot has been created, additional configuration may occur.
For example, clone Git repositories and set up a specific development environment for software project(s).
For example, for Java development, this may involve installing Java, Eclipse, and other tools
consistent with the versions needed for the software project.
These steps can be automated with scripts in the software product repository.

Additional snapshots can be created for different states of the VM, as appropriate.
