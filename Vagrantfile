# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.ssh.forward_agent = true

  # config.vm.provider "vmware_fusion" do |v|
  #   v.vmx["memsize"] = "1024"
  #   v.vmx["numvcpus"] = "1"
  # end

  # config.vm.provider "parallels" do |v|
  #   v.vmx["memsize"] = "1024"
  #   v.vmx["numvcpus"] = "1"
  # end

  # config.vm.provider "virtualbox" do |v|
  #   v.vmx["memsize"] = "1024"
  #   v.vmx["numvcpus"] = "1"
  # end

  config.vm.define "web" do |web|
    web.vm.box = "hashicorp/precise64"
    web.vm.network "private_network", ip: "192.168.12.10"
    web.vm.synced_folder ".", "/opt/projects/projectname" # change folder path

    web.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/main.yml"
      ansible.inventory_path = "ansible/dev-hosts.ini"
      ansible.limit = 'web'

    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "hashicorp/precise64"
    db.vm.network "private_network", ip: "192.168.12.11"
    db.vm.hostname = '192.168.12.11'

    db.vm.provision "ansible" do |ansible|
      ansible.playbook = "ansible/main.yml"
      ansible.inventory_path = "ansible/dev-hosts.ini"
      ansible.limit = 'db'
    end
  end

end
