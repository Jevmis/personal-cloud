# Security Guide - Michael J. Ndueso Personal Cloud

## Overview

Security is a core design principle of this project. The goal is to protect the server, applications, and data while following practical DevOps and cloud security best practices.

---

# Security Objectives

The platform is designed to:

- Protect the Oracle Cloud server
- Secure user authentication
- Encrypt network traffic
- Protect application data
- Prevent unauthorized access
- Maintain recoverable backups

---

# Server Security

## Operating System

- Ubuntu LTS
- Regular system updates
- Minimal installed packages

---

## User Accounts

Planned approach:

- Create a non-root administrator account
- Use `sudo` only when required
- Avoid daily use of the root account

---

## SSH Security

SSH access will use:

- SSH key authentication
- Strong passphrase-protected keys
- Password authentication disabled (after confirming key-based access)
- Root login disabled

---

# Network Security

Only the following ports will be exposed publicly:

| Port | Purpose |
|------|---------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |

All other ports will remain blocked.

---

# Docker Security

Each service will run inside its own Docker container.

Benefits include:

- Service isolation
- Easier updates
- Simpler backups
- Reduced attack surface

---

# Reverse Proxy Security

Nginx will:

- Handle HTTPS
- Redirect HTTP to HTTPS
- Forward traffic only to approved services

---

# SSL/TLS

Certificates will be issued using Let's Encrypt.

Goals:

- Encrypt all traffic
- Protect login credentials
- Improve browser trust

---

# Secrets Management

Sensitive information will never be committed to GitHub.

Examples include:

- Database passwords
- API keys
- SSH private keys
- Environment variables

Secrets will be stored using `.env` files that are excluded from Git.

---

# Backup Security

Backups will include:

- PostgreSQL database
- Docker volumes
- Configuration files

Backups should be stored separately from the running server whenever possible.

---

# Update Strategy

Regular maintenance tasks include:

- Operating system updates
- Docker image updates
- Wiki.js updates
- PostgreSQL updates
- Security patch reviews

---

# Incident Response

If a security issue is detected:

1. Restrict public access if necessary.
2. Review logs.
3. Restore from backups if required.
4. Patch the vulnerability.
5. Document the incident and lessons learned.

---

# Security Checklist

- [ ] SSH keys configured
- [ ] Password login disabled
- [ ] Firewall configured
- [ ] HTTPS enabled
- [ ] Automatic backups configured
- [ ] Docker images updated regularly
- [ ] Secrets excluded from Git
- [ ] Monitoring enabled

---

# Document Status

**Status:** Planning Phase

**Last Updated:** July 2026
