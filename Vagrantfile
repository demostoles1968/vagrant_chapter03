# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	config.vm.define "web", primary: true do |web|
  	web.vm.box = "puppetlabs/ubuntu-14.04-64-nocm"
		web.vm.network "public_network", ip: "192.168.1.100"
		web.vm.synced_folder "vagrantsite", "/opt/vagrantsite"
		web.vm.synced_folder "html", "/opt/html", type: "rsync"
		web.vm.provision "shell", inline: <<-SHELL
			apt-get update
			apt-get install -y nginx
			ln -s /opt/vagrantsite /usr/share/nginx/html/vagrantsite
		SHELL
	end	
end
