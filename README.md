# ansible-taste-test
ansible taste-test example

This is 'more-or-less' the first example from the [taste-test book](https://valdhaus.co/books/taste-test-puppet-chef-salt-stack-ansible.html) which you should buy and read.


## Create your digital ocean machines

1. Create 3 [Digital Ocean](https://www.digitalocean.com/) virtual machines [ droplets ]
2. Configure them for Ubuntu
3. Set there hostname dod-master, dod-puppy, dod-kitty. Notes: dod stands for DigitalOceanDroplet and puppy and kitty are nodes.
3. Upload your ssh key's, via Digital-oceans machine creation interface.
4. Manage `/etc/hosts`, and `~/.ssh/config` so that you can ssh to each machine without passwords and so that dod-master can ssh to the other 2 machines without passwords.  
5: finally make sure there are no firewall restrictions
   `iptables --list --numeric`

## Install Ansible on the master machine
Setup ansible on dod-master
```
$ apt-get update
$ apt-get install python-software-properties -y
$ add-apt-repository ppa:rquillo/ansible -y
$ apt-get update
$ apt-get install ansible -y
$ apt-get install git -y
```

## provision your nodes

Fianlly you are ready to provision your nodes.
- Pull this repository in the dod-master machine

`ansible-playbook taste.yml`