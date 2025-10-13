# ansible

install python3 on the control node and nodes that are to be managed by ansible

install ansible on the control node
$ pip install --include-deps ansible
ref: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#control-node-requirements

### Practise exercise 1: Enable password-less authentication
- Create 2 ec2 instances to be managed by ansible control plane (my laptop)
$ ssh-copy-id -f "-o IdentityFile <PATH TO PEM FILE>" ubuntu@<INSTANCE-PUBLIC-IP>
- Can now connect to the ec2 instance without any password:
$ ssh ubuntu@52.87.251.93

using password without the pem file:
- login to ec2 instance using instance connect 
- edit the file: /etc/ssh/sshd_config.d/60-cloudimg-settings.conf
$ sudo systemctl restart ssh
set new password for ubuntu user
$ sudo passwd ubuntu 
- from laptop: $ ssh-copy-id ubuntu@\<public-ip-of-ec2>
- passwordless authentication now enabled

### Ansible inventory

2 formats: inventory.ini or yaml
to avoid passing path of inventory.ini, it can rather be stored at the default location: /etc/ansible/hosts

Example adhoc command:
$ ansible -i inventory.ini -m ping all
-i - inventory location
-m - module
all - implement on all servers mentioned in inventory file
$ ansible -i inventory.ini -m shell -a "apt install openjdk" all

