Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/focal64"

  config.vm.provider "virtualbox" do |vb|
    vb.name = "Drone Runner Box"
    vb.memory = "8192"
    vb.cpus = 4
  end
  
  config.vm.provision "file", source: "pass.txt", destination: "/tmp/vault_password"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.vault_password_file = "/tmp/vault_password"
  end
  
end
