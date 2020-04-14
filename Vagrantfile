# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/8"
  config.vm.box_check_update = false
  config.vm.hostname = "centos8"
  config.vm.provider "virtualbox" do |vb|
  # Display the VirtualBox GUI when booting the machine
     vb.gui = false
     vb.memory = "8192"
     vb.cpus = 4
  end
$install_podman = <<SCRIPT
dnf install -y podman
SCRIPT
  config.vm.provision "shell", inline: $install_podman
end
