# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "boxcutter/ubuntu1604-desktop"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "provision.yml"
    ansible.inventory_path = 'hosts'
    ansible.limit          = 'all' # can also be limited to 'node' from inventory
    ansible.verbose        = true
    ansible.install        = true
  end

  config.vm.provider "virtualbox" do |vb|
    vb.gui = true
    vb.cpus = 2
    vb.memory = "4096"
  end


end
