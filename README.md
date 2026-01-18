# Ubuntu Hardening & Security Configuration

## Project Overview
This project documents the process of hardening and securing a fresh Ubuntu Linux installation.
The goal is to demonstrate practical system security and administration skills, including firewall setup, automatic updates, application sandboxing, and multi-factor authentication.

---

## Environment
- **Operating System:** Ubuntu LTS 25.10.
- **Hardware:** Laptop (bare-metal installation) or Virtual Machine.
- **Installation Method:** Built on top of the previous project(linux-ubuntu-deployment).
- **Tools & Utilities:** Bash, UFW (Uncomplicated Firewall), Fail2Ban, Lynis, RKHunter & Chkrootkit, Firejail, Google Authenticator (libpam-google-authenticator).

---

## Objectives
- Apply security best practices to a fresh Ubuntu installation
- Enable and configure the firewall to restrict incoming connections
- Enable automatic security updates to reduce vulnerability exposure
- Install and configure security monitoring tools for intrusion detection
- Disable unnecessary services to reduce the system attack surface
- Secure applications using sandboxing tools like Firejail
- Install auditd tto monitor system events
- Enable two-factor authentication (2FA) for additional login security

