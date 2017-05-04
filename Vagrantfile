# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|
  config.vm.box = 'ubuntu/xenial64'

  config.vm.define 'node' do |node|
    node.vm.host_name = 'localhost'
  end

  config.vm.provision 'shell', type: 'shell',
    inline: 'apt-get -yq install python'

  config.vm.provision 'ansible' do |ansible|
    ansible.sudo = true
    ansible.playbook = 'tests/test.yml'
    ansible.host_key_checking = false
    ansible.verbose = 'v'
  end

end # end Vagrant.configure
