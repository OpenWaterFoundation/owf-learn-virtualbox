# Open Water Foundation / Learn VirtualBox #

This documentation provides resources to learn how to use the VirtualBox software,
which allows virtual machines (VMs) for "guest" operating systems to be run on the "host" operating system.
This is particularly useful when a full Linux operating system needs to be run on a Windows desktop computer,
for example for software development and testing.

This documentation explains how to:

* install VirtualBox on a host Windows 10 computer
* create guest Linux Debian Jessie "bare VM" with minimal software installed
* export the VM to a "bare appliance"
* import the "bare appliance" to create a new VM
* configure the VM for an environment and save a snapshot

A similar process can be used with other combinations of operating systems.
Once a VM is available, specific software can be installed and configured for a specific purpose.

If a full VM is not needed, consider using [Cygwin](https://learn.openwaterfoundation.org/owf-learn-cygwin/),
Git Bash, MinGW, or Linux Subsystem on Windows 10
([see information about Linux shells](https://learn.openwaterfoundation.org/owf-learn-linux-shell/install/install/)).

This documentation has been written based on experience using VirtualBox at the Open Water Foundation.

## About the Open Water Foundation ##

The [Open Water Foundation](https://openwaterfoundation.org) is a nonprofit social enterprise that focuses
on developing and supporting open source software for water resources, so that organizations can make better decisions about water.
OWF also works to advance open data tools and implementation.
OWF has created this documentation to educate its staff, collaborators, and clients that use VirtualBox.

See also other [OWF learning resources](https://learn.openwaterfoundation.org).

## How to Use this Documentation ##

The documentation is organized in order of information and tasks necessary to install, configure, and use VirtualBox.
The menu on the left lists all pages in the documentation.
The menu on the right lists section in the current page.
If the page width has been made narrow, the menus may be indicted by icons with pop-up menus.

This documentation is not intended to be a full reference for VirtualBox but focuses on topics that
will help understand important technical concepts and be successful with VirtualBox.
See the [Resources](resources/resources.md) section for general information about VirtualBox.

The following conventions are used in this documentation:

* A command prompt of `$` will be shown for a normal user.
* `$ sudo` indicates that a normal user is running a command as superuser (administrative privileges).
* A command prompt of `#` will be shown for the root user.
In most cases this is avoided by running commands with `sudo`.

## License ##

The OWF Learn MkDocs website content and examples are licensed under the
[Creative Commons Attribution-International 4.0 (CC BY 4.0) License](https://creativecommons.org/licenses/by/4.0/).

## Source Repository on GitHub ##

The source files for this documentation are maintained in a GitHub repository:
[owf-learn-virtualbox](https://github.com/OpenWaterFoundation/owf-learn-virtualbox).

## Release Notes ##

See the [issues for the GitHub Project](https://github.com/OpenWaterFoundation/owf-learn-virtualbox/issues).
