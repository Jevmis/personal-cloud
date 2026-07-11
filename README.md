# Michael J. Ndueso Personal Cloud ☁️

A self-hosted personal cloud infrastructure platform built on **Oracle Cloud Free Tier** using modern DevOps practices.

This project serves as my personal engineering platform for hosting documentation, development tools, automation resources, and self-managed services.

---

## 🚀 Project Overview

The goal of this project is to design, deploy, secure, and maintain a production-style cloud environment while practicing:

- Cloud infrastructure management
- Linux server administration
- Docker containerization
- Reverse proxy configuration
- Database management
- Security hardening
- Backup and disaster recovery
- Continuous improvement through documentation

---

## 🏗️ Architecture

The platform will be deployed using the following architecture:
             Internet
                |
                |
          Domain (DNS)
                |
                |
          Nginx Reverse Proxy
                |
    ----------------------------
    |            |             |
  Wiki.js     Services     Monitoring
    |
PostgreSQL
    |
 Docker
    |
Oracle Cloud Free Tier VM

    
---

## 🛠️ Technology Stack

### Cloud Infrastructure

- Oracle Cloud Free Tier
- Linux Virtual Machine
- Networking & Security Rules

### Containerization

- Docker
- Docker Compose

### Web Infrastructure

- Nginx
- SSL/TLS Certificates
- Reverse Proxy

### Applications

- Wiki.js
- PostgreSQL
- Gitea
- Uptime Kuma
- Vaultwarden
- Jenkins

### Documentation

- Markdown
- Wiki.js
- GitHub Documentation

---

## 📂 Repository Structure

```text
personal-cloud/
│
├── assets/
│   ├── diagrams/
│   └── images/
│
├── backups/
│
├── docker/
│   ├── wiki/
│   ├── postgres/
│   ├── nginx/
│   ├── gitea/
│   ├── uptime-kuma/
│   ├── vaultwarden/
│   └── jenkins/
│
├── docs/
│
├── nginx/
│
├── scripts/
│
├── docker-compose.yml
├── .env.example
└── README.md

---

# 🎯 Roadmap

## Phase 1 — Foundation

✅ Create repository structure

⬜ Design architecture

⬜ Document deployment process


## Phase 2 — Cloud Infrastructure

⬜ Create Oracle Cloud Free Tier account

⬜ Provision Virtual Machine

⬜ Configure firewall rules

⬜ Install Docker


## Phase 3 — Wiki Platform

⬜ Deploy PostgreSQL

⬜ Deploy Wiki.js

⬜ Configure authentication

⬜ Configure backups


## Phase 4 — Production Improvements

⬜ Configure Nginx reverse proxy

⬜ Enable HTTPS

⬜ Add monitoring

⬜ Security hardening


## Phase 5 — Additional Services

⬜ Gitea

⬜ Uptime Kuma

⬜ Vaultwarden

⬜ Jenkins

---

# 🔐 Security Approach

Security practices planned for this environment:

- SSH key authentication
- Firewall configuration
- Least privilege access
- Environment variable management
- Regular backups
- Service isolation using Docker containers
- HTTPS encryption

---

# 💾 Backup Strategy

The platform will include:

- Database backups
- Configuration backups
- Docker volume backups
- Recovery documentation

Backup and restoration procedures will be documented in:

- `docs/backup.md`
- `docs/restore.md`


---

# 📚 Documentation

Detailed documentation will be maintained throughout the project:

- Architecture decisions
- Deployment guides
- Troubleshooting notes
- Security practices
- Lessons learned

---

# 📌 Project Status

🚧 Currently under development

The infrastructure is being built step-by-step while documenting each decision and implementation detail.

---

## 👨‍💻 Author

Michael Jackson Ndueso

QA Engineer | SDET | Test Automation Specialist

GitHub:
https://github.com/Jevmis