## Asteroid Reduction VM

A Vagrant + Virtual Box system for provisioning a VM to run the Asteroid Zoo reduction scripts. 

### Requirements

* [Vagrant 1.4.0+](http://vagrantup.com)
* [VirtualBox 4.3.0+](https://www.virtualbox.org/)

### Usage
Set the `GH_USER` and `GH_PASS` variables corresponding to your Github Username and Password by editing the Vagrantfile.

* `git clone https://github.com/edpaget/Vagrant-Vic`
* `cd vagrant-asteroid`
* Add the Asteroid Zoo database dump in a folder called "asteroid_zoo_data"
* `vagrant up`
* `vagrant ssh`
* `vic-run.py -h`
