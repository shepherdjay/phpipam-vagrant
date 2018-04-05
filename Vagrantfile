Vagrant.configure("2") do |config|
  config.vm.box_download_insecure = true
  config.vm.box = "dharmab/centos7"

  # Forward port 80 to localhost
  config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Setup Yum
  config.vm.provision "shell", inline: "yum -y update"

  # Provision Vagrant Using Ansible
  config.vm.provision "ansible_local", run: "always" do |ansible|
    ansible.playbook = "ansible/playbook.yml"
    ansible.config_file = "ansible/ansible.cfg"
    ansible.become = true
    verbose = true
  end
end