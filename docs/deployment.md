# Deployment Guide - Michael J. Ndueso Personal Cloud ☁️

## Overview

This document describes the planned deployment process for the Michael J. Ndueso Personal Cloud platform.

The deployment will use:

- Oracle Cloud Free Tier
- Ubuntu Linux
- Docker
- Docker Compose
- Nginx
- Wiki.js
- PostgreSQL

---

# Deployment Phases

The deployment will be completed in stages:

1. Cloud Infrastructure Setup
2. Server Configuration
3. Docker Installation
4. Database Deployment
5. Wiki.js Deployment
6. Reverse Proxy Configuration
7. HTTPS Configuration
8. Backup Setup
9. Monitoring Setup

---

# Phase 1 — Oracle Cloud Setup

## Create Cloud Account

Provider:
Oracle Cloud Infrastructure


Tasks:

- Create Free Tier account
- Select home region
- Configure identity verification
- Access OCI Console

---

# Phase 2 — Create Virtual Machine

Planned server:

| Component | Configuration |
|---|---|
| Provider | Oracle Cloud |
| OS | Ubuntu Linux |
| Access | SSH |
| Container Runtime | Docker |

Tasks:

- Create compute instance
- Assign public IP
- Configure SSH access
- Configure firewall rules

---

# Phase 3 — Server Preparation

Initial server tasks:

- Update packages
- Create deployment user
- Configure SSH security
- Install required tools

Required packages:

- Git
- Docker
- Docker Compose
- Nginx

---

# Phase 4 — Docker Environment

Docker will manage all application services.

Planned containers:
wiki
postgres
nginx
uptime-kuma
gitea
vaultwarden
jenkins


Services will be managed using:

docker-compose.yml


---

# Phase 5 — Database Deployment

Deploy PostgreSQL container.

Responsibilities:

- Store Wiki.js data
- Maintain application state
- Provide database persistence

Requirements:

- Persistent Docker volume
- Secure database credentials
- Regular backups

---

# Phase 6 — Wiki.js Deployment

Deploy Wiki.js container.

Configuration:

- Connect to PostgreSQL
- Create administrator account
- Configure storage
- Enable authentication

---

# Phase 7 — Domain and Reverse Proxy

Domain:
michaeljndueso.is-a.dev


Traffic flow:
User
|
HTTPS
|
Nginx
|
Wiki.js
|
PostgreSQL


---

# Phase 8 — HTTPS Configuration

SSL will be configured using:
Let's Encrypt


Goals:

- Enable HTTPS
- Secure user communication
- Automatic certificate renewal

---

# Phase 9 — Backup Configuration

Backup targets:

- PostgreSQL database
- Docker volumes
- Configuration files

Backup schedule:

To be defined after deployment.

---

# Phase 10 — Monitoring

Monitoring service:
Uptime Kuma


Purpose:

- Monitor service availability
- Track uptime
- Detect failures

---

# Deployment Status

Current Status:
Planning Phase


Next milestone:
Oracle Cloud VM provisioning
