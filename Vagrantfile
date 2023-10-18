Vagrant.configure("2") do |config|
  # VM01
  config.vm.define "ubuntu1" do |ubuntu1|
    ubuntu1.vm.box = "ubuntu/bionic64"
    ubuntu1.vm.hostname = "ubuntu1"
    ubuntu1.vm.network "public_network"
    ubuntu1.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = 2048
    end
    config.vm.provision "shell" do |s|
      ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
      s.inline = <<-SHELL
        echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
        echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
        ip a | grep enp0s8 | grep inet | awk '{print $2}' | cut -d '/' -f 1
      SHELL
    end
  end

  # VM02
  config.vm.define "ubuntu2" do |ubuntu2|
    ubuntu2.vm.box = "ubuntu/bionic64"
    ubuntu2.vm.hostname = "ubuntu2"
    ubuntu2.vm.network "public_network"
    ubuntu2.vm.provider "virtualbox" do |vb|
      vb.cpus = 2
      vb.memory = 2048
    end
    config.vm.provision "shell" do |s|
      ssh_pub_key = File.readlines("#{Dir.home}/.ssh/id_rsa.pub").first.strip
      s.inline = <<-SHELL
        echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
        echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
        ip a | grep enp0s8 | grep inet | awk '{print $2}' | cut -d '/' -f 1
      SHELL
    end
  end
end
