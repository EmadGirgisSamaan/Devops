# Docker Setup Guide

This folder contains comprehensive Docker installation and configuration guides for different Linux distributions.

## 📋 Contents

| File | Description |
|------|-------------|
| `Docker_Setup_Ubuntu.txt` | Complete Docker installation guide for Ubuntu/Debian systems |
| `Docker_Setup_Centos_RedHat.txt` | Complete Docker installation guide for CentOS/RHEL/Rocky Linux systems |

##  Quick Start

### For Ubuntu/Debian:
######################
```bash
# Follow the steps in Docker_Setup_Ubuntu.txt
sudo apt update
sudo apt install gnupg apt-transport-https ca-certificates curl software-properties-common

# For CentOS/RHEL/Rocky:
#########################
# Follow the steps in Docker_Setup_Centos_RedHat.txt
sudo yum update
sudo yum install -y yum-utils

# What's Included
#################
    + Prerequisites Installation: Required packages and dependencies
    + Docker Repository Setup: Adding official Docker repositories
    + Docker CE Installation: Installing Docker Community Edition
    + Post-Installation Configuration:
       - Adding user to docker group
       - Enabling Docker service on boot
       - Verifying installation
    + Basic Commands: Testing Docker installation

# 🔧 Post-Installation Steps
#############################
After installation, verify Docker is running:
# Check Docker version
docker --version

# Check Docker service status
sudo systemctl status docker

# Test Docker installation
docker run hello-world

# Verify Docker Compose
docker compose version

# 📌 Important Notes
#####################

     + Always use official Docker repositories for production environments
     + Add your user to the docker group to run Docker commands without sudo
     + Keep Docker updated to the latest stable version
     + Configure Docker daemon settings in /etc/docker/daemon.json if needed

# 🔐 Security Best Practices
#############################
     + Regularly update Docker to patch security vulnerabilities
     + Use Docker Content Trust for image verification
     + Scan images for vulnerabilities before deployment
     + Avoid running containers as root user

# 📚 Additional Resources
##########################

     + Official Docker Documentation
     + Docker Hub
     + Docker Security Best Practices

# 👤 Author
############
Emad Gerges Samaan
DevOps Engineer
Last Updated: 06/2026
