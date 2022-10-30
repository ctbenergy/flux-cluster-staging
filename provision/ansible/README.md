# Building a infrastructure deploying configuration using Ansible Playbooks

These playbooks configure Debian 11 Server,
To use them, first edit the `hosts.yml` inventory file to contain the
hostnames.

## System requirements

Deployment environment must have Ansible 2.8.0+

## Ansible playbooks

Run a playbook, like this:

```bash
ansible-playbook playbooks/ping.yml
ansible-playbook playbooks/test.yml
ansible-playbook playbooks/debug.yml

ansible-playbook playbooks/site.yml

ansible-playbook playbooks/deploy_ssh_key.yml
ansible-playbook playbooks/apt_dist_upgrade.yml
ansible-playbook playbooks/fail2ban.yml

```
