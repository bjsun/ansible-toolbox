# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box_check_update = false
  config.vm.box = "centos/7"
  # config.vm.box = "ubuntu/trusty64"
  # config.vm.box = "ubuntu/xenial64"
  config.ssh.forward_agent = true
  config.hostmanager.enabled = true
  # Disable the new default behavior introduced in Vagrant 1.7, to
  # ensure that all Vagrant machines will use the same SSH key pair.
  # See https://github.com/mitchellh/vagrant/issues/5005
  config.ssh.insert_key = false
  # VM Define
  cluster = [
    { :name => 'master', :ip => '10.10.10.10', :memory => 2048, :cpu => 2},
    { :name => 'node1',  :ip => '10.10.10.11', :memory => 1024, :cpu => 1},
    { :name => 'node2',  :ip => '10.10.10.12', :memory => 1024, :cpu => 1}
  ]

  cluster.each do |vm|
    config.vm.define vm[:name] do |vmconfig|
      vmconfig.vm.hostname = vm[:name]
      vmconfig.vm.network :private_network, ip: vm[:ip]
      vmconfig.vm.provider "virtualbox" do |vb|
        vb.name   = vm[:name]
        vb.memory = vm[:memory]
        vb.cpus   = vm[:cpu]
      end
    end
  end
end
