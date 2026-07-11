# Networking Guide - Michael J. Ndueso Personal Cloud

## Overview

This document describes the networking architecture for the Michael J. Ndueso Personal Cloud platform.

The objective is to securely expose selected services to the internet while keeping internal communication isolated.

---

# Network Overview

```text
                Internet
                    |
                    |
        michaeljndueso.is-a.dev
                    |
                    |
           Oracle Cloud Public IP
                    |
                    |
             Security List / Firewall
                    |
                    |
          Nginx Reverse Proxy
                    |
          -----------------------
          |                     |
      Wiki.js             Future Services
          |
          |
     PostgreSQL
```

---

# DNS

Planned domain:

```
michaeljndueso.is-a.dev
```

DNS will point to:

- Oracle Cloud Public IP

---

# Public Services

The following services will be accessible from the internet:

| Service | Access |
|----------|--------|
| Wiki.js | HTTPS |
| Nginx | HTTP / HTTPS |

Additional services may be exposed later through Nginx.

---

# Internal Services

The following services will not be exposed directly:

| Service | Public Access |
|----------|---------------|
| PostgreSQL | No |
| Docker Network | No |

Communication will occur only through Docker's internal networking.

---

# Firewall Rules

Planned inbound rules:

| Port | Protocol | Purpose |
|------|----------|----------|
| 22 | TCP | SSH |
| 80 | TCP | HTTP |
| 443 | TCP | HTTPS |

All unnecessary ports will remain closed.

---

# Docker Networking

Docker Compose will create a private bridge network.

Example:

```text
Internet
     |
Nginx Container
     |
Docker Network
     |
-----------------------
|                     |
Wiki.js          PostgreSQL
```

---

# Reverse Proxy

Nginx responsibilities:

- Accept incoming traffic
- Redirect HTTP to HTTPS
- Route requests to Wiki.js
- Support future services

---

# SSL

HTTPS certificates will be issued using Let's Encrypt.

Benefits:

- Encrypted communication
- Browser trust
- Secure authentication

---

# Future Expansion

Possible future subdomains:

| Subdomain | Service |
|-----------|---------|
| wiki.michaeljndueso.is-a.dev | Wiki.js |
| git.michaeljndueso.is-a.dev | Gitea |
| status.michaeljndueso.is-a.dev | Uptime Kuma |
| vault.michaeljndueso.is-a.dev | Vaultwarden |

---

# Networking Checklist

- [ ] Oracle Public IP assigned
- [ ] DNS configured
- [ ] Firewall configured
- [ ] Nginx installed
- [ ] HTTPS enabled
- [ ] Internal Docker networking verified

---

# Document Status

**Status:** Planning Phase

**Last Updated:** July 2026