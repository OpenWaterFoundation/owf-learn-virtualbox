# VirtualBox / Troubleshooting #

The following are useful resources for troubleshooting.

## General ##

* **Mouse does not move beyond the VM window boundary** - The mouse is captured by the guest VM.
Use the ***Right-ctrl*** key to toggle this behavior.
Fix by installing and configuring guest additions.

## Installation ##

* **After installing guest additions, screen is black after startup**
	+ If using Debian Jessie and Virtual Box 6, try using the ***Display / Graphics Controller*** setting
	of `VBoxVGA`.
	Enabling ***3D Acceleration*** in ***Display*** settings can also cause issues.
