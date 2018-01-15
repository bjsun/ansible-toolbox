# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  # config.vm.box_check_update = false
  config.vm.box = "centos/7"
  config.ssh.forward_agent = true
  config.ssh.insert_key = false
  # config.ssh.private_key_path = ["~/.vagrant.d/insecure_private_key"]

  config.vm.define "master" do |master_config|
    master_config.vm.hostname = "master"
    master_config.vm.network :private_network, ip: "10.0.15.10"
    master_config.vm.provider "virtualbox" do |vb|
      vb.name   = master_config.vm.hostname
      vb.memory = "1024"
    end
  end

  (1..2).each do |i|
    config.vm.define "node#{i}" do |nodeconfig|
      nodeconfig.vm.hostname = "node#{i}"
      nodeconfig.vm.network :private_network, ip: "10.0.15.1#{i}"
      nodeconfig.vm.provider "virtualbox" do |vb|
        vb.name   = nodeconfig.vm.hostname
        vb.memory = "1024"
      end
    end
  end
end
