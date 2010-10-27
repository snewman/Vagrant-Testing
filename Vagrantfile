Vagrant::Config.run do |config|
  config.vm.box = "lucid32"

  config.vm.provisioner = :chef_solo

  config.chef.cookbooks_path = "cookbooks"

  config.chef.add_recipe("vagrant_main")

  config.vm.define :web1 do |web_config|
    web_config.vm.forward_port("http", 80, 8080)
  end
   
  # config.vm.define :web2 do |web_config|
  #   web_config.vm.forward_port("http", 81, 8081)
  # end
  # 
  # config.vm.define :web3 do |web_config|
  #   web_config.vm.forward_port("http", 82, 8082)
  # end
  # 
  config.vm.define :db do |db_config|
    db_config.vm.forward_port("db", 3306, 3306)
    db_config.vm.forward_port("http", 80, 8082)
  end
end
