#Vagrant S'nce

Vagrant file plus Ansible for S'nce development (Symfony and eZ Publish 5 ready)

##Requirements
* Virtual Box installed (tested with version 5.1.12)
* Vagrant installed (tested with version 1.8.6, in vagrant 1.9.1 config.vm.network "private_network" doesn't work, in vagrant 1.8.7 the download box doesn't work)
* Plugin Vagrant-VBox (tested with version 0.13.0, install with command "vagrant plugin install vagrant-vbguest")
* Ansible installed (tested with version 2.2.1.0)

##Configuration

###config.vm.network 
* Update the IP with a proper one
* Update the vagrant/ansible/hosts file with the vagrant configured IP

###virtualbox.customize ["modifyvm", :id, "--name", "SNCE"]
* Add the correct VM name instead of the SNCE placeholder
* Modify accordingly the vagrant/ansible/vars/apache.yml file (name)

###config.vm.hostname
* Replace the placeholder with the correct hostname
* Modify accordingly the vagrant/ansible/vars/apache.yml file (server_name)

##Usage

1. Copy the files inside your development directory
2. Be sure that all the configurations placeholder are replaced and correct
3. Update you /etc/hosts file accordingly to the ```config.vm.hostname``` and ```config.vm.network``` vagrant parameters
4. ``` vagrant up ```
5. Done

##Tips
[Force cache and logs generation in non shared folders](https://gist.github.com/gabriperego/8239581)

##Installed software
* Apache 2.4.*
* Boto
* Bower 1.3.*
* Composer
* cURL
* Foundation CLI 1.*
* Git 1.8.*
* Grunt CLI 0.1.*
* ImageMagick
* Memcached
* MySQL 5.6.* -> root password: `root`
* Node.js 0.10.*
* npm 1.3.*
* PHP 5.6.*
  * php-cli
  * php-curl
  * php-gd
  * php-imagick
  * php-intl
  * php-mbstring
  * php-mcrypt
  * php-memcache
  * php-mhash
  * php-mysqlnd
  * php-opcache
  * php-pdo
  * php-pecl-apc
  * php-pecl-ssh2
  * php-xml
  * php-xsl
* PIP
* Ruby 2.*
* SASS 3.4.*
* Telnet
* Vim
* Wget
* NetTools
* Zip
