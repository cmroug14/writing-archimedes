## Notes: GuestAdditions Version Mismatch

For some reason shutting down the machine and restarting it fixed the problem.  Need to keep an eye on the problem and come up with a more permanent solution.

Potentially relevant [issue thread](https://github.com/dotless-de/vagrant-vbguest/issues/95).

    Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
    $ vagrant up
    Bringing machine 'default' up with 'virtualbox' provider...
    [default] Clearing any previously set forwarded ports...
    [default] Clearing any previously set network interfaces...
    [default] Preparing network interfaces based on configuration...
    [default] Forwarding ports...
    [default] -- 22 => 2222 (adapter 1)
    [default] -- 80 => 8888 (adapter 1)
    [default] -- 8080 => 8889 (adapter 1)
    [default] -- 3030 => 3333 (adapter 1)
    [default] Booting VM...
    [default] Waiting for machine to boot. This may take a few     minutes...
    DL is deprecated, please use Fiddle
    [default] Machine booted and ready!
    Got different reports about installed GuestAdditions version:
    Virtualbox on your host claims:   4.2.16
    VBoxService inside the vm claims: 4.3.6
    Going on, assuming VBoxService is correct...
    vGuestAdditions seems to be installed (4.3.6) correctly, but not running.
    Got different reports about installed GuestAdditions version:
    Virtualbox on your host claims:   4.2.16
    VBoxService inside the vm claims: 4.3.6
    Going on, assuming VBoxService is correct...
    Starting the VirtualBox Guest Additions ...done.
    Got different reports about installed GuestAdditions version:
    Virtualbox on your host claims:   4.2.16
    VBoxService inside the vm claims: 4.3.6
    Going on, assuming VBoxService is correct...
    [default] Mounting shared folders...
    [default] -- /imgs
    [default] -- /vagrant
    [default] VM already provisioned. Run `vagrant provision` or use `--provision` to force it

    Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
    $ vagrant halt
    [default] Attempting graceful shutdown of VM...
    DL is deprecated, please use Fiddle
    
    Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy     (master)
    $ vagrant up
    Bringing machine 'default' up with 'virtualbox' provider...
    [default] Clearing any previously set forwarded ports...
    [default] Clearing any previously set network interfaces...
    [default] Preparing network interfaces based on configuration...
    [default] Forwarding ports...
    [default] -- 22 => 2222 (adapter 1)
    [default] -- 80 => 8888 (adapter 1)
    [default] -- 8080 => 8889 (adapter 1)
    [default] -- 3030 => 3333 (adapter 1)
    [default] Booting VM...
    [default] Waiting for machine to boot. This may take a few     minutes...
    DL is deprecated, please use Fiddle
    [default] Machine booted and ready!
    GuestAdditions 4.3.6 running --- OK.
    [default] Mounting shared folders...
    [default] -- /imgs
    [default] -- /vagrant
    [default] VM already provisioned. Run `vagrant provision` or use `--provision` to force it

    Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
    $ vagrant vbguest --status
    DL is deprecated, please use Fiddle
    GuestAdditions 4.3.6 running --- OK.

---------
## March 31: Version Mismatch Returns

[vbguest plugin](http://kvz.io/blog/2013/01/16/vagrant-tip-keep-virtualbox-guest-additions-in-sync/) unsuccessful

````
Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
$ vagrant up
Bringing machine 'default' up with 'virtualbox' provider...
[default] Clearing any previously set forwarded ports...
[default] Clearing any previously set network interfaces...
[default] Preparing network interfaces based on configuration...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] -- 80 => 8888 (adapter 1)
[default] -- 8080 => 8889 (adapter 1)
[default] -- 3030 => 3333 (adapter 1)
[default] Booting VM...
[default] Waiting for machine to boot. This may take a few minutes...
DL is deprecated, please use Fiddle
[default] Machine booted and ready!
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
GuestAdditions seems to be installed (4.3.6) correctly, but not running.
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
Starting the VirtualBox Guest Additions ...done.
[default] Mounting shared folders...
[default] -- /imgs
[default] -- /vagrant
[default] VM already provisioned. Run `vagrant provision` or use `--provision` t
o force it

Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
$ vagrant vbguest --do install
DL is deprecated, please use Fiddle
GuestAdditions 4.3.6 running --- OK.
Reading package lists...
Building dependency tree...
Reading state information...
dkms is already the newest version.
linux-headers-3.11.0-15-generic is already the newest version.
The following packages were automatically installed and are no longer required:
  libxfont1 libxkbfile1 x11-xkb-utils xfonts-base xfonts-encodings
  xfonts-utils xserver-common xserver-xorg-core
Use 'apt-get autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 10 not upgraded.
Copy iso file C:\Program Files\Oracle\VirtualBox\VBoxGuestAdditions.iso into the
 box /tmp/VBoxGuestAdditions.iso
mount: block device /tmp/VBoxGuestAdditions.iso is write-protected, mounting rea
d-only
Forcing installation of Virtualbox Guest Additions 4.3.6 - guest version is 4.3.
6
Verifying archive integrity... All good.
Uncompressing VirtualBox 4.3.6 Guest Additions for Linux............
VirtualBox Guest Additions installer
Removing installed version 4.3.6 of VirtualBox Guest Additions...
Copying additional installer modules ...
Installing additional modules ...
Removing existing VirtualBox DKMS kernel modules ...done.
Removing existing VirtualBox non-DKMS kernel modules ...done.
Building the VirtualBox Guest Additions kernel modules ...done.
Doing non-kernel setup of the Guest Additions ...done.
You should restart your guest to make sure the new modules are actually used

Installing the Window System drivers ...fail!
(Could not find the X.Org or XFree86 Window System.)
An error occurred during installation of VirtualBox Guest Additions 4.3.6. Some
functionality may not work as intended.
In most cases it is OK that the "Window System drivers" installation failed.
/home/vagrant/.profile: line 6: $'\r': command not found
/home/vagrant/.profile: line 10: $'\r': command not found
/home/vagrant/.profile: line 28: syntax error: unexpected end of file

Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
$
````
Attempt to install vbguest:

````
Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
$ vagrant vbguest --do install
DL is deprecated, please use Fiddle
GuestAdditions 4.3.6 running --- OK.
Reading package lists...
Building dependency tree...
Reading state information...
dkms is already the newest version.
linux-headers-3.11.0-15-generic is already the newest version.
The following packages were automatically installed and are no longer required:
  libxfont1 libxkbfile1 x11-xkb-utils xfonts-base xfonts-encodings
  xfonts-utils xserver-common xserver-xorg-core
Use 'apt-get autoremove' to remove them.
0 upgraded, 0 newly installed, 0 to remove and 10 not upgraded.
Copy iso file C:\Program Files\Oracle\VirtualBox\VBoxGuestAdditions.iso into the
 box /tmp/VBoxGuestAdditions.iso
mount: block device /tmp/VBoxGuestAdditions.iso is write-protected, mounting rea
d-only
Forcing installation of Virtualbox Guest Additions 4.3.6 - guest version is 4.3.
6
Verifying archive integrity... All good.
Uncompressing VirtualBox 4.3.6 Guest Additions for Linux............
VirtualBox Guest Additions installer
Removing installed version 4.3.6 of VirtualBox Guest Additions...
Copying additional installer modules ...
Installing additional modules ...
Removing existing VirtualBox DKMS kernel modules ...done.
Removing existing VirtualBox non-DKMS kernel modules ...done.
Building the VirtualBox Guest Additions kernel modules ...done.
Doing non-kernel setup of the Guest Additions ...done.
You should restart your guest to make sure the new modules are actually used

Installing the Window System drivers ...fail!
(Could not find the X.Org or XFree86 Window System.)
An error occurred during installation of VirtualBox Guest Additions 4.3.6. Some
functionality may not work as intended.
In most cases it is OK that the "Window System drivers" installation failed.
/home/vagrant/.profile: line 6: $'\r': command not found
/home/vagrant/.profile: line 10: $'\r': command not found
/home/vagrant/.profile: line 28: syntax error: unexpected end of file

Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
$ vagrant reload
[default] Attempting graceful shutdown of VM...
DL is deprecated, please use Fiddle
[default] Clearing any previously set forwarded ports...
[default] Clearing any previously set network interfaces...
[default] Preparing network interfaces based on configuration...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] -- 80 => 8888 (adapter 1)
[default] -- 8080 => 8889 (adapter 1)
[default] -- 3030 => 3333 (adapter 1)
[default] Booting VM...
[default] Waiting for machine to boot. This may take a few minutes...
[default] Machine booted and ready!
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
GuestAdditions seems to be installed (4.3.6) correctly, but not running.
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
Starting the VirtualBox Guest Additions ...done.
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
[default] Mounting shared folders...
[default] -- /imgs
[default] -- /vagrant
[default] VM already provisioned. Run `vagrant provision` or use `--provision` t
o force it

Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
$ vagrant plugin install vagrant-vbguest
Installing the 'vagrant-vbguest' plugin. This can take a few minutes...
Installed the plugin 'vagrant-vbguest (0.10.0)'!

Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
$ vagrant reload
[default] Attempting graceful shutdown of VM...
DL is deprecated, please use Fiddle
[default] Clearing any previously set forwarded ports...
[default] Clearing any previously set network interfaces...
[default] Preparing network interfaces based on configuration...
[default] Forwarding ports...
[default] -- 22 => 2222 (adapter 1)
[default] -- 80 => 8888 (adapter 1)
[default] -- 8080 => 8889 (adapter 1)
[default] -- 3030 => 3333 (adapter 1)
[default] Booting VM...
[default] Waiting for machine to boot. This may take a few minutes...
[default] Machine booted and ready!
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
GuestAdditions seems to be installed (4.3.6) correctly, but not running.
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
Starting the VirtualBox Guest Additions ...done.
Got different reports about installed GuestAdditions version:
Virtualbox on your host claims:   4.2.16
VBoxService inside the vm claims: 4.3.6
Going on, assuming VBoxService is correct...
[default] Mounting shared folders...
[default] -- /imgs
[default] -- /vagrant
[default] VM already provisioned. Run `vagrant provision` or use `--provision` t
o force it
````

## After Updating VirtualBox

````
Christine@CHRISTINE-PC ~
$ cd Desktop/vagrant-cite/ubuntu-saucy/

Christine@CHRISTINE-PC ~/Desktop/vagrant-cite/ubuntu-saucy (master)
$ vagrant up
There was an error while executing `VBoxManage`, a CLI used by Vagrant
for controlling VirtualBox. The command and stderr is shown below.

Command: ["showvminfo", "6b371836-f806-4696-bddf-788836a6452a"]

Stderr: VBoxManage.exe: error: Failed to create the VirtualBox object!
VBoxManage.exe: error: Code CO_E_SERVER_EXEC_FAILURE (0x80080005) - Server execu
tion failed (extended info not available)
VBoxManage.exe: error: Most likely, the VirtualBox COM server is not running or
failed to start.
````