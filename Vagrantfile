# Vagrantfile para configurar un servidor web Apache
Vagrant.configure("2") do |config|
    # Definir la máquina virtual
    config.vm.box = "ubuntu/bionic64" # Puedes usar cualquier versión de Ubuntu o Debian compatible
    config.vm.network "private_network", type: "dhcp"
    config.vm.provider "virtualbox" do |vb|
      vb.memory = "512"
      vb.cpus = 1
    end
  
    # Configurar la sincronización de carpetas
    config.vm.synced_folder "./web_pages", "/var/www/html"
  
    # Instalar Apache en el arranque
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
      systemctl enable apache2
      systemctl start apache2
    SHELL
  end
  