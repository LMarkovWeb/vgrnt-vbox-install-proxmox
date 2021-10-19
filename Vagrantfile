# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_NO_PARALLEL'] = 'yes'

Vagrant.configure("2") do |config|

  config.vm.box = "skysilk/proxmox-pve6"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "8192"
    vb.cpus = 4
  end
 
  # proxmox
  config.vm.define "proxmox" do |proxmox|
    proxmox.vm.network "private_network", ip: "192.168.20.50"
    proxmox.vm.network "forwarded_port", id: "proxmox", guest: 8006, host: 8899, guest_ip: "10.0.2.15", host_ip: "127.0.0.1", protocol: "tcp"
  end
end