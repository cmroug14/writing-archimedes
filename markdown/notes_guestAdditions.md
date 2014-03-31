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
