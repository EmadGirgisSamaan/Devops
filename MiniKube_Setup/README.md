# MiniKube Setup Guide

This folder contains comprehensive MiniKube installation and configuration guides for different Linux distributions using Docker driver.

## 📋 Contents

| File | Description |
|------|-------------|
| `MiniKube_CentOS_Rocky_docker_driver.txt` | Complete MiniKube setup guide for CentOS/RHEL/Rocky Linux with Docker driver |
| `MiniKube_Ubuntu_Debian_docker_driver.txt` | Complete MiniKube setup guide for Ubuntu/Debian with Docker driver |

## 🚀 Quick Start

### Prerequisites
- Docker installed and running
- At least 2 CPUs
- Minimum 2GB RAM (4GB recommended)
- Virtualization enabled in BIOS

### For CentOS/RHEL/Rocky:
```bash
# Install Docker first (see Docker_Setup folder)
sudo dnf install -y yum-utils
sudo dnf config-manager --add-repo=https://download.docker.com/linux/centos/docker-ce.repo
sudo dnf install docker-ce docker-ce-cli containerd.io

# Install MiniKube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-latest.x86_64.rpm
sudo rpm -Uvh minikube-latest.x86_64.rpm

# Start MiniKube with Docker driver
minikube start --driver=docker --nodes=2

# For Ubuntu/Debian:
####################
# Install Docker first (see Docker_Setup folder)
sudo apt update
sudo apt install docker.io docker-compose

# Install MiniKube
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube

# Start MiniKube with Docker driver
minikube start --driver=docker --nodes=2

# 📝 What's Included
#####################
    + Docker Installation: Container runtime setup
    + MiniKube Installation: Installing MiniKube binary
    + Cluster Configuration: Setting up Kubernetes cluster
    + Multi-Node Setup: Configuring 2-node cluster
    + kubectl Configuration: Kubernetes command-line tool setup
    + Driver Configuration: Using Docker as the driver
# 🔧 Configuration Steps:
#########################
1. Install Docker
-----------------
Ensure Docker is installed and running before installing MiniKube.

2. Install MiniKube
-------------------
Download and install the latest MiniKube release for your distribution.

3. Start MiniKube Cluster
-------------------------
# Start with Docker driver and 2 nodes
minikube start --driver=docker --nodes=2

# Specify resources (optional)
minikube start --driver=docker --cpus=4 --memory=4096

4. Configure kubectl
--------------------
# Set MiniKube as kubectl context
minikube kubectl -- get pods -A

# Create alias for easier access
alias kubectl='minikube kubectl --'

5. Verify Installation
----------------------
# Check cluster status
minikube status

# List nodes
kubectl get nodes

# View all pods
kubectl get pods -A


#🔧 Useful Commands
####################

==> Cluster Management
----------------------
# Start cluster
minikube start

# Stop cluster
minikube stop

# Delete cluster
minikube delete

# Pause cluster
minikube pause

# Resume cluster
minikube unpause

# kubectl Commands
##################

# Get all pods
kubectl get pods -A

# Get services
kubectl get services

# Get nodes
kubectl get nodes

# Describe pod
kubectl describe pod <pod-name> -n <namespace>

# View logs
kubectl logs <pod-name> -n <namespace>

# MiniKube Specific
###################

# Access Kubernetes dashboard
minikube dashboard

# SSH into MiniKube VM
minikube ssh

# Get IP address
minikube ip

# Check logs
minikube logs

# 📌 Important Notes
#####################
    + Docker Driver: Uses Docker containers to run Kubernetes nodes (recommended for development)
    + Multi-Node: This guide sets up a 2-node cluster for testing high availability
    + Resources: Adjust CPU and memory allocation based on your system capabilities
    + Persistent Storage: Use minikube mount for persistent volumes in development
    + Add User to Docker Group:
bash
sudo usermod -aG docker $USER
newgrp docker

# 🐛 Troubleshooting
#####################
Common Issues
1. Permission Denied with Docker
-------------------------------
# Add user to docker group
sudo usermod -aG docker $USER
newgrp docker

2. MiniKube Won't Start
-----------------------
# Delete and recreate
minikube delete
minikube start --driver=docker

# Check logs
minikube logs

3. kubectl Connection Refused
-----------------------------

# Update context
minikube update-context

# Verify cluster status
minikube status

4. Insufficient Resources
-------------------------
# Start with fewer resources
minikube start --driver=docker --cpus=2 --memory=2048

# 🔐 Security Best Practices
#############################
    + Don't expose MiniKube dashboard publicly
    + Use RBAC for production-like testing
    + Regularly update MiniKube to latest version
    + Don't run containers as root in pods
    + Scan images before deployment

# 📚 Additional Resources
##########################
    + Official MiniKube Documentation
    + Kubernetes Documentation
    + MiniKube GitHub Repository
    + Docker Driver Documentation
    + kubectl Cheat Sheet

# 🎯 Next Steps
################
Deploy your first application
Learn about Kubernetes objects (Pods, Services, Deployments)
Practice with ConfigMaps and Secrets
Explore Ingress and LoadBalancers
Study Persistent Volumes and Storage

# 👤 Author
###########
Emad Gerges Samaan
DevOps Engineer
Last Updated: 2026



