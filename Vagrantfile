Vagrant.configure("2") do |config|
  # Usar la caja base de Ubuntu 22.04
  config.vm.box = "ubuntu/jammy64"

  # Asignar RAM y CPU
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512"
    vb.cpus = 1
  end

  # Configurar red privada
  config.vm.network "private_network", type: "dhcp"

  # Configurar Apache
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y apache2
  SHELL

  # Compartir la carpeta local "paginas_web" con Apache
  config.vm.synced_folder "./paginas_web", "/var/www/html"
end
