# NBFC - Ansible Playbooks

A collection of useful Ansible playbooks for automating server setups, based on DigitalOcean's Community guides.

- [Initial Server Setup for Ubuntu 18.04](https://github.com/nubificus/ansible-playbooks/tree/master/initial-setup) *

_\*the Initial Server Setup should be your starting point for fresh servers._

## Getting Started

To set up your Ansible environment, please follow our guide on [How to Install and Configure Ansible on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-ansible-on-ubuntu-18-04).

### Connection Test

From your local machine setup hosts.ini:

`hosts.ini`:
```
[hosts]
192.168.1.198
jetson.nanos.gr
```
and run:
```command
ansible -i hosts.ini -m ping -u remote_user
```

If you're able to get a "pong" reply back from your node(s), your setup works as expected and you'll be able to run both ad-hoc commands and playbooks on your nodes, using Ansible.

### Initial Server Setup

To setup a node with users (in `users.yml`) and initial packages (in `packages.yml`) run the following:

```
cd initial-setup
ansible-playbook -i hosts.ini -u root -v playbook.yml
```

