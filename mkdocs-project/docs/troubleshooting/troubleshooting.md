# VirtualBox / Troubleshooting #

The following are useful resources for troubleshooting.

## General ##

* **Mouse does not move beyond the VM window boundary** - The mouse is captured by the guest VM.
Use the ***Right-ctrl*** key to toggle this behavior.
Fix by installing and configuring guest additions.

## Installation ##

* **Installing the Extension Pack shows error `Cannot install extension pack` (Windows 10)**
	+ This may be because the attempt to install the extension pack did not use an
	account with administrator priveleges.
	Try installing by running the installer from a command prompt window that is run as administrator.
* **Installation of operating system software shows error about not being able access repository (see image below)**
	+ This is usually due to changes on servers, such as phasing out a mirror for old distributions.
	+ It could be due to a temporary internet outage.
	+ Try a different mirror for downloads.
	+ There are usually multiple sites (mirrors) used to find software so continuing with the installation should be OK.

**<p style="text-align: center;">
![error-debian-site](images/error-debian-site.png)
</p>**

**<p style="text-align: center;">
Debian Download Error (<a href="../images/error-debian-site.png">see full-size image</a>)
</p>**

* **After installing guest additions, screen is black after startup**
	+ If using Debian Jessie and Virtual Box 6, try using the ***Display / Graphics Controller*** setting
	of `VBoxVGA`.
	Enabling ***3D Acceleration*** in ***Display*** settings can also cause issues.
