# VirtualBox / Windows 10 Host / Export Linux Debian Jessie VM Appliance #

Once a VM has been created, it can be exported as an "appliance", which is a self-contained
VM file that can be imported into VirtualBox running on another computer.
This is useful when a standard environment needs to be used on multiple computers,
for example for software development, software testing, or operational system.

To export a Linux Debian Jessie appliance, first make sure that the VM is stopped.
Then select the ***VirtualBox Manager / Tools***.

Select the ***Export*** tool.  Select the VM to export, as shown in the following image.

**<p style="text-align: center;">
![export-debian-jessie1](images/export-debian-jessie1.png)
</p>**

**<p style="text-align: center;">
Export Debian Jessie Virtual Machine (<a href="../images/export-debian-jessie1.png">see full-size image</a>)
</p>**

The default "guided mode" can be used by pressing ***Next***, which uses typical defaults.

The default selections will for the most part be OK.
However, because the VM will be reused, the initial name (for example `vb-sam-j64-dev04-nscore`) can be
simplified (for example `vb-j64-nscore`).  The file extension will be consistent with the format.
Using the default `ova` extension results in a single file for the appliance, which simplifies moving the appliance.

**<p style="text-align: center;">
![export-debian-jessie2](images/export-debian-jessie2.png)
</p>**

**<p style="text-align: center;">
Export Debian Jessie Virtual Machine - Details (<a href="../images/export-debian-jessie2.png">see full-size image</a>)
</p>**

Press ***Next*** to continue.  The following will be shown to configure system settings.
The initial defaults will be similar to the following, where the name matches the VM name that is being exported.

**<p style="text-align: center;">
![export-debian-jessie3](images/export-debian-jessie3.png)
</p>**

**<p style="text-align: center;">
Export Debian Jessie Virtual Machine - Virtual System Settings (Default) (<a href="../images/export-debian-jessie3.png">see full-size image</a>)
</p>**

Similar to changing the filename, the name of the VM can be changed to the more general form.
This general name can be changed when the appliance is imported later.
Information for the product can also be specified, as shown in the following example.

**<p style="text-align: center;">
![export-debian-jessie4](images/export-debian-jessie4.png)
</p>**

**<p style="text-align: center;">
Export Debian Jessie Virtual Machine - Virtual System Settings (Specific) (<a href="../images/export-debian-jessie4.png">see full-size image</a>)
</p>**

Press ***Export*** to export the appliance.  A progress bar will be shown.  The export will take a few minutes.

**<p style="text-align: center;">
![export-debian-jessie5-progress](images/export-debian-jessie5-progress.png)
</p>**

**<p style="text-align: center;">
Export Debian Jessie Virtual Machine - Progress (<a href="../images/export-debian-jessie5-progress.png">see full-size image</a>)
</p>**

The following illustrates the output file.

**<p style="text-align: center;">
![export-debian-jessie6-file](images/export-debian-jessie6-file.png)
</p>**

**<p style="text-align: center;">
Export Debian Jessie Virtual Machine - Output File (<a href="../images/export-debian-jessie6-file.png">see full-size image</a>)
</p>**

After exporting the appliance, the file can be placed in a location for downloads.
