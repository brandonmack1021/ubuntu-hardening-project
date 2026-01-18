# Ubuntu Hardening & Security Configuration


## Project Overview

This project documents the process of hardening and securing an existing Ubuntu Linux installation.

The goal

---

## Hardening Steps

1.  Update and Upgrade the System

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

2. Enable Firewall (UFW)

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

3. Enable Automatic Security Updates

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

4. Install Security Tools

- Install monitoring and intrusion detection tools using sudo apt install fail2ban ufw rkhunter chkrootkit lynis.

    • Run a system audit with sudo lynis audit system.

    • Helps detect potential threats and monitor system security.

    Disk Encryption (Optional)

    • Install encryption tools with sudo apt install cryptsetup.

    • Use LUKS for encrypting disks (best done at installation for full-disk encryption).

    • Protects sensitive data in case the device is lost or stolen.

    Disable Unnecessary Services

    • List all system services using sudo systemctl list-unit-files --type=service.

    • Stop unwanted services with sudo systemctl stop <service> and prevent them from starting at boot using sudo systemctl disable <service>.

    • Reduces the system attack surface by only running required services.

    Browser & Application Security

    • Install Firejail to sandbox applications using sudo apt install firejail.

    • Run Firefox in a sandbox with firejail firefox.

    • Limits potential damage if an application is compromised.

    Enable Two-Factor Authentication (Google Authenticator)

    • Install the Google Authenticator PAM module with sudo apt install libpam-google-authenticator.

    • Configure your user for 2FA using google-authenticator.

    • Adds an extra layer of login security beyond passwords.

Optional Notes

    Always backup important data before applying system hardening.

    Avoid pushing sensitive files (like private keys or passwords) to GitHub.

    This repository can serve as a template for future Ubuntu installations.

