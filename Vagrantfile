# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  config.vm.define "jenkinscontroller" do |controller|
    controller.vm.box = "generic/ubuntu2004"
    controller.vm.network "private_network", ip: "192.168.33.11"
    controller.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y openjdk-11-jre
        wget -q -O - https://pkg.jenkins.io/debian-stable/jenkins.io.key | sudo apt-key add -
        sh -c 'echo deb https://pkg.jenkins.io/debian-stable binary/ > \
            /etc/apt/sources.list.d/jenkins.list'
        apt-get update
        apt-get install -y jenkins
      SHELL
  end

  config.vm.define "jenkinsagentssh" do |agentssh|
    agentssh.vm.box = "generic/ubuntu2004"
    agentssh.vm.network "private_network", ip: "192.168.33.12"
    agentssh.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y openjdk-11-jre
      SHELL
  end

  config.vm.define "jenkinsagentdocker" do |agentdocker|
    agentdocker.vm.box = "generic/ubuntu2004"
    agentdocker.vm.network "private_network", ip: "192.168.33.13"
    agentdocker.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y openjdk-11-jre
      SHELL
  end

end
