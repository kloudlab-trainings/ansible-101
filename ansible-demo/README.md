

# installation
```
pip install ansible
apt update && apt install sshpass
```

## create inventory
Create hosts.ini

```
ip_address ansible_user=username  ansible_password=password

# example
54.210.243.162  ansible_user=ansible  ansible_password=ansible
34.228.214.88 ansible_user=ansible  ansible_password=ansible
```



Ansible adhoc commands
```
ansible -i hosts.ini all -m ping
ansible -i hosts.ini all -m command -a "date"  # see dates on all managed.
ansible -i hosts.ini all -m command -a "ip a"

```

great for debugging, running one task. But when you have many tasks you need something better.

#Playbook Commands
export ANSIBLE_CONFIG=`pwd`/ansible.cfg
ansible-playbook -i hosts.ini 1.yaml

Limit to specific hosts
ansible-playbook -i hosts.ini 1.yaml -l <hostname/ip/group>