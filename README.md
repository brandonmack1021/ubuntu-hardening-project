# Ubuntu Hardening & Security Configuration

## Project Overview
This project documents the process of hardening and securing a fresh Ubuntu Linux installation.
The goal is to demonstrate practical system security and administration skills, including firewall setup, SSH hardening, automatic updates, user management, application sandboxing, and multi-factor authentication.

---

## Environment
- **Operating System:** Ubuntu LTS
- **Hardware:** Laptop (bare-metal installation) or Virtual Machine
- **Installation Method:** Bootable USB or fresh ISO installation (refer to my linux-ubuntu-deployment repository)
- **Tools & Utilities:**
- Bash
- UFW (Uncomplicated Firewall)
- Fail2Ban
- Lynis
- RKHunter & Chkrootkit
- Firejail
- Google Authenticator (libpam-google-authenticator)
- Git

---

## Objectives
- Apply security best practices to a fresh Ubuntu installation
- Create and configure a non-root user for daily use
- Enable and configure the firewall to restrict incoming connections
- Harden SSH access, including disabling root login and enforcing key-based authentication
- Enable automatic security updates to reduce vulnerability exposure
- Install and configure security monitoring tools for intrusion detection
- Disable unnecessary services to reduce the system attack surface
- Secure applications using sandboxing tools like Firejail
- Enable two-factor authentication (2FA) for additional login security

---

## Notes
- Always backup important data before applying system hardening
- Avoid pushing sensitive files (like private keys or passwords) to GitHub
- This repository can serve as a template for future Ubuntu installations
