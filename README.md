
# WIP - this readme is work-in-progess
(but the good thing is, the software is absolute ready to run)

## Requirements for Vagrant
You'll need `vagrant` and the `vagrant-digitalocean` plugin on your host machine to create a Digital Ocean droplet. For a detailed description of this plugin, just visit the GH repo https://github.com/smdahlen/vagrant-digitalocean.

```
brew install vagrant
vagrant plugin install vagrant-digitalocean
```

Some usefull Vagrant commands for DigitalOcean:
```
vagrant digitalocean-list -r images $DIGITAL_OCEAN_TOKEN
```

## Resources
https://github.com/smilejay/kvm-book/blob/master/scripts/qemu-ifup-NAT
https://github.com/smilejay/kvm-book/blob/master/scripts/qemu-ifdown-NAT


# Create a local VirtualBox machine
```
vagrant up --provider virtualbox
vagrant ssh
```
Or short version, because the Vagrant provider `virtualbox` is the default provider.
```
vagrant up
vagrant ssh
```

# Create a DigitalOcean Droplet
Start a new Droplet and QEMU and the ARM64 image will be automatically provisioned.
```
vagrant up --provider digital_ocean
vagrant ssh
```

Run the QEMU machine, this takes some time.
```
/vagrant/scripts/run-qemu-arm64.sh
```
Now use the credentials `username=ubuntu`, `password=ubuntu` to login into the QEMU machine.

To logout and stop the QEMU machine, just use:
```
sudo poweroff
```


---
The MIT License (MIT)

Copyright (c) 2015 Dieter Reuter