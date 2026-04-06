# Ansible Nginx Automation

This project demonstrates how to automate the installation and management of Nginx on remote AWS EC2 instances using Ansible. It follows a real-world DevOps workflow including SSH-based authentication and infrastructure automation.

---

## Overview

The playbook connects to remote servers using Ansible and performs:

* Installation of Nginx
* Starting the Nginx service
* Enabling Nginx to start on boot

---

## Tech Stack

* **Ansible** – Configuration management & automation
* **AWS EC2 (Ubuntu)** – Target servers
* **Linux** – Operating system
* **SSH** – Secure remote access

---

##  Project Structure

```
ansible-nginx/
├── inventory        # Target server IPs
├── nginx.yml        # Ansible playbook
└── README.md
```

---

##  Prerequisites

* Ansible installed on control node
* At least one EC2 instance (target node)
* SSH access between control and target

---

##  SSH Key Setup (Manual Method)

Passwordless SSH authentication is configured manually:

### Step 1: Generate / View Public Key (Control Node)

```
ssh key-gen
cat ~/.ssh/id_rsa.pub
```

### Step 2: Add Key to Target Server

Login to target EC2 and paste the key:

```
~/.ssh/authorized_keys
```

### Step 3: Set Correct Permissions

```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

### Step 4: Test Connection

```
ssh ubuntu@<target-ec2-ip>
```

Successful login without password confirms setup

---

## Run the Ansible Playbook

Execute the playbook using:

```
ansible-playbook -i inventory nginx.yml
```

---

## Features

* Automates Nginx installation
* Ensures service is running
* Enables service at boot
* Implements passwordless SSH authentication

---

##  Key Learnings

* Basics of Ansible automation
* SSH key-based authentication
* Managing remote infrastructure
* Writing and executing playbooks

--- 
