# cybersecurity-task-14
Linux Server Hardening &amp; Secure Configuration

## Overview
This project demonstrates the process of hardening a Linux system to reduce its attack surface and secure it against common threats. The system was reviewed and configured using security best practices such as least privilege, defense in depth, and service minimization.

The hardening process focused on user management, SSH security, firewall configuration, service auditing, and system monitoring.

---

## Objectives
- Review default system users, services, and open ports
- Restrict user and sudo privileges
- Secure SSH access using best practices
- Configure a firewall with a default-deny policy
- Disable unnecessary services
- Verify secure system state through audits and logs

---

## Environment
- **Operating System:** Kali Linux
- **Tools Used:**
  - `systemctl`
  - `ss`
  - `ufw`
  - `nano`
  - OpenSSH

---

## Step-by-Step Hardening Summary

### 1. User Account Review
- Reviewed all system users with valid login shells
- Disabled interactive login for service accounts (e.g., database users)
- Ensured only required user accounts can authenticate
- Restricted sudo access based on least privilege

---

### 2. SSH Hardening
- Disabled root login via SSH
- Enforced key-based authentication
- Disabled password-based authentication
- Restarted and verified SSH service after configuration

---

### 3. Network Port and Service Audit
- Reviewed listening ports using `ss -tulnp`
- Identified unnecessary exposed services
- Removed Apache web server
- Ensured database services were bound to localhost only
- Verified SSH as the only externally accessible service

---

### 4. Firewall Configuration (UFW)
- Enabled UFW firewall
- Set default policy to deny incoming traffic
- Allowed SSH (port 22) for remote administration
- Explicitly denied insecure services such as FTP (port 21)
- Removed unused firewall rules
- Enabled firewall logging
- Applied rules for both IPv4 and IPv6 traffic

---

### 5. Service Hardening
- Audited enabled and running services using `systemctl`
- Disabled unnecessary background and network services
- Verified only essential system and security services remain active
- Reduced total running services to a minimal, secure set

---

### 6. System Verification
- Verified running services state
- Confirmed firewall rules and default policies
- Ensured only required services are exposed
- Reviewed system and authentication logs for anomalies

---

## Final System State
- Only SSH is exposed for remote access
- Firewall enforces default-deny inbound policy
- Unnecessary services and ports removed
- Service accounts restricted from login
- System running minimal required services

---

## Security Configuration Summary
The Linux system was hardened by enforcing least privilege, minimizing running services, securing SSH access, and implementing a host-based firewall. The attack surface was significantly reduced by disabling unnecessary services and restricting network exposure. Logging and monitoring were enabled to support detection and auditing.

---

## Final Outcome
- Improved resistance against brute-force and network-based attacks
- Reduced system attack surface
- Enforced secure administrative access
- Applied industry-aligned Linux hardening practices

---

## Conclusion
This task demonstrates the ability to secure a Linux system against common attack vectors through systematic hardening, service minimization, and secure configuration. The system now follows best practices suitable for production and security-focused environments.

---
