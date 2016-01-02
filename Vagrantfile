# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Standard minimal Ubuntu box
  config.vm.box = "ubuntu/trusty64"
  config.vm.box_url = "https://github.com/kraksoft/vagrant-box-ubuntu/releases/download/14.04/ubuntu-14.04-amd64.box"

  # Port 9000 is where grunt server is doing serving from
  config.vm.network :forwarded_port, guest: 9000, host: 9000
  # Port 35729 is required by LiveReload to reflect content changes
  config.vm.network :forwarded_port, guest: 35729, host: 35729

  # projects folder next to this Vagrantfile will be shared with the VM
  config.vm.synced_folder "projects", "/home/vagrant/projects"

  # Configure everything else ready to run Yeoman
  config.vm.provision "shell", path: "provision.sh"

end
