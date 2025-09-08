# SJSU Ansible Webserver Project

This project is part of my SJSU assignment to practice **infrastructure automation** with Ansible.

It deploys and undeploys an **Nginx webserver** on two VMs (VM1 & VM2), listening on **port 8080**.  
Each VM serves a custom "Hello World" page:

- VM1 → `Hello World from SJSU-1`
- VM2 → `Hello World from SJSU-2`

---

## 🖥️ Environment
- MacBook Pro (control machine)
- Multipass VMs running Ubuntu 22.04
- Ansible installed via Homebrew

---

## 📂 Project Structure
sjsu-ansible/
├── hosts.ini # Ansible inventory with VM IPs
├── site.yml # Playbook (deploy + undeploy)
└── templates/
     ├── index.html.j2 # Hello World template
		 └── sjsu.conf.j2 # Nginx site config (port 8080)

---

## 🚀 Usage

### 1. Test connectivity
```bash
ansible -i hosts.ini webservers -m ping
```
### 2. Deploy webservers
```
ansible-playbook -i hosts.ini site.yml --tags deploy
Visit:
http://<VM1_IP>:8080 → Hello World from SJSU-1
http://<VM2_IP>:8080 → Hello World from SJSU-2
```
### 3. Undeploy servers
```
ansible-playbook -i hosts.ini site.yml --tags undeploy

```
📸 Demo
```
Screenshots and demo video included in the assignment Word report.

```
📌 Author
```
Name: Shreram
Course: Software Engineering Masters, SJSU – Data Science Specialization
