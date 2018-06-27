Vagrant.configure("2") do |config|

  config.vm.define "Ansible" do |ansible|
    ansible.vm.box = "centos/7"

    # Provisioning SSH Keys
    ansible.vm.provision "file",
        source: "./ssh_keys/id_rsa",
        destination: "~/.ssh/id_rsa"

    ansible.vm.synced_folder "./playbooks", "/var/playbooks", type: "nfs"

    ansible.vm.hostname = "Ansible"

    ansible.vm.network "private_network",
        ip: "10.0.0.2",
        virtualbox__intnet: "ansible"

    ansible.vm.provider "virtualbox" do |v|
      v.name = "Ansible"
      v.memory = 512
      v.cpus = 1
    end
  end

  config.vm.define "LoadBalancer" do |lb|
    lb.vm.box = "centos/7"

    # Provisioning SSH Keys
    lb.vm.provision "file",
        source: "./ssh_keys/id_rsa.pub",
        destination: "~/.ssh/authorized_keys"

    lb.vm.hostname = "LoadBalancer"

    lb.vm.network "private_network",
        ip: "10.0.0.3",
        virtualbox__intnet: "ansible"

    lb.vm.provider "virtualbox" do |v|
      v.name = "Load Balancer"
      v.memory = 512
      v.cpus = 1
    end
  end

  config.vm.define "WebServer1" do |web1|
    web1.vm.box = "debian/jessie64"

    # Provisioning SSH Keys
    web1.vm.provision "file",
        source: "./ssh_keys/id_rsa.pub",
        destination: "~/.ssh/authorized_keys"

    web1.vm.hostname = "WebServer1"

    web1.vm.network "private_network",
        ip: "10.0.0.4",
        virtualbox__intnet: "ansible"

    web1.vm.provider "virtualbox" do |v|
      v.name = "Web Server 1"
      v.memory = 512
      v.cpus = 1
    end
  end

  config.vm.define "WebServer2" do |web2|
    web2.vm.box = "centos/7"

    # Provisioning SSH Keys
    web2.vm.provision "file",
        source: "./ssh_keys/id_rsa.pub",
        destination: "~/.ssh/authorized_keys"

    web2.vm.hostname = "WebServer2"

    web2.vm.network "private_network",
        ip: "10.0.0.5",
        virtualbox__intnet: "ansible"

    web2.vm.provider "virtualbox" do |v|
      v.name = "Web Server 2"
      v.memory = 512
      v.cpus = 1
    end
  end

  config.vm.define "DataBase" do |db|
    db.vm.box = "centos/7"

    # Provisioning SSH Keys
    db.vm.provision "file",
        source: "./ssh_keys/id_rsa.pub",
        destination: "~/.ssh/authorized_keys"

    db.vm.hostname = "DataBase"

    db.vm.network "private_network",
        ip: "10.0.0.6",
        virtualbox__intnet: "ansible"

    db.vm.provider "virtualbox" do |v|
      v.name = "Data Base"
      v.memory = 512
      v.cpus = 1
    end
  end
end
