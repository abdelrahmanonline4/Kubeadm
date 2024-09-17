# Vagrantfile to provision a Kubernetes cluster using kubeadm
Vagrant.configure("2") do |config|
  
    # Master node configuration
    config.vm.define "k8s-master" do |master|
      master.vm.box = "ubuntu/focal64"  
      master.vm.hostname = "k8s-master"
      master.vm.network "private_network", ip: "192.168.50.10"
      master.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
        vb.cpus = 2
      end
      master.vm.provision "shell", path: "install_kubeadm.sh"
    end
  
    # Worker node configuration
    config.vm.define "k8s-worker1" do |worker1|
      worker1.vm.box = "ubuntu/focal64"  
      worker1.vm.hostname = "k8s-worker1"
      worker1.vm.network "private_network", ip: "192.168.50.11"
      worker1.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 2
      end
      worker1.vm.provision "shell", path: "install_kubeadm.sh"
    end
  
    config.vm.define "k8s-worker2" do |worker2|
      worker2.vm.box = "ubuntu/focal64"  
      worker2.vm.hostname = "k8s-worker2"
      worker2.vm.network "private_network", ip: "192.168.50.12"
      worker2.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        vb.cpus = 2
      end
      worker2.vm.provision "shell", path: "install_kubeadm.sh"
    end
  end
  