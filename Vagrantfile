# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # config.vm.define :config_master do |config|
    config.vm.box = "bento/ubuntu-22.04"
    # config.vm.box = "generic/rhel9"
    config.vm.hostname = "servera"
    config.vm.box_check_update = false

  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # config.vm.network "private_network", ip: "192.168.33.10"

  # config.vm.network "public_network"

  # To enable all vagrant experimental feature do: export VAGRANT_EXPERIMENTAL="1"
  # config.vm.disk :disk, size: "20GB", primary: true

  # config.vm.synced_folder "../data", "/vagrant_data"

    config.vm.provider "libvirt" do |libvirt|
      # Display the VirtualBox GUI when booting the machine
      # libvirt.gui = true
    
      # Customize the amount of memory on the VM:
      libvirt.memory = "2048"
      libvirt.cpus = "2"
      # below add extra disk not update primary
      libvirt.storage :file, :size => '20G'
      
      # note: kvm is fast & qemu is slow
      libvirt.driver = "kvm"
      # libvirt.driver = "qemu"
      # libvirt.default_prefix = "k8s-vm"
      # libvirt.title= "k8s-master-node"
    end
    
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get upgrade -y
      # apt-get install -y apache2
    SHELL
  end
# end
