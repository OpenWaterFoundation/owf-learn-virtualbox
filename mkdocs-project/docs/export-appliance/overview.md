# VirtualBox / Export Appliance / Overview #

A VirtualBox virtual machine (VM) can be exported at any point to create an "appliance",
which is a self-contained environment that can be used as the starting point for work on the virtual machine.
Exported VMs are saved in a standard format such as an `ova` file that can be imported to create a new VM instance.
Examples of appliances include:

*   "Fresh" ("bare") operating system that is the foundation for additional software installation and configuration.
*   Pre-configured environments for development, test, and production software environments.
    For example, use these appliances to help a development team be efficient.
*   Self-contained machines for deployment in production environments.
    For example, create deployable VMs to install on many desktop computers that need to run a system.

See the following examples of how to export an appliance:

*   [Windows host exporting Linux Debian Jessie VM](linux-debian-jessie/export-appliance-debian-jessie.md)
