# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
  config.vm.box      = 'hashicorp/precise32'

  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.provision :shell, path: 'script/provision', keep_color: true

  if `uname`.include? "Linux"
    config.vm.synced_folder './workspace', '/home/vagrant/workspace', type: 'rsync'
  else
    config.vm.synced_folder './workspace', '/home/vagrant/workspace'
  end
end
