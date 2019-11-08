Vagrant.configure("2") do |config|
  # os
  #config.vm.box = "ubuntu/xenial64"
  config.vm.box = "ubuntu/bionic64"

  # headroom for solr
  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = "4096"
  end

  config.vm.define :vufind do |vufind|
    # open ports
    vufind.vm.network "forwarded_port", guest: 80, host: 8000
    vufind.vm.network "forwarded_port", guest: 8080, host: 8080

    # provisioning with ansible
    vufind.vm.provision "ansible" do |ansible|
      ansible.playbook = "vufind.yml"
      ansible.extra_vars = { ansible_python_interpreter:"/usr/bin/python3" }
      ansible.verbose = true
      ansible.groups = { "vufind" => ["vufind"] }
    end
  end

end
