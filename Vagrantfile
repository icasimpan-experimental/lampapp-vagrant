# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.hostname = "vagrat"
    config.vm.box = "mbman/debian-7"

    config.vm.network :private_network, ip: "192.168.56.101"
    config.ssh.forward_agent = true

    config.vm.synced_folder "./", "/var/www", id: "vagrant-root", :nfs => true

    config.vm.provision "chef_solo" do |chef|
        chef.add_recipe "lampapp"
        chef.cookbooks_path = "cookbooks"

        chef.json.merge!({
            :lampapp => {
                :name => "vagrant",
                :password => "foobar",
                :ip => "192.168.56.101",
                :path => "",
            },
            :php => {
                :directives => {"date.timezone" => "Europe/Zagreb"}
            }
        })
    end
end
