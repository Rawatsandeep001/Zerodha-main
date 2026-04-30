# ANSIBLE ASSIGNMENT-1
## UserManager – Project Management System

---

## 📌 Overview
This project demonstrates a comprehensive **Ansible-based User and Project Management System** for automating Linux administration tasks such as user creation, group management, directory structure setup, permissions, sudo access, and password policies.

It simulates a real-world **DevOps environment** with multiple teams, role-based access control, and security enforcement.

---

## 🏗️ Team Structure

- Development Team → `dev-team`
- DevOps Team → `devops-team`
- Admin Group → `admin-group`

---

## 🔧 Inventory Setup
```bash
cat inventory.ini
```
![alt text](image.png)

### Test Connectivity
```bash
sudo ansible nodes -i inventory.ini -m ping
```
![alt text](image-1.png)
---

## 👤 User Management

### Create 9 Users (UID starts from 2000)

#### Dev Team
```bash
ansible nodes -i inventory.ini -m user -a "name=devuser1 uid=2000 group=dev-team shell=/bin/bash" -b
ansible nodes -i inventory.ini -m user -a "name=devuser2 uid=2001 group=dev-team shell=/bin/bash" -b
ansible nodes -i inventory.ini -m user -a "name=devuser3 uid=2002 group=dev-team shell=/bin/bash" -b
```
![alt text](image-2.png)

![alt text](image-3.png)
#### DevOps Team
```bash
ansible nodes -i inventory.ini -m user -a "name=devops1 uid=2003 group=devops-team shell=/bin/bash" -b
ansible nodes -i inventory.ini -m user -a "name=devops2 uid=2004 group=devops-team shell=/bin/bash" -b
ansible nodes -i inventory.ini -m user -a "name=devops3 uid=2005 group=devops-team shell=/bin/bash" -b
```
![alt text](image-4.png)

![alt text](image-5.png)

![alt text](image-7.png)

![alt text](image-6.png)
#### Admin Team
```bash
ansible nodes -i inventory.ini -m user -a "name=admin1 uid=2006 group=admin-group shell=/bin/bash" -b
ansible nodes -i inventory.ini -m user -a "name=admin2 uid=2007 group=admin-group shell=/bin/bash" -b
ansible nodes -i inventory.ini -m user -a "name=admin3 uid=2008 group=admin-group shell=/bin/bash" -b
```

![alt text](image-8.png)

![alt text](image-9.png)

![alt text](image-10.png)

![alt text](image-11.png)

![alt text](image-12.png)
---

## 👥 Group Management (Teams)
```bash
ansible nodes -i inventory.ini -m group -a "name=dev-team state=present" -b
ansible nodes -i inventory.ini -m group -a "name=devops-team state=present" -b
ansible nodes -i inventory.ini -m group -a "name=admin-group state=present" -b
```
![alt text](image-20.png)
---

## 📁 Directory Structure

### Personal Workspace
```bash
ansible nodes -i inventory.ini -m file -a "path=/home/devuser1/workspace state=directory mode=0750" -b
```
![alt text](image-13.png)

### Team Directories
```bash
ansible nodes -i inventory.ini -m file -a "path=/opt/teams/dev-team state=directory mode=0770" -b
ansible nodes -i inventory.ini -m file -a "path=/opt/teams/devops-team state=directory mode=0770" -b
ansible nodes -i inventory.ini -m file -a "path=/opt/teams/admin-group state=directory mode=0770" -b
```
![alt text](image-16.png)

![alt text](image-17.png)


![alt text](image-18.png)


![alt text](image-19.png)


---

## 🔐 SUDO ACCESS
```bash
ansible nodes -i inventory.ini -m copy -a "dest=/etc/sudoers.d/admin-group content='%admin-group ALL=(ALL) NOPASSWD:ALL' mode=0440" -b
```
![alt text](image-15.png)

---

## 🔑 Password Policy
```bash
ansible nodes -i inventory.ini -m lineinfile -a "path=/etc/login.defs regexp='^PASS_MAX_DAYS' line='PASS_MAX_DAYS 30'" -b
```
![alt text](image-14.png)
---

## 🔐 Security Features
- Role-based access control
- Team isolation
- Sudo privilege delegation
- Password expiry enforcement
- Centralized system management

---

## 📊 Permission Model

| Resource Type       | Access Policy |
|--------------------|--------------|
| Personal Workspace  | Owner full, team read |
| Team Directories    | Team full, others read-only |
| Shared Resources    | All teams read/write |
| Archive             | Read-only for all users |
| Admin Areas         | admin-group full access |

```
## 🚀 Conclusion
This project demonstrates how Ansible can automate large-scale Linux user management, security policies, and infrastructure configuration with consistency, scalability, and minimal manual effort.

