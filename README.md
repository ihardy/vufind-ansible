# vufind-ansible
Anisble playbook and role for deploying a basic vufind instance and loading some sample data. This playbook has been tested against Ubuntu 16.04 (Xenial).

## example playbook
```
- hosts: all
  roles:
    - vufind
```
## using the vagrant file
To provision a vagrant box with vufind and load sample data, you need to have [Vagrant](https://www.vagrantup.com/) and [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) installed on the host machine. Assuming you have python3 already installed, here is one easy way to add Ansible without any impact on the system python install (if it exists):
```
python3 -m venv venv
source venv/bin/activate
pip install ansible
```
Once the prerequisites are met, run
```
vagrant up
```
VuFind should be available at `http://localhost:8000/vufind/` (port 80 on the guest machine is mapped ot 8000 on the host).

You may want to tweak the amount of memory allocated to the vagrant box depending on whats available on your system. When you're done you can either run `vagrant halt` to shutdown and save the state of the Vagrant box or `vagrant destroy` to remove it.

## Notes
Sample data is from UNC Libraries and fetched from the internet archive here: https://archive.org/download/unc_catalog_marc
