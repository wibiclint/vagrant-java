# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "vagrant/cookbooks"
    chef.add_recipe "java"
    chef.json = {
      :java =>  {
        'install_flavor' => 'oracle',
        'jdk_version' => '7',
        'oracle' => {
          'accept_oracle_download_terms' => true
        }
      }
    }

  end
end
