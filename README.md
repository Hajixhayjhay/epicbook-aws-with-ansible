# epicbook-aws
# 📚 EpicBook Deployment — Terraform + Ansible

EpicBook is a sample web application deployed using **Terraform** and **Ansible** to demonstrate end-to-end **Infrastructure as Code (IaC)** and **configuration automation** in a DevOps workflow.

---

## 🧩 Project Overview

This project provisions infrastructure using **Terraform** and configures application components using **Ansible roles**.  
It showcases a clean, modular, and idempotent deployment pipeline for a production-like environment.

---

## 🏗️ Architecture

Terraform ➜ Infrastructure Provisioning
Ansible ➜ Configuration Management
Nginx ➜ Web Server
EpicBook ➜ Web Application

Each layer is automated to ensure consistency, scalability, and repeatability across environments.

---

## ⚙️ Tools & Technologies

- **Terraform** – Infrastructure provisioning  
- **Ansible** – Configuration management  
- **YAML** – Declarative configuration  
- **Nginx** – Reverse proxy and web server  
- **Git** – Version control  
- **Linux (Ubuntu)** – Target host




---

## 🚀 Deployment Workflow

### Step 1️⃣ — Initialize and Apply Terraform
```bash
cd aws-cloud
terraform init
terraform apply --var-file="dev.tfvars" --auto-approve
This step provisions the infrastructure (e.g., a virtual machine, security groups, networking).

Step 2️⃣ — Configure with Ansible
bash
Copy code
cd ../ansible
ansible-playbook -i inventory.ini site.yml
Ansible automates:

System updates & package installations

Nginx configuration

EpicBook app deployment

Step 3️⃣ — Encrypt Sensitive Data (Optional)
To protect sensitive credentials in group_vars/web.yml:

```bash

ansible-vault encrypt group_vars/web.yml

```

To edit or decrypt:


```bash

ansible-vault edit group_vars/web.yml
ansible-vault decrypt group_vars/web.yml

```

✅ Key Learnings
Separation of concerns between provisioning (Terraform) and configuration (Ansible)

Use of Ansible roles for maintainable automation

Implementation of handlers, templates, and idempotent tasks

Security best practices via Ansible Vault

📘 Reflection
This project strengthened my understanding of how DevOps tools interact in a real deployment cycle.
By modularizing infrastructure and configuration, I ensured a reusable and scalable setup that teams can easily maintain and extend.

 Future Improvements
Integrate CI/CD using GitHub Actions

Add load balancing and auto-scaling

Implement application monitoring with Prometheus or CloudWatch