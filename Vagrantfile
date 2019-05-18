# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/xenial64"
  config.vm.box_check_update = false
  config.vm.network "forwarded_port", guest: 5000, host: 80, host_ip: "10.10.10.20"
  config.vm.network "private_network", ip: "10.10.10.20"


   config.vm.provider "virtualbox" do |vb|
     vb.gui = true
     vb.memory = "512"
   end

   $script = <<-SCRIPT
   echo I am provisioning...
   date > /etc/vagrant_provisioned_at
   apt-get update
   apt-get -y install ansible 
   SCRIPT

   config.vm.provision "shell", inline: $script
   config.vm.provision "ansible" do |ansible|
     ansible.playbook = "provision/site.yml"
     ansible.verbose = true
   end
end
