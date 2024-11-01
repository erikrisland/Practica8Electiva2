Vagrant.configure("2") do |config|
 
    config.vm.box = "ubuntu/bionic64"
  
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  
    config.vm.hostname = "apache-server"

    config.vm.network "private_network", ip: "192.168.33.10"

    config.vm.synced_folder "./html", "/var/www/html"
  
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo systemctl enable apache2
      sudo systemctl start apache2
    SHELL
  end