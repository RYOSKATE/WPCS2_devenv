# WPCS2_devenv
Development environment for WPCS2 using Vagrant + Ansible

## Usage

First, init and up your box.
```
vagrant up
```

Then, ssh to the box.
```
vagrant ssh
```

Before the setting up, you need to install Ansible.
```
/vagrant/init.sh
```

Finally, run Ansible.
```
sudo ansible-playbook -i /vagrant/develop /vagrant/playbook.yml 
```

You have to logout / login to the box again for applying changes on `~/.bashrc`.

Happy developing!
