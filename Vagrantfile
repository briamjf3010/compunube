# -*- mode: ruby -*-
# vi: set ft=ruby : 

Vagrant.configure("2") do |config|
  # Configuración del balanceador de carga
  config.vm.define "haproxy" do |haproxy|
    haproxy.vm.box = "ubuntu/bionic64"
    haproxy.vm.network "private_network", ip: "192.168.56.10"
    haproxy.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y haproxy consul
    SHELL
  end

  # Configuración del servidor web 1
  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/bionic64"
    web1.vm.network "private_network", ip: "192.168.56.11"
    web1.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y nodejs npm consul
      npm install express
    SHELL
  end

  # Configuración del servidor web 2
  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/bionic64"
    web2.vm.network "private_network", ip: "192.168.56.12"
    web2.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y nodejs npm consul
      npm install express
    SHELL
  end
end