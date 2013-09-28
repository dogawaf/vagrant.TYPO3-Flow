Vagrant.configure("2") do |config|

	config.vm.box = "quantal"

	config.vm.box_url = "https://github.com/downloads/roderik/VagrantQuantal64Box/quantal64.box"

	config.vm.network "private_network", ip: "192.168.23.3"

	#config.ssh.forward_agent = true

	config.vm.synced_folder ".", "/vagrant", nfs: true

	config.vm.provider "virtualbox" do |v|
		v.customize ["modifyvm", :id, "--memory", "2048"]
	end

	config.vm.provision "chef_solo" do |chef|
		chef.cookbooks_path = ["cookbooks", "site-cookbooks"]

		#chef.log_level = :debug

		chef.add_recipe "typo3-flow"
	end

end