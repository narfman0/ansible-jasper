# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/jessie64"
  config.vm.hostname = "jasper"
  config.nfs.functional = false
  config.vm.define :jasper do |jasper|
  end

  config.vm.provider :virtualbox do |vb|
    if RUBY_PLATFORM =~ /darwin/
      vb.customize ["modifyvm", :id, '--audio', 'coreaudio', '--audiocontroller', 'hda']
    elsif RUBY_PLATFORM =~ /mingw|mswin|bccwin|cygwin|emx/
      vb.customize ["modifyvm", :id, '--audio', 'dsound', '--audiocontroller', 'ac97']
    end
  end

  # Ansible provisioner.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.sudo = true
  end
end
