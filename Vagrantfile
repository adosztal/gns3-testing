if Vagrant::VERSION < "2.0.0"
  $stderr.puts "Please use at least Vagrant 2.0.0"
  abort
end

GNS3_VERSION = "2.2.0a4"

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.box_check_update = true

  config.vm.define "gns3-testing-server" do |server|
    server.vm.provider "virtualbox" do |vb|
	     vb.customize ["modifyvm", :id, "--cpus", "2"]
       vb.name = "gns3-testing-server"
       vb.memory = 2048
    end
    server.vm.hostname = "gns3-testing-server.local"
    server.vm.network :private_network, ip: "172.19.139.10"
    server.vm.provision :shell, path: "deploy-gns3-server.sh"
  end

  config.vm.define "gns3-testing-client" do |client|
    client.vm.provider "virtualbox" do |vb|
	     vb.customize ["modifyvm", :id, "--cpus", "2"]
       vb.name = "gns3-testing-client"
       vb.memory = 2048
       vb.gui = true
    end
    client.vm.hostname = "gns3-testing-client.local"
    client.vm.network :private_network, ip: "172.19.139.11"
    client.vm.provision :shell, path: "deploy-gns3-client.sh"
  end

end
