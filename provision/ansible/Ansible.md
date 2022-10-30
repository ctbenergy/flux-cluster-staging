## Ansible

## Ansible Documentation

[Ansible Documentation](https://docs.ansible.com/ansible/latest/)

[Getting started with Ansible](https://docs.ansible.com/ansible/latest/getting_started/index.html)

[Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/index.html)

[User Guide](https://docs.ansible.com/ansible/latest/user_guide/index.html)

[Tips and tricks](https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html)

[Sample Ansible setup](https://docs.ansible.com/ansible/latest/user_guide/sample_setup.html)

[How to build your inventory](https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html)

[Working with command line tools](https://docs.ansible.com/ansible/latest/user_guide/command_line_tools.html)

[Ansible Configuration Settings](https://docs.ansible.com/ansible/latest/reference_appendices/config.html)

[Encrypting content with Ansible Vault](https://docs.ansible.com/ansible/latest/user_guide/vault.html)

[Collection Index](https://docs.ansible.com/ansible/latest/collections/index.html)

## Collections in the Community Namespace

[Collections in the Community Namespace](https://docs.ansible.com/ansible/latest/collections/community/)

[community.crypto.openssh_keypair module – Generate OpenSSH private and public keys](https://docs.ansible.com/ansible/latest/collections/community/crypto/openssh_keypair_module.html)

## Collections in the Ansible Namespace

[Collections in the Ansible Namespace](https://docs.ansible.com/ansible/latest/collections/ansible/)

[ansible.builtin.ssh connection – connect via SSH client binary](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/ssh_connection.html)

## Ansible vault

### Ansible vault password

Keep this password in another place away from your playbook repository.
I have my Ansible vault password in `~/vault_pass.txt` Create your own.

### Ansible vault encrypt/view/decrypt

```bash
ansible-vault encrypt vault_test.yml
ansible-vault view vault_test.yml
ansible-vault decrypt vault_test.yml
ansible-vault create vault_test.yml
ansible-vault edit vault_test.yml
```

```bash
ansible-vault encrypt_string 'ANSIBLE_HOST' --name 'ansible_host' --vault-password-file ~/.vault_pass
```

### Ansible vault id

With inline encrypted variables, you can also use Vault Identities.

```bash
    ansible-vault encrypt_string --vault-id staging@~/.vault_pass_staging 'SECRET' --name 'password'
```

or use the `vault_identity_list` in the `default` section from `ansible.cfg`.

```bash
ansible-vault encrypt_string --encrypt-vault-id staging 'ANSIBLE_HOST' --name 'ansible_host'
```

## Ansible inventory

```bash
ansible-inventory -i inventory/staging/hosts.yml --list
```

## Ansible playbook

```bash
ansible-playbook -i {{.ANSIBLE_INVENTORY_DIR}}/hosts.yml {{.ANSIBLE_PLAYBOOK_DIR}}/test.yml
```

# Ansible Galaxy

The Ansible community hub for sharing automation with everyone.

[Ansible Galaxy](https://galaxy.ansible.com/home)

## Ansible Galaxy Documentation

[Galaxy Documentation](https://galaxy.ansible.com/docs/)

[Installing content](https://galaxy.ansible.com/docs/using/installing.html)

### Ansible Galaxy Roles<br/><br/>

Listing Your Installed Roles

```bash
ansible-galaxy list
```

Determining Where Roles Are Installed

```bash
ansible-inventory -i inventory/staging/hosts.yml --list
```

Install a Role

```bash
ansible-galaxy install geerlingguy.apache
```

Install a specific version

```bash
ansible-galaxy install geerlingguy.apache,v1.0.0
```

It's also possible to point directly to the git repository

```bash
ansible-galaxy install git+https://github.com/geerlingguy/ansible-role-apache.git,0b7cd353c0250e87a26e0499e59e7fd265cc2f25
```

Installing Multiple Roles From a File

```bash
ansible-galaxy install -r rools/requirements.yml --force
```

Determine where to install roles

```bash
ansible-galaxy install --roles-path ~/ansible-roles geerlingguy.apache
```

### Ansible Galaxy Collections<br/><br/>

Listing Your Installed Collections

```bash
ansible-galaxy collection list
```

Installing Collections Roles From a File

```bash
ansible-galaxy collection install -r collections/requirements.yml
```

# Ansible Turtorials

[Encrypt with Ansible-Vault](https://iceburn.medium.com/encrypt-with-ansible-vault-2306d1fd818b)

[How to Keep Your Playbooks Secure With Ansible Vault](https://www.cloudbees.com/blog/how-to-keep-your-playbooks-secure-with-ansible-vault)

[How To Use Ansible Vault to Protect Sensitive Playbook Data](https://www.digitalocean.com/community/tutorials/how-to-use-vault-to-protect-sensitive-ansible-data)

[Encrypting Files with Ansible Vault](https://www.youtube.com/watch?v=xeBnAbmt3Wk)

[Ansible Vault tutorial : How to secure ssh password using vault-id encryption |Cisco Example |Part 4](https://www.youtube.com/watch?v=K1y-9pFJ6FA)

[Ansible Playbook to deploy user with SSH Key](https://bidhankhatri.com.np/automation/ansible-playbook-to-deploy-user-with-ssh-key/)

# Ansible VS Code Extension

[Ansible VS Code Extension by Red Hat](https://marketplace.visualstudio.com/items?itemName=redhat.ansible)
