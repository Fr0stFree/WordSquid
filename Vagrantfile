Vagrant.configure("2") do |config|
    config.vm.define "web" do |web|
        web.vm.box = "net9/ubuntu-24.04-arm64"
        
        web.vm.synced_folder "html", "/var/www/html"
        
        web.vm.network "public_network", ip: "192.168.0.15"
        web.vm.network "forwarded_port", guest: 22, host: 2220, id: "ssh"

        # provider
        web.vm.provider "virtualbox" do |vb|
            vb.name = "web"
            vb.memory = "1024"
            vb.cpus = 2
        end
    end
end