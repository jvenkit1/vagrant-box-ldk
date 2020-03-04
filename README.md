# vagrant-box-ldk
Linux development kit via Vagrant

# Usage
The repository provides a Vagrantfile which configures the linux environment.<br/>
Prior to using this, ensure that the necessary packages are installed:<br/>
1. Install Virtualbox <br/>
2. Install vagrant <br/>

Once the required packages are installed, cd to the current working directory where the Vagrantfile is present.<br/>
Run `vagrant up` to start the VM.<br/>
This will download and create a Ubuntu based virtual environment for development. To access the environment, we need to ssh into the vm.<br/>
Run `vagrant ssh` to ssh into the VM. <br/>
If you want to halt the VM, run `vagrant halt`. <br/>
Alternately, if you want to suspend the VM temporarily, run `vagrant suspend`. <br/>

# Note:
1. Currently will work only on Unix subsystems such as a Macbook.
2. Networking is currently disabled.
