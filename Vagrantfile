# -*- mode: ruby -*-
ENV['VAGRANT_SERVER_URL'] = 'https://vagrant.elab.pro'

Vagrant.configure("2") do |config|

    N = 2
    (1..N).each do |i|
      config.vm.define "host#{i}" do |node|
        node.vm.box = "ubuntu/focal64"
        node.vbguest.installer_options = { allow_kernel_upgrade: true }
        node.vm.synced_folder ".", "/vagrant"
        #node.vm.synced_folder ".", "/vagrant", disabled: true
        node.vm.hostname = "host#{i}"
        node.vm.network "private_network", ip:"10.0.26.1#{i}"
        node.vm.provider "virtualbox" do |vb|
          vb.memory = "1024"
          vb.name = "host#{i}"
          vb.cpus = 2
        end
      end
    end
 
end