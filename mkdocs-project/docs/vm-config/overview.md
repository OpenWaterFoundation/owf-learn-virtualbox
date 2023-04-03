# VirtualBox / VM Configuration / Overview #

*   [Introduction](#introduction)
*   [Linux VM Configuration](#linux-vm-configuration)

----

## Introduction ##

Once a virtual machine (VM) has been created or imported,
additional software needs to be installed to configure the VM for productive use.
The software that is installed depends on the purpose of the VM.

For example, a development machine may require installing compilers, version control, and other software.

A production machine may not require much up front software because a separate installation process
may be used to install production software,
which will be created on the development machine.

It is wise to use snapshots to save the state of the VM prior to installing additional software
and at strategic points.
This allows a snapshot to be restored if the configuration needs to be fixed
(rather than trying to uninstall or correct a software installation).
Using snapshots on a test VM allows the VM to be "wiped" and then software can be reinstalled for testing.

Some level of automation such as self-extracting software installers and configuration scripts
can help to streamline configuring VMS and performing repetitive tasks with consistency.
Investment in automation tends to pay off because troubleshooting and enhancements
result in incremental changes to previous work.

## Linux VM Configuration ##

Configuration of a Linux VMs consists of:

*   Host name properties (e.g., machine name).
*   User accounts (e.g., developers with `sudo` privileges).
*   Common software that is generally useful (e.g., web browsers, editors).
*   Specific software to accomplish specific tasks (e.g., software development tools).

See the following specific examples:

*   [Linux Debian](linux-debian/config-debian.md)
