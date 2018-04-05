Vagrant.configure("2") do |config|
  config.vm.box_download_insecure = true
  config.vm.box = "dharmab/centos7"

  config.vm.define 'master' do |master|
    master.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
    master.vm.provision "ansible_local", run: "always" do |ansible|
        ansible.playbook = "ansible/master_playbook.yml"
        ansible.config_file = "ansible/ansible.cfg"
        ansible.become = true
        verbose = true
    end
  end

  config.vm.define 'stable', autostart: false do |stable|
    stable.vm.network "forwarded_port", guest: 80, host: 8081, host_ip: "127.0.0.1"
    stable.vm.provision "ansible_local", run: "always" do |ansible|
        ansible.playbook = "ansible/stable_playbook.yml"
        ansible.config_file = "ansible/ansible.cfg"
        ansible.become = true
        verbose = true
    end
  end

  # Setup Yum
  config.vm.provision "shell", inline: "yum -y update"

end