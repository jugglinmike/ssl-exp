# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "base"
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "private_network", ip: "192.168.101.101"

  # Enable provisioning with a shell script. Additional provisioners such as
  # Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
  # documentation for more information about their specific syntax and use.
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y nginx
    sudo ln -s /vagrant/src/server.key /etc/nginx
    sudo ln -s /vagrant/src/server.crt /etc/nginx
    sudo ln -s /vagrant/src/nginx.conf /etc/nginx/sites-enabled/ssl-exp.local
    /etc/init.d/nginx restart
  SHELL
end
