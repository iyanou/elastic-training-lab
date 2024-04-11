Vagrant.configure(2) do |config|
  etcHosts = ""
  config.vm.box = "ubuntu/jammy64"
  config.vm.box_url = "ubuntu/jammy64"
  config.vm.boot_timeout = 6000

  NODES = [
    { :hostname => "HOST01", :ip => "192.168.50.104", :cpus => 2, :mem => 2048},
    { :hostname => "HOST02", :ip => "192.168.50.105", :cpus => 2, :mem => 2048},
    { :hostname => "HOST03", :ip => "192.168.50.106", :cpus => 2, :mem => 2048},
    { :hostname => "HOST04", :ip => "192.168.50.107", :cpus => 4, :mem => 4096}
  ]
  
  # Define /etc/hosts for all servers
  NODES.each do |node|
    etcHosts += "echo '#{node[:ip]}   #{node[:hostname]}' >> /etc/hosts\n"
  end
  
  NODES.each do |node|
    config.vm.define node[:hostname] do |cfg|
      cfg.vm.hostname = node[:hostname]
      cfg.vm.network "private_network", ip: node[:ip]

      cfg.vm.provider "virtualbox" do |v|
        v.customize [ "modifyvm", :id, "--cpus", node[:cpus] ]
        v.customize [ "modifyvm", :id, "--memory", node[:mem] ]
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
        v.customize ["modifyvm", :id, "--name", node[:hostname] ]
      end

      cfg.vm.provision :shell, :inline => etcHosts
    end
  end
end