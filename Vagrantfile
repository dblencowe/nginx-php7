# vi: ft=ruby

require 'rbconfig'

ROLE_NAME = 'nginx-php7'
HOST_NAME = 'test-' + ROLE_NAME
VAGRANTFILE_API_VERSION = '2'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = 'centos/7'

  config.vm.define HOST_NAME do |node|
    node.vm.hostname = HOST_NAME
    node.vm.network :forwarded_port,  guest: 80, host: 8080
    node.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'test.yml'
    end
  end
end

