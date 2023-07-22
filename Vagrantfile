# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANT_API_VERSION = "2"
VAGRANT_VIRTUAL_BOX = "ubuntu/bionic64"

$apt_update = <<APT_UPDATE_ENDSCRIPT
sudo apt-get update --yes
sudo apt-get upgrade --yes
APT_UPDATE_ENDSCRIPT

$install_docker = <<INSTALL_DOCKER_ENDSCRIPT
sudo apt-get install ca-certificates curl gnupg lsb-release --yes
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update --yes
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-compose --yes
sudo apt-get install gnupg2 pass --yes
sudo usermod -a -G docker vagrant
INSTALL_DOCKER_ENDSCRIPT

Vagrant.configure(VAGRANT_API_VERSION) do |config|
  config.vm.box = VAGRANT_VIRTUAL_BOX
  config.vm.provider "virtualbox" do |vbox|
    vbox.memory = 4096
  end
  config.vm.provision "shell", inline: $apt_update
  config.vm.provision "shell", inline: $install_docker
  config.vm.network "forwarded_port", guest: 5432, host:5432
  config.vm.network "forwarded_port", guest: 8000, host:8000
  config.vm.network "forwarded_port", guest: 8443, host:8443
  config.vm.network "forwarded_port", guest: 80, host:80
  config.vm.network "forwarded_port", guest: 8001, host:8001
  config.vm.network "forwarded_port", guest: 1337, host:1337
  config.vm.network "forwarded_port", guest: 9001, host:9001
  config.vm.network "forwarded_port", guest: 9002, host:9002
  config.vm.network "forwarded_port", guest: 9003, host:9003
  config.vm.network "forwarded_port", guest: 9004, host:9004
  config.vm.network "forwarded_port", guest: 9411, host:9411
  config.vm.network "forwarded_port", guest: 9200, host:9200
  config.vm.network "forwarded_port", guest: 9600, host:9600
  config.vm.network "forwarded_port", guest: 5555, host:5555
  config.vm.network "forwarded_port", guest: 5601, host:5601
end