# -*- mode: ruby -*-
# vi: set ft=ruby :
#
#  The fedora/25-cloud-base and debian/jessie64 boxes are also available for
#  the "virtualbox" provider.  Set the VAGRANT_PROVIDER environment variable to
#  "virtualbox" to use them instead.
#
Vagrant.configure("2") do |config|
  config.vm.define "fedora" do |c|
    c.vm.box = "fedora/25-cloud-base"
    c.vm.synced_folder ".", "/vagrant", type: "rsync",
      rsync__exclude: "bundles", rsync__args: "-vadz"
    c.vm.provision "shell", inline: <<-SHELL
      sudo /vagrant/vagrant/provision.sh
    SHELL
  end
  config.vm.define "debian" do |c|
    c.vm.box = "debian/jessie64"
    c.vm.synced_folder ".", "/vagrant", type: "rsync",
      rsync__exclude: "bundles", rsync__args: "-vadz"
    c.vm.provision "shell", inline: <<-SHELL
      sudo /vagrant/vagrant/provision.sh
    SHELL
  end
end
