LAMPapp Vagrant
===============

Vagrant setup that runs your local project on LAMP server with minimal config.

Your project is available on 192.168.56.101 IP (*.vagrant.dev alias)
and you can connect to MySQL remotely using the same IP as root:foobar


This is an example for LAMPapp Vagrant Chef cookbook:

  https://github.com/mbman/lampapp

REQUIREMENTS
============

  http://www.vagrantup.com/

NFS share is activated by default for better performance and must me installed on host machine (windows not supported).

Chef cookbook dependencies are included as git submodules and need to be initialized.

SETUP
=====

  - Clone, fork or unzip this repo into your project ("vagrant" for instance)
  - Initialize all cookbook submodules
  - Set "config.vm.synced_folder" Vagrantfile value to your web root directory path
  - Set "config.lampapp.path" to your public dir path relative to web root
  - Run "vagrant up" from the same directory Vagrantfile is located in

Your project is now running on a LAMP server and can be access using
the static IP address, with or without SSL:
    
  - http://192.168.56.101 
  - https://192.168.56.101 