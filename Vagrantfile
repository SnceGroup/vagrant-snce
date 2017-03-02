Vagrant.configure("2") do |config|
  config.vm.box = "centos7-x64-vbox"
  config.vm.box_url = "https://www.dropbox.com/s/l78vy3tja5edduw/CentOS-7-x86_64-Vagrant-1611_02.VirtualBox.box?dl=1"

  config.vm.network "private_network", ip: "192.168.3.23", auto_config: true
  config.vm.network :forwarded_port, guest: 80, host: 2000

  config.vm.synced_folder "./", "/var/www/html", id: "vagrant-root", :nfs => true
  config.vm.synced_folder "./", "/vagrant", id: "vagrant-root-default", :nfs => true

  config.vm.usable_port_range = (2200..2250)
  config.vm.provider :virtualbox do |virtualbox|
    virtualbox.customize ["modifyvm", :id, "--name", "SNCE"]
    virtualbox.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    virtualbox.customize ["modifyvm", :id, "--memory", "1024"]
    virtualbox.customize ["setextradata", :id, "--VBoxInternal2/SharedFoldersEnableSymlinksCreate/v-root", "1"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "vagrant/ansible/playbook.yml"
  end

  config.vm.hostname = "snce.local"

  config.ssh.username = "vagrant"

  config.ssh.shell = "bash -l"

  config.ssh.keep_alive = true
  config.ssh.forward_agent = false
  config.ssh.forward_x11 = false
  config.vagrant.host = :detect
end
