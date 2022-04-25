*****************************************************************ansible*************************************************************************************************
1> Create user in Master Node & All Client Nodes
# useradd ansible
# passwd ansible
# vi /etc/ansible/hosts
[gameserver]
---------    -> ip of node
# visudo 
ansible ALL=(ALL:ALL) NOPASSWD:ALL
# vi /etc/ssh/sshd_config
PermitRootLogin yes
PasswordAuthentication yes
# service sshd restart
# ssh -------  ---> priv ip with passwd u logged node.
# ssh-keygen ----> generate key pair on master node and copy to client node for ssh hanshake.
# cd .ssh
# ssh-copyid ansible@-------   --> priv ip of node (For all node do it)

in Master node 
# su - ansible
# ansible-playbook 1.yaml --check

or
# ansible-playbook 1.yaml -u ansible -K

*************************************************************************************************************************************************************************
