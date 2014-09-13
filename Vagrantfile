# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.omnibus.chef_version = :latest
  config.berkshelf.enabled = true

  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 2375, host: 2375
  config.vm.network "forwarded_port", guest: 5000, host: 5000

  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = ["cookbooks", "site-cookbooks"]
    chef.roles_path = "roles"
    chef.environments_path = "environments"
    chef.data_bags_path = "data_bags"
    chef.add_role "default"
  end
end
