# VPS Setup

If you want to set up a production ready VPS, there are a few steps you should take.

This document goes through the list of steps that I personally take.


## 1. Create a New User with Sudo Permissions
```bash
# Log in as root
ssh root@your-server-ip

# Create a new user
adduser newuser

# Add the user to the sudo group
usermod -aG sudo newuser

# Test the new user
su - newuser
sudo apt update
```


## 2. Set Up SSH Key Authentication
```bash
# On your local machine, generate an SSH key pair if you don’t already have one
ssh-keygen -t ed25519 -C "your_email@example.com"

# Copy the SSH key to the new user on the server
ssh-copy-id -i ~/.ssh/id_ed25519.pub newuser@your-server-ip

# Test key-based login
ssh newuser@your-server-ip
```

## 3. Harden SSH

```bash
# Open SSH configuration file
sudo nano /etc/ssh/sshd_config

# Modify the following in the file:
# PermitRootLogin no # Disable root login
# PasswordAuthentication no  # Disable password based auth

# Restart SSH service
sudo systemctl restart ssh

# Test SSH with new settings before logging out
ssh newuser@your-server-ip
```

## 4. Set Up a Firewall (UFW)
```bash
# Install UFW if not already installed
sudo apt install ufw

# Allow necessary ports
sudo ufw allow OpenSSH    # SSH
sudo ufw allow 80/tcp     # HTTP
sudo ufw allow 443/tcp    # HTTPS

# Enable UFW
sudo ufw enable

# Check UFW status
sudo ufw status
```

## 4. CrowdSec

[CrowdSec](https://doc.crowdsec.net/u/getting_started) is a modernized, collaborative, and scalable security solution. It is a behavior-based security engine that continuously monitors your logs for malicious behavior.

```bash
curl -s https://install.crowdsec.net | sudo sh
apt install crowdsec
sudo apt install crowdsec-firewall-bouncer-iptables
```

### Check the status of the service

```bash
sudo systemctl status crowdsec
```

**View bans**

```bash
sudo cscli decisions list
```