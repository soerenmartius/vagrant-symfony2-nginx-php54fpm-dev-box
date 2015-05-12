# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "precise64"

  config.vm.network "private_network", ip: "192.168.50.5"

  config.vm.network "forwarded_port", guest: 80, host: 1337
  config.vm.network "forwarded_port", guest: 3306, host: 3306
  config.vm.network "forwarded_port", guest: 27017, host: 27017

  config.vm.provision :puppet do |puppet|
    puppet.manifests_path = "puppet/manifests"
    puppet.manifest_file  = "precise64.pp"
    puppet.module_path = "puppet/modules"
    puppet.options = ['--verbose']
   end

  config.vm.synced_folder ".", "/vagrant",
    :nfs => true,
    :mount_options => ['actimeo=2']

end
