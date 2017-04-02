# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "xenial64"

  config.vm.provider :lxc do |lxc,ovrd|
    ovrd.vm.box = "arjenvrielink/xenial64-lxc"
    lxc.backingstore = 'dir'
  end

  config.vm.provision "shell",
    inline: "sudo apt update && sudo apt install -y devscripts dh-golang dh-systemd golang-any indent libapparmor-dev libseccomp-dev python3-markdown xfslibs-dev" +
            " autoconf automake autotools-dev bash-completion debhelper dh-apparmor dh-autoreconf fakeroot gettext grub-common gnupg2 init-system-helpers" +
            " libcap-dev libglib2.0-dev libudev-dev pkg-config python3 python3-docutils squashfs-tools udev"

  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  end

end
