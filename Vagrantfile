# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant development environment requires a box to build off of.
  config.vm.box_url = "https://atlas.hashicorp.com/unzagi/boxes/ubuntu"
  config.vm.box = "unzagi/ubuntu"
  config.vm.box_version = "0.4.1"
  
    forward_port = ->(guest, host = guest) do
    config.vm.network :forwarded_port,
      guest: guest,
      host: host,
      auto_correct: true
  end
  
  # Sync between the ansible folder in the VM and the 'sites' directory
  config.vm.synced_folder "ansible", "/etc/ansible", mount_options: ["fmode=666"]
  # Sync between the ansible folder in the VM and the 'configs' directory
  config.vm.synced_folder "output", "/etc/ansible/output"

  forward_port[3389,3380] # xrdp (RDP)
 
 config.vm.provider "virtualbox" do |v|
  v.name = "Rancid_Ansible_Lab_Box"
  v.memory = 1024
  v.cpus = 2
end

  # This will Set host only network and should match the gateway router subnet in GNS3
  config.vm.network :private_network, ip: "10.0.1.254"
  
  # Add any static routes here
  # 192.168.4.0/24 is the subnet allocated in GNS3 non-gateway subnets
  config.vm.provision "shell",
    run: "always",
    inline: "route add -net 192.168.4.0 netmask 255.255.255.0 gw 10.0.1.1"
end
