# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.define "box1" do |box1|
    box1.vm.network "forwarded_port", guest: 8080, host: 8001
    box1.vm.network "forwarded_port", guest: 22, host: 22001, id: 'ssh'
    box1.vm.host_name = "nginx-01"
  end
  config.vm.define "box2" do |box2|
    box2.vm.network "forwarded_port", guest: 8080, host: 8002
    box2.vm.network "forwarded_port", guest: 22, host: 22002, id: 'ssh'
    box2.vm.host_name = "nginx-02"
  end
end
