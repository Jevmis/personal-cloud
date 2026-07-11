# Michael J. Ndueso Personal Cloud Architecture ☁️

## Overview

This document describes the architecture design for the Michael J. Ndueso Personal Cloud platform.

The platform is designed as a self-hosted infrastructure environment running on Oracle Cloud Free Tier.

The main goals are:

- Host personal documentation
- Maintain a QA engineering knowledge base
- Run development and automation services
- Practice cloud infrastructure management
- Apply DevOps and security best practices

---

# High-Level Architecture

```text
                         Users
                           |
                           |
                      Internet
                           |
                           |
                    DNS Domain
          (michaeljndueso.is-a.dev)
                           |
                           |
                  Nginx Reverse Proxy
                           |
              -------------------------
              |          |            |
              |          |            |
           Wiki.js    Services    Monitoring
              |
              |
         PostgreSQL Database
              |
              |
            Docker
              |
              |
      Oracle Cloud Free Tier VM

      ```markdown
---

# Infrastructure Layer

## Cloud Provider

Provider:

Oracle Cloud Infrastructure (OCI)

Purpose:

- Host the virtual machine
- Provide networking
- Provide public IP access
- Run Docker services

---

# Compute Layer

## Virtual Machine

The server will use an Oracle Cloud Always Free Compute Instance.

Planned configuration:

| Component | Value |
|---|---|
| Provider | Oracle Cloud |
| Operating System | Ubuntu Linux |
| Container Platform | Docker |
| Deployment Method | Docker Compose |
| Access Method | SSH |

---

# Container Layer

All applications will run as isolated Docker containers.

Planned services:

## Wiki.js

Purpose:

- Personal knowledge base
- QA documentation
- Engineering notes
- Learning journal

Container:

wiki

---

## PostgreSQL

Purpose:

Database engine for Wiki.js.

Container:

postgres

Relationship:
Wiki.js
|
|
PostgreSQL


---

## Nginx

Purpose:

- Reverse proxy
- Route incoming traffic
- Handle SSL certificates
- Manage HTTPS access

Container:

nginx

Traffic flow:
nginx
User
|
HTTPS
|
Nginx
|
Application Container


---

# Additional Services

Future services planned:

## Gitea

Purpose:

Self-hosted Git repository platform.

---

## Uptime Kuma

Purpose:

Service monitoring and uptime tracking.

---

## Vaultwarden

Purpose:

Self-hosted password manager.

---

## Jenkins

Purpose:

CI/CD experimentation and automation pipelines.

---

# Network Architecture

## External Access

Users access the platform through:

michaeljndueso.is-a.dev

Traffic:
Internet
|
|
Public IP
|
|
Nginx
|
|
Docker Services


---

# Security Design

Security controls planned:

## Server Access

- SSH key authentication
- Disable password login
- Limited user permissions

---

## Network Security

Required ports:

| Port | Purpose |
|---|---|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |

Unused ports will remain closed.

---

## Application Security

Practices:

- Environment variables for secrets
- No credentials stored in Git
- Regular updates
- Container isolation
- Backup strategy

---

# Data Storage

Persistent data will be stored using Docker volumes.

Example:

Docker Container
    |
    |
Docker Volume
    |
    |
Persistent Storage

Important data:

- Wiki.js content
- PostgreSQL database
- Application configurations

---

# Backup Architecture

Backup targets:

- PostgreSQL database
- Docker volumes
- Configuration files
- Environment settings

Backup location:
backups/

---

# Deployment Flow

The planned deployment process:

1. Create Oracle Cloud VM
2. Configure networking
3. Install Docker
4. Configure Docker Compose
5. Deploy PostgreSQL
6. Deploy Wiki.js
7. Configure Nginx
8. Enable HTTPS
9. Configure backups
10.Add monitoring


---

# Future Improvements

Possible future additions:

- Infrastructure as Code (Terraform)
- Automated deployments
- CI/CD pipelines
- Log management
- Security scanning
- Disaster recovery testing

---

# Document Status

Status:

Planning Phase
Last Updated:
July 2026

