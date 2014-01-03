#Vagrant S'nce

Vagrant file plus Puppet and shell provisionings for S'nce development (Symfony and eZ Publish 5 ready)

##Prerequisites
* Virtual Box installed (tested with version 4.3.2)
* Vagrant installed (tested with version 1.3.5)

##Configuration

###config.vm.box_url
* Add the correct password (You should know it if you are an S'nce employees)

###virtualbox.customize ["modifyvm", :id, "--name", "SNCE"]
* Add the correct VM name instead of the SNCE placeholder
* Modify accordingly the vagrant/puppet/hieradata/common.yaml file (provider.virtualbox.modifyvm.name)

###config.vm.hostname
* Replace the placeholder with the correct hostname
* Modify accordingly the vagrant/puppet/hieradata/common.yaml file (apache.vhosts.It98D0P4J49p.servername)

##Usage

1. Copy the files inside your development directory
2. Be sure that all the configurations placeholder are replaced and correct
3. Update you /etc/hosts file accordingly to the ```config.vm.hostname``` and ```config.vm.network``` vagrant parameters
3. Due to a [CentOS issue](https://github.com/puphpet/puphpet/issues/250) you must keep disabled NFS the first time
4. ``` vagant up ```
5. After the setup run ``` vagant halt ```
6. Change config.vm.synced_folder :nfs to true
7. ``` vagant up ```
8. Done

##Tips
[Force cache and logs generation in non shared folders](https://gist.github.com/gabriperego/8239581) 
