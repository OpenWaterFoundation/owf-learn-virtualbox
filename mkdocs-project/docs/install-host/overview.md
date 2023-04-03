# VirtualBox / Install / Overview #

VirtualBox should be installed on the host computer within which guest virtual machines will be run.

This documentation focuses on installing VirtualBox on a Windows 10/11 host computer
and creating Linux Debian guest virtual machines.
This allows typical software that is run on Windows to be used for day-to-day tasks
and use the Linux virtual machines for software development and testing.

See the following to enable interoperability:

*   Install guest additions when creating a guest VM
    (see documentation sections in the "Create Guest VM" documentation for various operationg systems).
*   Shared folders can be defined to share files between Windows and Linux
    (see the [Shared Folders](../vm-settings/shared-folders/shared-folders.md) documentation).

Specific installation instructions are available for the following host operating systems:

*   [Microsoft Windows](win/install-win-host.md)
