# -*- mode:ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "testvm" do |testvm|
    testvm.vm.box = "ubuntu/trusty64"
#    testvm.vm.box = "ansible"
 #   testvm.vm.box_url = "https://github.com/holms/vagrant-centos7-box/releases/download/7.1.1503.001/CentOS-7.1.1503-x86_64-netboot.box"
    testvm.vm.network :private_network, ip: "192.168.33.21"

    testvm.vm.provision :ansible do |ansible|
      ansible.playbook = "webserver_php.yml"
      ansible.verbose = "vvv"
    end
  end

  config.vm.provider :virtualbox do |v|
    v.customize ["modifyvm", :id ,"--memory", "1024"]
  end
end
