# rke-ansible

Ansible playbook to install Rancher Kubernetes Engine

## Usage

Skip this step if you are using real hardware

```sh
vagrant up
```

Copy your ssh key to the remote machine, then run the Ansible playbook

```sh
ansible-playbook playbook.yml -i hosts.ini -u vagrant
```
