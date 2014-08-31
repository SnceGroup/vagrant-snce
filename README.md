#Vagrant S'nce

Vagrant file plus Ansible for S'nce development (Symfony and eZ Publish 5 ready)

##Requirements
* Virtual Box installed (tested with version 4.3.14)
* Vagrant installed (tested with version 1.6.2)
* Ansible installed (tested with version 1.7)

##Configuration

###config.vm.box_url
* Add the correct password (You should know it if you are an S'nce employees)

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
4. Install a plugin to fix a network issue on CentOS 7 ```vagrant plugin install vagrant-centos7_fix```
5. ``` vagant up ```
6. Done

##Tips
[Force cache and logs generation in non shared folders](https://gist.github.com/gabriperego/8239581)

##Installed software
* Wget
* Vim
* cURL
* Telnet
* PIP
* Boto
* Zip
* Unzip
* Apache 2.2.*
* PHP 5.4.*
  * php-cli
  * php-gd
  * php-mbstring
  * php-pdo
  * php-pecl-apc
  * php-xml
  * php-curl
  * php-imagick
  * php-intl
  * php-memcache
  * php-mcrypt
  * php-mhash
  * php-mysqlnd
  * php-xsl
  * php-pecl-ssh2
* Composer
* MySQL 5.6.* -> root password: `root`
* Git 1.8.*
* SASS 3.4.*
* Compass 1.*
* ImageMagick
* Memcached