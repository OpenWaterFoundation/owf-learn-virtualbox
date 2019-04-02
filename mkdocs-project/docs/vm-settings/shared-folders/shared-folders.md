# VirtualBox / Shared Folders #

This documentation explains how to share folders between guest and host operating system.
This allows files to be copied back and forth using a shared folder.

* [Windows 10 Host](#windows-10-host)
	+ [Linux Debian Jessie Guest VM](#linux-debian-jessie-guest-vm)
	
----

## Windows 10 Host ##

To enable file sharing, do the following on the host machine:

1. Create a convenient folder that can be used for shared files, for example `C:\vbshare`.

Note that it is not necessary to set Windows sharing properties on this folder.

### Linux Debian Jessie Guest VM ###

Do the following on the Linux Debian Jessie guest.

Make sure that the user is in the `vboxsf` group, which grants permissions to shared folders,
where `username` is the user to be configured:

```
$ sudo usermod -a -G vboxsf username
```

Then `cat /etc/group` should show the user listed in the `vboxsf` group.

In ***VirtualBox Manager***, select the VM of interested and Open the ***Shared Folders*** settings.
Then use the ***Add (plus)*** button on the right to add a shared folder.
For example, the following mounts a guest operating system folder `/media/vbshare`
matching the `C:\vbshare` host operating system folder, with the following settings:

* ***Folder Path*** - the host (Windows 10) operating system folder to share
* ***Folder Name*** - repeat the folder name from above, which will be used to display the folder name in the guest operating system
* ***Read-only*** - typically do not want this to be set because want to allow files to be written from either direction
* ***Auto-mount*** - typically want to select because want the shared folder to be configured automatically when the guest operating system starts
* ***Mount point*** - the guest operating system folder where the shared folder will mount
* ***Make Permanent*** - if selected, the shared folder is a ***Machine Folder*** and will be mounted when the VM restarts
(otherwise will be listed in ***Transient Folders***)

**<p style="text-align: center;">
![win-linux-shared-folders1](images/win-linux-shared-folders1.png)
</p>**

**<p style="text-align: center;">
Configure Shared Folder (Editing) (<a href="../images/win-linux-shared-folders1.png">see full-size image</a>)
</p>**

Press ***OK*** to save the settings, which will display the shared folder as follows.

**<p style="text-align: center;">
![win-linux-shared-folders2](images/win-linux-shared-folders2.png)
</p>**

**<p style="text-align: center;">
Configure Shared Folder (Saved) (<a href="../images/win-linux-shared-folders2.png">see full-size image</a>)
</p>**

Press ***OK*** to close the window.

Reboot the VM.  The following should show the shared drive listed among other file systems:

```
$ sudo mount

vbshare on /media/vbshare type vboxsf (rw,nodev,relatime,uid=0,gid=999,ttl=0,dmode=0770,fmode=0770,dmask=00,fmask=00,tag=VBoxAutomounter)
```

The sharing can be tested by copying files into the folder from host or guest operating system.
This is a convenient way to transfer files between machines.
