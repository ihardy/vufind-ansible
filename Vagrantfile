Vagrant.configure("2") do |config|
  # os
  config.vm.box = "ubuntu/xenial64"

  # headroom for solr
  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = "8192"
  end

  # open ports
  config.vm.network "forwarded_port", guest: 80, host: 8000
  config.vm.network "forwarded_port", guest: 8080, host: 8080

  # provisioning with ansible
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "vufind.yml"
    ansible.extra_vars = { ansible_python_interpreter:"/usr/bin/python3" }
    ansible.verbose = true
  end


end
