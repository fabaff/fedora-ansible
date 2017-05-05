# Fedora - Ansible Contrib Repository

This repository contains user-contributed real world examples for Ansible
playbooks, especially for Fedora and its downstream (RHEL), as well as modules
that are not a part of Ansible's core distribution.

This is designed to be a resource to folks learning configuring Fedora
with Ansible, as well as a way to share useful resources of all kinds.

If you have just found Ansible or Fedora, you should start here:

 * [Fedora](http://www.fedoraproject.org)
 * [Ansible project](https://github.com/ansible/ansible) -- see the examples directory

A lot of playbooks in this repository are made and used with the 
[Fedora Security Lab](https://fedorahosted.org/security-spin/) and the 
[Fedora Security Lab Test bench](https://fedorahosted.org/security-spin/wiki/Test%20bench). 
For all security-related playbooks please check the 
[Fedora Security Lab Test bench](https://github.com/fabaff/fsl-test-bench) git
repository .

## Prerequisites

The setup of Ansible is explained on the 
[Ansible Getting Started](http://ansible.cc/docs/gettingstarted.html) page. 
Here is only the setup of the managed nodes covered. For every system you want
to manage, you need to have the client's SSH key in the *authorized_keys* file
of the management system and Python.

Make sure that [Python](http://www.python.org/) is installed. If not, install
the Python package.

```bash
$ sudo dnf -y install python
```
Add the SSH key to the *authorized_keys* file.

From the managed node:

```bash
$ ssh root@[IP address of your management system] 'cat ~/.ssh/id_rsa.pub' | cat - >> ~/.ssh/authorized_keys
```
From the management system:

```bash
$ sudo ssh-copy-id -i /root/.ssh/id_rsa.pub root@[IP address of your managed node]
```

## Structure

At the moment the structure of the repository looks like this:

```bash
.
├── files ----------- Template files
├── handlers -------- Handlers for Fedora services
├── maintenance ----- Complete playbooks
├── maintenance.yml - Regular tasks to perform on a running system
├── modules --------- Modules especially for Fedora
├── README.md ------- This files
├── tasks ----------- A collection of tasks
├── setup.yml ------- Collected tasks for a fresh installed system
└── variables ------- Storage files for variables
```

## Warning
**Think first** before you implement stuff from this repository. Consider the 
playbooks in this repository as a show case. Somethings doesn't make sense, are
nasty hacks, or easier to do with another approach.

## Licensing
Examples and modules should be licensed GPLv3 per the rest of Ansible, to
encourage modules to graduate from contrib to core.

All playbook content is assumed to be Creative Commons 3.0 Attribution licensed. 
Non-commerical or No-derivatives CC extensions are not acceptable, to encourage
easy use by all users, regardless of purpose.
