# vagrant-fake-server-room

# Vagrant common commands
```shell
vagrant up
vagrant destroy
vagrant up webserver-1
```

## Access machine
```shell
 ssh -i ~/.vagrant.d/insecure_private_key vagrant@127.0.0.1 -p 2211
```

## Commands
```shell
ip a
ssh-keygen -it ed25519 -C "Hazar Gul Nazari"
ssh-copy-id -i ~/.ssh/id_ed25519 ip-address
eval $(ssh-agent)
alias ssha='eval $(ssh-agent)'

nano .bashrc 

git config --global user.name "Hazar Gul Nazari"
git config --global user.email "codexcoffee@gmail.com"
cat ~/.gitconfig
```

## Ansible Commands
```shell
touch inventory
126.22.12.32 >> inventory
126.22.12.31 >> inventory
...

# initial connection
ansible all --key-file ~/.ssh/ansible -i inventory -m ping
----
-m = module
-i inventory-name

touch ansible.cfg
---
[default]
inventory = inventory
private_key_file = ~/.ssh/ansible
---
ansible all -m ping

ls /etc/ansible

ansible all --list-hosts
ansible all -m gather_facts
ansible all -m gather_facts --limit ip-address
ansible all -m apt -a update_cache=true // fails
ansible all -m apt -a update_cache=true --become --ask-become-pass
ansible all -m apt -a name=vim-nox --become --ask-become-pass
ansible all -m apt -a name=tmux --become --ask-become-pass
ansible all -m apt -a name=snapd --become --ask-become-pass
ansible all -m apt -a "name=snapd state=latest" --become --ask-become-pass
ansible all -m apt -a "upgrade=dist" --become --ask-become-pass
sudo apt dist-upgrade
```

## Creating playbook in Ansible
Ansible Playbook a declarative approach to have the desired state of a machine.
Ansible reads the playbook and make sure that the state of machine is same as declared on the playbook.
```shell
# Create a install_apache.yml
nano install_apache.yml

```
