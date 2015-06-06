

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


# Run the QEMU machine and login
Start a new Droplet and QEMU and the ARM64 image will be automatically provisioned.
```
vagrant up
vagrant ssh
```

Run the QEMU machine, this takes some time.
```
/vagrant/scripts/run-qemu-arm64.sh
```
Now use the credentials `username=ubuntu`, `password=ubuntu` to login into the QEMU machine.

To logout and stop the QEMU machine, kust use:
```
sudo poweroff
```


# TODO
- [ ] create network bridge
- [ ] attach network on start of QEMU machine


DR, 2015