# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant_box = 'ubuntu/xenial64'
host_name = 'dockhost'
CPU_NO = '1'
RAM_MB = '2048'

Vagrant.configure("2") do |config|
  config.vm.box = Vagrant_box
  config.vm.hostname = host_name
  config.vm.provider "virtualbox" do |test|
    test.name = host_name
    test.memory = RAM_MB
    test.cpus = CPU_NO
  end
  config.vm.network "private_network", ip: "172.16.0.100", netmask: "255.255.255.0"
#  config.vm.provision "shell", path: "~/GIT/vagrant/provision/script01.sh"
  config.vm.provision "ansible_local" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "playbook.yml"
  end
end
