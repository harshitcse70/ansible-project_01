# Ansible Nginx + Docker Automation (Role-Based)

This project demonstrates how to automate the installation and management of **Nginx and Docker** on remote AWS EC2 instances using **Ansible roles**. It follows a real-world DevOps workflow including **modular design, SSH authentication, and infrastructure automation**.

---

##  Overview

This project uses an Ansible playbook that calls reusable roles to:

* Install Docker
* Install Nginx
* Start and enable services on boot

 Designed using **best practices (roles instead of monolithic playbooks)**

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
├── inventory
├── site.yml
├── roles/
│   ├── docker/
│   │   └── tasks/main.yml
│   └── nginx/
│       └── tasks/main.yml
└── README.md
```

---

## Prerequisites

* Ansible installed on control/node(no need to install it on target node)
* At least one EC2 instance (target node)
* SSH access configured between control and target

---

## SSH Key Setup (Manual Method)

### Step 1: Generate Key (Control Node)

```
ssh-keygen
cat ~/.ssh/id_rsa.pub
```

### Step 2: Add Key to Target Server

Paste into:

```
~/.ssh/authorized_keys
```

### Step 3: Set Permissions

```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

### Step 4: Test Connection

```
ssh ubuntu@<target-ec2-ip>
```

---

## Run the Playbook

```
ansible-playbook -i inventory nginx.yml
```

---

##  Execution Flow

```
Playbook (site.yml)
        ↓
Docker Role → installs Docker
        ↓
Nginx Role → installs Nginx
        ↓
Services started and enabled 
```

---

##  Features

* Role-based modular architecture
* Automated Docker & Nginx installation
* Service management (start + enable)
* Passwordless SSH authentication
* Clean and scalable DevOps structure

---

## Key Learnings

* Ansible roles vs playbooks
* Modular automation design
* SSH key-based authentication
* Infrastructure automation on AWS
* Git branching & refactoring workflow

---
