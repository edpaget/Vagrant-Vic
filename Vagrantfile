# -*- mode: ruby -*-
# vi: set ft=ruby :

GH_USER = ""
GH_PASSWORD = ""

provision = <<BASH
apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
echo 'deb http://downloads-distro.mongodb.org/repo/ubuntu-upstart dist 10gen' | tee /etc/apt/sources.list.d/mongodb.list
apt-get update
apt-get install -y python-pip python-dev build-essential libatlas-base-dev gfortran python-numpy mongodb-org git-core
mongorestore --db asteroid --drop /vagrant/asteroid_zoo_data
pip install git+https://#{GH_USER}:#{GH_PASSWORD}@github.com/edpaget/vic.git
BASH


if GH_USER.empty?
  p "Please set Github username"
  exit(1)
end

if GH_PASSWORD.empty?
  p "Please set Github Password"
  exit(1)
end

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.hostname = "reduction"

  config.vm.box = "opscode_ubuntu-13.10"
  config.vm.box_url = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-13.10_chef-provisionerless.box"

  config.vm.provision "shell", inline: provision

end
