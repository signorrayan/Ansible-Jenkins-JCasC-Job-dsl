Vagrant.configure(2) do |config|
  config.vm.box = "bento/centos-7.9"

  config.vm.define "jenkins" do |jenkins|
    jenkins.vm.network "private_network", ip: "192.168.56.13"
    jenkins.vm.hostname = "jenkins"
    jenkins.vm.provider "jenkins" do |vb|
      vb.cpus = 1
      vb.memory = 1024
    end
  end

  config.vm.define "agent1" do |agent1|
    agent1.vm.network "private_network", ip: "192.168.56.15"
    agent1.vm.hostname = "agent1"
    agent1.vm.provider "agent1" do |vb|
      vb.cpus = 1
      vb.memory = 1024
    end
  end
end
