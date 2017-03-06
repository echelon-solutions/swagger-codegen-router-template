# Isolated build environment configuration for the project
#
# Why? To enable repeatable builds, whether you are on your machine,
#   someone else's machine, or you are running from a build box.
#
# For more information:
#   https://www.vagrantup.com/
#   https://docs.vagrantup.com/
#
# Author: Khalid Zoabi [khalid@echelon.solutions]

Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/precise64"
  config.vm.box_version = "1.1.0"

  config.vm.hostname = "java-maven-build-environment"  
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "256"
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    echo "Installing Java 8 ..."
    sudo apt-get install -y software-properties-common python-software-properties
    echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | sudo /usr/bin/debconf-set-selections
    sudo add-apt-repository ppa:webupd8team/java -y
    sudo apt-get update
    sudo apt-get install oracle-java8-installer
    echo "Setting environment variables for Java 8 ..."
    sudo apt-get install -y oracle-java8-set-default
    echo "Installing Maven ..."
    sudo apt-get install -y maven
  SHELL

end
