# WPCS2_devenv
Development environment for WPCS2 using Vagrant + Ansible

## Usage

### Setup environment

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
sudo add-apt-repository ppa:ansible/ansible
sudo apt update
sudo apt install -y ansible
```

Finally, run Ansible.
```
sudo ansible-playbook -i /vagrant/develop /vagrant/playbook.yml 
```

You have to logout / login to the box again for applying changes on `~/.bashrc`.

### Instructions for developing WPCS2

1. Clone WPCS2 to `WPCS2_devenv/WPCS2` (Do it on host)
  * On VM, you can access host's folder `WPCS2_devenv/` as `vagrant/`
1. ssh to VM

 ```
 vagrant ssh
 ```
 
1. cd to WPCS2 directory

 ```
 cd /vagrant/WPCS2
 ```
 
1. Install gems

 ```
 mkdir -p ~/WPCS2/vendor/bundle
 bundle install --path ~/WPCS2/vendor/bundle
 ```
 (option)
 ```
 sudo apt install graphviz
 ```
 
1. Install node packages

 ```
 npm install -no-bin-links
 ```
 
1. Serve the app

 ```
 rake db:migrate
 bundle exec rails s -b 0.0.0.0
 ```

1. Access to the app on your browser
 * [http://localhost:3000/](http://localhost:3000/)
 * You can change the port number by editing Vagrantfile

Happy developing!

