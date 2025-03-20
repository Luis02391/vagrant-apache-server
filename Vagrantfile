Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    
    # Configurar red con IP estática
    config.vm.network "private_network", ip: "192.168.56.10"
    
    # Configurar recursos de la máquina virtual
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"  # 512MB de RAM
      vb.cpus = 1        # 1 CPU
    end
  
    # Sincronizar carpeta local con Apache en la VM
    config.vm.synced_folder "./webpages", "/var/www/html"
  
    # Provisionamiento: instalar y habilitar Apache
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install -y apache2
      sudo systemctl enable apache2
      sudo systemctl start apache2
    SHELL
  end
  