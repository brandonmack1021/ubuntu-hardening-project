# Ubuntu Hardening Commands

## Step 1: Update and Upgrade the System
sudo apt update
sudo apt upgrade -y
sudo apt dist-upgrade -y
sudo apt autoremove -y

## Step 2: Create a Non-Root User
sudo adduser yourusername
sudo usermod -aG sudo yourusername
sudo passwd -l root

## Step 3: Enable Firewall (UFW)
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow ssh # or your chosen SSH port
sudo ufw enable
sudo ufw status verbose

## Step 4: Secure SSH
# Edit /etc/ssh/sshd_config as follows:
# PermitRootLogin no
# PasswordAuthentication no
# AllowUsers yourusername
# Port 2222 # optional
sudo systemctl restart ssh

## Step 5: Enable Automatic Security Updates
sudo apt install unattended-upgrades
sudo dpkg-reconfigure --priority=low unattended-upgrades

## Step 6: Install Security Tools
sudo apt install fail2ban ufw rkhunter chkrootkit lynis
sudo lynis audit system

## Step 7: Disk Encryption (Optional)
sudo apt install cryptsetup

## Step 8: Disable Unnecessary Services
sudo systemctl list-unit-files --type=service
sudo systemctl stop <service>
sudo systemctl disable <service>

## Step 9: Browser & Application Security
sudo apt install firejail
firejail firefox

## Step 10: Enable Two-Factor Authentication (Google Authenticator)
sudo apt install libpam-google-authenticator
google-authenticator
