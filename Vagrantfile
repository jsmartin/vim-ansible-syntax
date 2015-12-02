## standalone

VAGRANTFILE_API_VERSION = "2"


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "system" do |r|
    r.vm.hostname = "web-1"
    r.vm.box = "bento/centos-7.1"
    r.ssh.insert_key = false
    #r.vm.network :private_network, ip: "10.10.0.10"
    r.vm.provider :virtualbox do |vb, override|
      vb.customize ["modifyvm", :id, "--memory", "128"]
      vb.customize ["modifyvm", :id, "--cpus", "1"]
    end
  
    r.vm.provision :ansible do |ansible|
      ansible.extra_vars = {
        foo: "bar",
      }
      ansible.host_key_checking = false
      ansible.sudo = true
      ansible.verbose = "v"
      ansible.playbook = "test.yml"
      ansible.limit = "all"
    end
  end
end
