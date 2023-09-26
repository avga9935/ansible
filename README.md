# Ansible Automation README
This README provides instructions on how to set up Ansible automation for managing remote machines.

## Introduction
This project aims to simplify the process of managing remote machines using Ansible. Ansible is an open-source automation tool that allows you to configure and control multiple servers from a central location.

## Prerequisites
Before you begin, ensure you have the following prerequisites in place:

- **Main Ubuntu Machine**: This is the central machine from which you will control other instances.
- **Remote Machines**: Machines you want to manage using Ansible.
- **SSH Keys**: Create SSH keys for secure access to remote machines.

## Getting Started
Follow these steps to set up Ansible automation:

### Connecting Machines
Ensure all remote machines are connected to the main Ubuntu machine so that Ansible can access them without issues.

### SSH Key Setup
Generate SSH keys on the main Ubuntu machine and copy the public key (`id_rsa.pub`) to the `~/.ssh/authorized_keys` file on each remote machine.

### Installing Ansible
Install Ansible on the main Ubuntu machine using the following commands:

```bash
sudo apt update
sudo apt install ansible
```
## Creating an Inventory
Create an inventory file (e.g., inventory.ini) to list the IP addresses or hostnames of the remote machines you want to manage with Ansible.

## Creating a Playbook
Create a playbook file (e.g., myplaybook.yml) where you specify the instructions or commands you want to run on remote machines.

## Running the Playbook
Execute your playbook using Ansible with the following command:
ansible-playbook -i inventory.ini myplaybook.yml

##Example Playbook
Here is an example playbook (myplaybook.yml) and the expected output:

```
PLAY [Example Playbook] ********************************************************

TASK [Gathering Facts] *********************************************************
ok: [WEB1]

TASK [Update packages] *********************************************************
ok: [WEB1]

TASK [Install nginx] ***********************************************************
ok: [WEB1]

TASK [Start nginx] *************************************************************
ok: [WEB1]

PLAY RECAP *********************************************************************
WEB1                       : ok=4    changed=0    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```
