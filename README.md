# vagrant-box-ldk
Linux development kit via Vagrant

# Usage
The repository provides a Vagrantfile which configures the linux environment.<br/>
Prior to using this, ensure that the necessary packages are installed:<br/>
1. Install Virtualbox <br/>
2. Install vagrant <br/>

Once the required packages are installed, cd to the current working directory where the Vagrantfile is present.<br/>

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
