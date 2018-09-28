# read vm nodes.json and params configurations files
nodes_config = (JSON.parse(File.read("nodes.json")))['nodes']

VAGRANTFILE_API_VERSION = "2"
 
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  #For each node
  nodes_config.each do |node|
    # get node name
    node_name   = node[0] 
    # get entry parameters
    node_values = node[1] 
    # configure node
    config.vm.define node_name do |config|
      config.vm.box = node_values[':box'] # Set VM OS
      config.vm.hostname = node_name
      config.vm.network :private_network, ip: node_values[':ip']
      config.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", node_values[':memory']]
        vb.customize ["modifyvm", :id, "--name", node_name]
      end
      config.vm.provision :shell, :path => node_values[':bootstrap']
    end
  end
  # set /vagrant directory access rights to 777 
  # useful if you need shared resources between the different nodes and/or your physical machine
  config.vm.synced_folder ".", "/vagrant",  :mount_options => ["dmode=777,fmode=777"] 
end

