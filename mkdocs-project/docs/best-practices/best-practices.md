# VirtualBox / Best Practices #

This page provides best practices when using VirtualBox.

* [Use Snapshots](#use-snapshots)
* [Organize VMs in Groups](#organize-vMs-in-groups)
* [Shutting Down Machines](#shutting-down-machines)
* [Use Shared Folders to Transfer Files](#use-shared-folders-to-transfer-files)

---------------------

## Use Snapshots ##

Snapshots can save time when recovering from a corrupted VM
(e.g., installed incompatible software),
or when repeating software installation and testing.
See the [Snapshots](../snapshots/snapshots.md) documentation.

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

**In general, specify new groups when important appliances, and move VMs between
groups using the ***VirtualBox Manager*** rather than moving VM files using file system tools.**

## Shutting Down Machines ##

If possible, shut down virtual machines cleanly by using the ***Shutdown*** choice for the login session.
This helps ensure that the state is saved and data are not list.
Shutdown can also be started from the command line, for example:

```
$ sudo shutdown now
```

## Use Shared Folders to Transfer Files ##

It is often necessary to move files between host and guest VMs.
A simple way to do this is to create a standard folder, for example on Windows 10 host.
Then use shared folders on all the VMs mounting the Windows folder.
Files can then be copied to and from the shared folder, minimizing the need for `ftp`, `scp`,
or other transfer commands.
