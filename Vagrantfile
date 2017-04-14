# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.synced_folder ".", "/vagrant-src"
  (1..3).each do |i|
    config.vm.define "elastic-0#{i}" do |d|
      d.vm.box = "ubuntu/xenial-cloud"
      d.vm.box_url = "https://cloud-images.ubuntu.com/xenial/20170311/xenial-server-cloudimg-amd64-vagrant.box"
      d.vm.hostname = "elastic-node-0#{i}"
      d.vm.network "private_network", ip: "10.100.100.10#{i}"
      d.vm.provision :shell, path: "vagrant-provision.sh"
      d.vm.provision :shell, inline: "PYTHONUNBUFFERED=1 ansible-playbook /vagrant-src/ansible/elastic.yml -c local"
      d.vm.provider "virtualbox" do |v|
        v.memory = 3072
      end
    end
  end
end
