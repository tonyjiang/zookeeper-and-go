# Vagrant.configure("2") do |config|
#   config.vm.box = "hashicorp/precise64"
#   config.vm.network :forwarded_port, host: 2181, guest: 2181
#   config.vm.provision :shell, :path => "zookeeper-singleton.sh"
# end

Vagrant::Config.run do |config|
  config.vm.define :zk1 do |zk1_config|
    zk1_config.vm.box = "hashicorp/precise64"
    zk1_config.vm.network :hostonly, "192.168.12.10"
    zk1_config.vm.provision :shell, :path => "zookeeper-member.sh", :args => "1"
  end

  config.vm.define :zk2 do |zk2_config|
    zk2_config.vm.box = "hashicorp/precise64"
    zk2_config.vm.network :hostonly, "192.168.12.11"
    zk2_config.vm.provision :shell, :path => "zookeeper-member.sh", :args => "2"
  end

  config.vm.define :zk3 do |zk3_config|
    zk3_config.vm.box = "hashicorp/precise64"
    zk3_config.vm.network :hostonly, "192.168.12.12"
    zk3_config.vm.provision :shell, :path => "zookeeper-member.sh", :args => "3"
  end
end
