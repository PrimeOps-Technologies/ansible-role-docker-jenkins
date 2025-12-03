# 🚀 Ansible Role — jenkins

[![PrimeOps-Technologies](https://img.shields.io/badge/Made%20By-PrimeOps-blue?style=flat-square&logo=ansible)](https://primeops.co.in)
[![Ansible](https://img.shields.io/badge/Ansible-2.9%2B-green.svg?logo=ansible)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)


A production-ready Ansible role to install and configure **jenkins** on Ubuntu/Debian systems.


---

## 🏢 About PrimeOps-Technologies

**PrimeOps-Technologies** delivers **Cloud & DevOps excellence** for modern teams:
- 🚀 **Infrastructure Automation** with Terraform, Ansible & Kubernetes
- 💰 **Cost Optimization** via scaling & right-sizing
- 🛡️ **Security & Compliance** baked into CI/CD pipelines
- ⚙️ **Fully Managed Operations** across AWS, Azure, and GCP


> 💡 Need enterprise-grade DevOps automation?
> 👉 Visit [**primeops.co.in**](https://primeops.co.in) or email **primeopstechnologies@gmail.com**

---

## 📁 Directory Structure

```
jenkins/
├── defaults/main.yml
├── handlers/main.yml
├── meta/main.yml
├── tasks/configure.yml
├── tasks/install.yml
├── tasks/users.yml
├── templates
└── LICENSE
```

---

## ⚙️ Role Variables

### **defaults/main.yml**
```yaml
# Jenkins variable
jenkins_version: "lts-alpine"
jenkins_caddy_server_name: jenkins.cloudlovers.com

# jenkins settings
jenkins_opt_dir: "/opt/jenkins"
jenkins_config_dir: "{{ jenkins_opt_dir }}/config"
jenkins_tmp_dir: "{{ jenkins_opt_dir }}/tmp"
jenkins_data_dir: "{{ jenkins_opt_dir }}/data"

jenkins_https_port: "443"
jenkins_http_port: "8080"
jenkins_xmx: "{{ ( ansible_memtotal_mb * 0.20 ) | round(0, 'ceil') | int }}"
jenkins_user: jenkins
jenkins_group: jenkins
jenkins_hostname: localhost
jenkins_agent_port: "50001"
jenkins_plugins:
  - git
  - ssh

# Caddy settings
caddy: true
cert_path: "/root/config"
key_path: "/root/config"

# node version
java_packages: openjdk-11-jdk

```

---

## 🚀 Usage

---

## 🔄 Handlers

```yaml
- name: restart jenkins
  service:
    name: "jenkins.service"
    state: restarted
    enabled: true

```

---

## 🧪 Testing

After running the role, verify using:

```
http://your-server-ip:8080/
```

---

## 🖥️ Supported Platforms

| OS | Versions |
|----|----------|
| **Ubuntu** | 18.04, 20.04, 22.04 |
| **Debian** | 10, 11 |

## 👥 Team Members
<table> <tr> <td align="center"> <img src="https://github.com/yrahul05.png" width="80" style="border-radius:50%"><br> <strong>Rahul Yadav</strong><br> <sub>CEO & CTO</sub><br> <a href="https://github.com/yrahul05">@yrahul05</a> </td>  <td align="center"> <img src="https://github.com/themanojkumawat.png" width="80" style="border-radius:50%"><br> <strong>Manoj Kumawat</strong><br> <sub>DevOps Lead</sub><br> <a href="https://github.com/themanojkumawat">@themanojkumawat</a> </td> <td align="center"> <img src="https://github.com/sureshyadav76.png" width="80" style="border-radius:50%"><br> <strong>Suresh Yadav</strong><br> <sub>Senior DevOps Engineer</sub><br> <a href="https://github.com/sureshyadav76">@sureshyadav76</a> </td> <td align="center"> <img src="https://github.com/therahul28.png" width="80" style="border-radius:50%"><br> <strong>Rahul</strong><br> <sub>Senior DevOps Engineer</sub><br> <a href="https://github.com/therahul28">@therahul28</a> </td> <td align="center"> <img src="https://github.com/abhisharma24.png" width="80" style="border-radius:50%"><br> <strong>Abhi Sharma</strong><br> <sub>Senior DevOps Engineer</sub><br> <a href="https://github.com/abhisharma24">@abhisharma24</a> </td> <td align="center"> <img src="https://github.com/Rohityadav-7.png" width="80" style="border-radius:50%"><br> <strong>Rohit Yadav</strong><br> <sub>COO</sub><br> <a href="https://github.com/Rohityadav-7">@Rohityadav-7</a> </td>  </tr> </table>


### 💙 Maintained by [PrimeOps-Technologies](https://primeops.co.in)
> PrimeOps-Technologies — Simplifying Cloud, Securing Scale.