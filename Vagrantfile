# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # set to false, if you do NOT want to check the correct VirtualBox Guest Additions version when booting this box
  if defined?(VagrantVbguest::Middleware)
    config.vbguest.auto_update = true
  end

  config.vm.box = "centos/7"
#  config.vm.box = "bento/ubuntu-16.04"
#  config.vm.box = "geerlingguy/debian8"

  config.vm.define "danijenkins", primary: true do |danijenkins|
     config.vm.hostname = "danijenkins"
     danijenkins.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
     danijenkins.vm.provider :esxi do |lb|
       lb.memory = 1024
     end
 end
 
  config.vm.provider :vmware_esxi do |esxi, overrider|
    #
    #   Provider settings
    #
    esxi.esxi_hostname = 'ip'
    esxi.esxi_username = 'vagrant'
    esxi.esxi_password = 'passwordd'
    esxi.esxi_virtual_network = 'red'
    esxi.esxi_disk_store = "volumen"
  end
end

