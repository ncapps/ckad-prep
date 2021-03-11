# -*- mode: ruby -*-
# vi: set ft=ruby :

# For a complete reference, please see the online documentation at
# https://docs.vagrantup.com.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  # Configure common command line utilities
  config.vm.provision "cli-utilities", type: "shell", path: "./scripts/common-debian.sh"

  # Install k3s
  config.vm.provision "k3s", type: "shell", inline: <<-SHELL
    curl -sfL https://get.k3s.io | sh -s - --write-kubeconfig-mode 644
    # Configure kubectl alias and completion
    kubectl completion bash >/etc/bash_completion.d/kubectl
    echo 'alias k=kubectl' >>/home/vagrant/.bashrc
    echo 'complete -F __start_kubectl k' >>/home/vagrant/.bashrc
  SHELL

end
