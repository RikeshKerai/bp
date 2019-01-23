# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "vbu" do |vbu|
    vbu.vm.box = "bento/ubuntu-18.04"
    vbu.vm.network "private_network", ip: "192.168.10.10"
    vbu.vm.box_check_update = false
    vbu.vm.network "forwarded_port", guest: 8080, host: 8888
    vbu.vm.synced_folder ".", "/vbu_mac"
    vbu.vm.provider "virtualbox" do |vb|
       vb.customize ["modifyvm", :id, "--name", "vbu-test1"]
       vb.memory = "1024"
    end
    vbu.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update -y
      sudo apt-get install software-properties-common -y
      sudo apt-add-repository --yes ppa:ansible/ansible -y
      sudo apt-get install ansible -y
      cd /vbu_mac
      ansible-playbook playbook.yml
    SHELL
  end
end
