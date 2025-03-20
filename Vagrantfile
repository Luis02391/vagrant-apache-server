Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    
    config.vm.network "private_network", ip: "192.168.56.10"
    
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  # 512MB de RAM
      vb.cpus = 1        # 1 CPU
    end
  
    config.vm.synced_folder "./webpages", "/var/www/html"
  
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo systemctl enable apache2
      sudo systemctl start apache2
    SHELL
  end
  