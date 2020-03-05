# encoding: utf-8
# -*- mode: ruby -*-
# vi: set ft=ruby :
# Box / OS
VAGRANT_BOX = 'ubuntu/trusty64'

# Reading configuration file
custom = nil
custom_configs = %w( config.yaml config.yaml.default )
custom_configs.each { |filename|
  filepath = File.dirname(File.expand_path(__FILE__)) + "/" + filename
  if File.exist?(filepath)
    custom = YAML.load_file(filepath)
    break
  end
}
# Currently there is a hard dependency on the config file existing. Will remove this dependency in future versions



# Memorable name for your
VM_NAME = 'ldk'
# VM User — 'vagrant' by default
VM_USER = 'vagrant'
# Username on your Device
MAC_USER = 'jvenkit1'
# VM Port — uncomment this to use NAT instead of DHCP
# VM_PORT = 8080
Vagrant.configure(2) do |config|
  # Vagrant box from Hashicorp
  config.vm.box = VAGRANT_BOX

  # Actual machine name
  config.vm.hostname = VM_NAME
  # Set VM name in Virtualbox
  config.vm.provider "virtualbox" do |v|
    v.name = VM_NAME
    v.memory = 2048
  end
  #DHCP — comment this out if planning on using NAT instead
  # config.vm.network "private_network", type: "dhcp"
  # # Port forwarding — uncomment this to use NAT instead of DHCP
  # config.vm.network "forwarded_port", guest: 80, host: VM_PORT
  # Sync folder
  custom['shared_folder_mounts'].each { |mount|
    from_host = File.expand_path(mount['from_host'])
    to_guest = mount['to_guest']

    if File.directory?(from_host)
      # parent dirs to be auto-created by synced_folder mount
      config.vm.synced_folder from_host, to_guest
    else
      puts "WARNING: Will skip mounting of non-existent optional host directory"
      puts "  from_host: " + from_host
      puts "  to_guest:  " + to_guest
    end
  }
  # config.vm.synced_folder HOST_PATH, GUEST_PATH
  # # Disable default Vagrant folder, use a unique path per project
  # config.vm.synced_folder '.', '/home/'+VM_USER+'', disabled: true
  # Install Git
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y git
    apt-get install -y build-essential
    apt-get update
    apt-get upgrade -y
    apt-get autoremove -y
  SHELL
end
