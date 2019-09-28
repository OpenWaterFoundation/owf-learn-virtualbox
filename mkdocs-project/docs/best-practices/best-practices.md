# VirtualBox / Best Practices #

This page provides best practices when using VirtualBox.

* [Organize VMs in Groups](#organize-vMs-in-groups)
* [Shutting Down Machines](#shutting-down-machines)

---------------------

## Organize VMs in Groups ##

It can be confusing to keep track of VMs, even if detailed machine names are used.
The VMs can organized in groups to help avoid confusion, using the ***Group*** feature.
The default group is `Fresh-OS`, which will be used by default.
Examples of groups:

* `Appliances` - (machines meant to be imported as starting point for other VMs)
* `Develop (project)` - machines used for product development
* `Ops (name)` - machines used in operations

To add a new group, right click on a VM and use the ***Group*** menu in the ***VirtualBox Manager***.
A default group with label ***New group*** will be added.
To rename, right-click on the label and select ***Rename Group...***.

It is also a good idea to save the VM hard disk file in a named folder under the group.
For example, use a name `GroupName/VMName/VMName.vdi` for the hard disk file.
This ensures that the files related to the VM are organized and isolated from other VMs.
Use the ***VirtualBox Manager*** to move VMs between groups.
Trying to move the files manually tends to cause confusion with the VirtualBox software.

**Need to understand the folders better because a VM can belong to more than one group.**

## Shutting Down Machines ##

If possible, shut down virtual machines cleanly by using the ***Shutdown*** choice for the login session.
This helps ensure that the state is saved and data are not list.

