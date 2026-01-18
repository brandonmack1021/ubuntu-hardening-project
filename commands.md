# Ubuntu Hardening & Security Configuration


## Project Overview

This project documents the process of hardening and securing an existing Ubuntu Linux installation.

The goal

---

## Hardening Steps

### 1.  Update and Upgrade the System

- Open Terminal
- Run the following commands to update and upgrade all packages:
    
    ```bash 
    sudo apt update && sudo apt upgrade -y
    ```
    
    ```bash
    sudo apt dist-upgrade -y
    ```
    
    ```bash
    sudo apt autoremove -y
    ```
**Notes**
- These commands will ensure your system is fully patched and up to date

### 2. Enable Firewall (UFW)

- Set default firewall policies
   
   ```bash
   sudo ufw default deny incoming
   ```

  ```bash
  sudo ufw default allow outgoing.
   ```

```bash
sudo ufw enable
```

```bash
sudo ufw status verbose
```
**Notes** 
- 

### 3. Enable Automatic Security Updates

- Install unattended upgrades:

```bash
sudo apt install unattended-upgrades
```

- Configure automatic updates:

```bash
sudo dpkg-reconfigure --priority=low unattended-upgrades
```

**Notes**

- Running these commands will automatically keeps the system patched which will help by reducing exposure to vulnerabilities.

### 4. Install Security Tools

- Install monitoring and intrusion detection tools:

```bash
sudo apt install fail2ban ufw rkhunter chkrootkit lynis
```

- Run a system audit with sudo lynis audit system:

```bash
sudo lynis audit system
```
**Notes**
- fail2ban: blocks IPs after multiple failed login attempts
- rkhunter/chrootkit: scans for rootkits
- lynis: security auditing tool

### 5. Disk Encryption (Optional)

- Install encryption tools:

```bash
sudo apt install cryptsetup
```

**Notes** 
- Use LUKS for encrypting disks (best done at installation for full-disk encryption).
- Protects sensitive data in case the device is lost or stolen.

### 6. Disable Unnecessary Services

- List all system services:
```bash
sudo systemctl list-unit-files --type=service
```

- Stop services you dont need:
```bash
sudo systemctl stop <service>
```
- Prevent them from starting at boot:
```bash
sudo systemctl disable <service>
```

**Notes**
- The <service> section gets replaces with the service name from the list that you want to stop or disable.
- Reduces the system attack surface by only running required services.

### 7. Browser & Application Security

- Install Firejail to sandbox applications:

```bash
sudo apt install firejail
```

- Run Firefox in a sandbox
```bash
firejail firefox
```

**Notes** 
- Limits potential damage if an application is compromised.


### 8. Advanced Hardening (Optional)

- Install and enable auditd:
```bash
sudo apt install auditd
```

```bash
sudo systemctl enable auditd
```

```bash
sudo systemctl start auditd
```

- Consider two-factor authentication for logins:

```bash
sudo apt install libpam-google-authenticator
```
```bash
google-authenticator
```
 
**Notes** 
- Use auditd to monitor system events.
- using two-factor authentication adds an extra layer of login security beyond passwords.

---

## **Final Notes**

- Always backup important data before applying system hardening.

- Avoid pushing sensitive files (like private keys or passwords) to GitHub.

- This repository can serve as a template for future Ubuntu installations.

- This project was intended to build off of my linux-ubuntu-deployment project.

- These steps are intended to provide **basic security hardening** for a personal Ubuntu system.

- While they significantly reduce the attack surface, they do not represent an exhaustive or enterprise-level security configuiration.


