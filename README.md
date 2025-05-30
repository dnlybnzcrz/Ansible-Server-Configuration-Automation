# Ansible Server Configuration Automation

This repository contains Ansible playbooks for automating server configuration management across Ubuntu and CentOS environments.

## Project Overview

This project automates the following tasks across multiple servers:
- Sets up a custom MOTD (Message of the Day) banner
- Installs and configures Python3 and pip3 as default
- Installs Java 8 (OpenJDK)
- Creates a new user with specific UID and home directory

## Prerequisites

- Ansible installed on the control node
- SSH access to target servers
- Target servers running Ubuntu or CentOS

## Project Structure

```
.
├── ansible.cfg      # Ansible configuration file
├── config.yaml      # Main playbook configuration
├── inventory        # Inventory file with server details
└── README.md        # Project documentation
```

## Server Configuration

The project currently manages two servers:
- Ubuntu Server (192.168.56.7)
- CentOS Server (192.168.56.9)

## Playbook Tasks

1. **MOTD Configuration**
   - Sets a custom message: "Ansible Managed node by cruz"

2. **Package Installation**
   - Python3
   - pip3
   - Java 8 (OpenJDK)

3. **Python Configuration**
   - Sets Python3 as the default python interpreter
   - Sets pip3 as the default package manager

4. **User Management**
   - Creates a new user named "Daniel"
   - Sets UID to 1069
   - Creates home directory automatically

## Usage

To run the playbook:

```bash
ansible-playbook -i inventory config.yaml
```

## Variables

The playbook uses the following variables:
- `motd`: Custom message of the day
- `user`: Username for the new user account
- Package names are defined in the inventory file for different distributions

## Author

Daniel Cruz

## License

This project is open-sourced under the MIT license.
