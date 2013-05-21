Vagrant::Config.run do |config|
  config.vm.box = "lucid32"

  #config.vm.share_folder "phantomjs", "/home/vagrant/phantomjs", "../phantomjs", :nfs=>true
  config.vm.share_folder "build", "/home/vagrant/build", "build", :nfs=>true
  config.vm.network :hostonly, "10.11.12.13"

  # Enable and configure the chef solo provisioner
  config.vm.provision :chef_solo do |chef|
    chef.cookbooks_path = "cookbooks"
    chef.add_recipe "apt"
    chef.add_recipe "git"
    chef.add_recipe "build-essential"
    chef.add_recipe "openssl"
  end
end
