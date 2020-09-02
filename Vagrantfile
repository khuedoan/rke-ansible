# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"

  config.vm.define "master" do |master|
    master.vm.network "private_network", ip: "192.168.56.101"
  end

  (1..2).each do |i|
    config.vm.define "worker-#{i}" do |worker|
      worker.vm.network "private_network", ip: "192.168.56.10#{i+1}"
    end
  end

  config.vm.provider "virtualbox" do |vb|
    vb.cpus   = 2
    vb.memory = 2048
  end

  config.vm.provision "file",
    source: "~/.ssh/id_rsa.pub",
    destination: "~/.ssh/host.pub"
  config.vm.provision "shell",
    inline: "cat /home/vagrant/.ssh/host.pub >> /home/vagrant/.ssh/authorized_keys"
end
