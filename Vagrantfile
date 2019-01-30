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

  config.vm.define "testlink", primary: true do |testlink|
     config.vm.hostname = "testlink"
     testlink.ssh.shell = "bash -c 'BASH_ENV=/etc/profile exec bash'"
     testlink.vm.provider :esxi do |lb|
       lb.memory = 1024
     end
 end
 
  config.vm.provider :vmware_esxi do |esxi, overrider|
    #
    #   Provider settings
    #
    esxi.esxi_hostname = 'main-srv1.chakray.local'
    esxi.esxi_username = 'vagrant'
    esxi.esxi_password = 'env:'
    esxi.esxi_virtual_network = 'VM Network'
  end
end

