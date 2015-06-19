ip_address = "192.168.10.10"
project_name = "BaseVagrantBox"

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/utopic32"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/utopic/current/utopic-server-cloudimg-i386-vagrant-disk1.box"
  config.vm.box_check_update = true

  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.vm.define project_name do |node|
    node.vm.hostname = project_name + ".local"
    node.vm.network :private_network, ip: ip_address
    node.hostmanager.aliases = [ project_name + ".local", "www." + project_name + ".local" ]
  end

  config.vm.synced_folder "Data/", "/Data"
  config.vm.provision :shell, :path => "updateOS.sh"

end
