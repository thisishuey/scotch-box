# -*- mode: ruby -*-
# vi: set ft=ruby :

$installIntl = <<SCRIPT
	apt-get update
	apt-get -y install php5-intl
	apt-get -y autoremove
	service apache2 restart
SCRIPT

Vagrant.configure("2") do |config|

	config.vm.box = "scotch/box"
	config.vm.provision :shell, inline: $installIntl
	config.vm.network "private_network", ip: "192.168.48.39"
	config.vm.hostname = "scotchbox"
	config.vm.synced_folder ".", "/var/www/public", :mount_options => ["dmode=777", "fmode=666"]

end
