# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.define :master do |node|
    node.vm.box = "bento/ubuntu-18.04"
    node.vm.network :private_network, ip: "10.200.19.10"
  end

  config.vm.define :slave_bind do |node|
    node.vm.box = "bento/ubuntu-18.04"
    node.vm.network :private_network, ip: "10.200.19.11"
  end

  config.vm.define :slave_nsd do |node|
    node.vm.box = "bento/ubuntu-18.04"
    node.vm.network :private_network, ip: "10.200.19.12"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.extra_vars = "inventories/development/group_vars/all"
    ansible.verbose = "v"
    ansible.groups = {
      "master" => ["master"],
      "slave-bind" => ["slave_bind"],
      "slave-nsd" => ["slave_nsd"]
    }
  end
end
