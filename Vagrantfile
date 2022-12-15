# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "monitoring" do |monitoring|
    monitoring.vm.box = "bento/centos-7.5"
    monitoring.vm.hostname = "monitoring"
    monitoring.vbguest.auto_update = false
    monitoring.vm.network "private_network", ip: "192.168.57.100"
  end
  config.vm.define "node_exporter" do |node_exporter|
    node_exporter.vm.box = "bento/centos-7.5"
    node_exporter.vm.hostname = "node-exporter"
    node_exporter.vbguest.auto_update = false
    node_exporter.vm.network "private_network", ip: "192.168.57.101"
  end
  config.vm.define "elastic" do |elastic|
    elastic.disksize.size = '16GB'
    elastic.vm.box = "bento/centos-7.5"
    elastic.vm.hostname = "elastic"
    elastic.vbguest.auto_update = false
    elastic.vm.network "private_network", ip: "192.168.57.102"
    elastic.vm.provider "virtualbox" do |v|
      v.memory = 2048
    end
  end
end