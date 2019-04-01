# VirtualBox / Windows 10 Host / File Locations #

File locations for VirtualBox software and virtual machines can be confusing.
The following is a summary of important file locations on a Windows 10 host computer.
This documentation was prepared using Virtual Box 6.0.4 installed on Windows 10.

* **VirtualBox Software** - The VirtualBox software typically must be installed by a user
with administrative privileges and installs software to the `C:\Program Files\Oracle\VirtualBox` folder.
Most of the files comprise the ***VirtualBox Manager*** and command line `VBoxManage.exe` program.
However, the following are of particular interest:
	+ `ExtensionPacks/` - installation location for the extension pack,
	used for VirtualBox software and host computer integration.
	+ `VBoxGuestAdditions.iso` - the ISO image that is opened as CD device when installing
	the guest additions, which provides integration of guest and host operating systems.
* **VirtualBox User Files** - VirtualBox user files will be modified through a user's activities
and are written to a location that does not require administrator privileges.
These files are located under `C:\Users\user`:
	+ **VM files (default location)**, `VirtualBox VMs/` - the default location for VMs, which can be used if the `C:` drive
	has adequate space.  If a different drive is used, a similar folder can be created,
	such as `D:\User\user` (`user` would be specific to the user on the system).
	It is typical that this main folder contains subfolders for each VM group,
	with separate folders for machines within a group.
	+ **VirtualBox user files**, `VirtualBox/` - configuration and software log files for VirtualBox software:
		- `VirtualBox.xml` - configuration file that lists VM groups and machines.
		It is useful to review this file to understand how the VirtualBox software works
		and for troubleshooting, but editing it can corrupt VirtualBox.
	+ **Appliance Exports**, `Documents/` - the default folder where appliances will be exported.
	The files are portable and can be moved to other locations and other machines.
* **VirtualBox VMs** - VM files exist in a folder such as `C:\Users\user\VirtualBox VMs` or
alternate such as `D:\Users\user\VirtualBoxVMs`.  Specific folders and files include:
	+ Each MV group is represented by a corresponding folder.
	+ The group `Fresh-OS` is a default that is used for new VMs.
	+ Each VM in a group is represented by a corresponding folder, which includes the following:
		- `Logs/` - logs for VM sessions, written by the VirtualBox software
		- `Snapshots/` - VM snapshots (filename is a hash that does not match the snapshot name)
		- `*.vbox` - VM details as shown in the ***VirtualBox Manager***.
		The VM can belong to zero or more groups and the group names are listed.
		- `*.vbox-prev` - a backup of the `*.vbox` file.
		- `*.vdi` - virtual hard drive
		- **Question:  If a VM belongs to more than one group, what is the ***VirtualBox Manager***'s behavior
		when saving VM files in a group folder?  Does it store in the first group?**
