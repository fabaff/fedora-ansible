# Roles

This directory contains roles for Ansible.

## Usage

Manual creation of a role:

```bash
mkdir -p [roles-name]/{files,handlers,meta,templates,tasks,vars}
```

To setup a role for Ansible Galaxy:

```bash
ansible-galaxy init [role-name]
```

The playbooks need a 'roles' entry:

```
---
- hosts: all
  roles:
     - common
     - [role-name]
```

## Further information

For details please check the [Ansible documentation](http://docs.ansible.com/playbooks_roles.html)
