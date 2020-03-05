# vagrant-box-ldk
Vagrant is an open source software for building, maintaining and shipping development environments.<br/>
The idea here is that the required development environment can be made available as a VM, complete with all the necessary utilities compiled, with a keen focus on portability and usability.<br/>

This project aims to provide a linux based development environment.

# Usage
The repository provides a Vagrantfile which configures the linux environment.<br/>
Prior to using this, ensure that the necessary packages are installed:<br/>
1. Install Virtualbox. <br/>
2. Install vagrant. <br/>

Once the required packages are installed, cd to the current working directory where the Vagrantfile is present.<br/>

This also can mount folders onto the vm. The location of the folder to be mounted is set in the config.yaml file present in the current directory header.

```
# Run the vagrant machine
vagrant up

# ssh vm
vagrant ssh

# Pause vm
vagrant suspend

# Halt vm
vagrant halt
```

# Saving and Restoring snapshots

It is often useful to save a snapshot of the vagrant machine.
```
# Halt before saving snapshots
vagrant halt
vagrant snapshot save pristine-install

# Restring snapshots
vagrant snapshot restore pristine-install

# Listing snapshots
vagrant snapshot list
```

# Note:
1. Currently tested on OSX
2. Supports only private networking.

# TODO:
1. Test support with Windows OS.

# Download Links:
Virtualbox: https://www.virtualbox.org/wiki/Downloads <br/>
Vagrant: https://www.vagrantup.com/downloads.html <br/>
