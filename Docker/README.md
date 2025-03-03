# Docker
Docker is a container-based virtualization technology that allows applications to run in a lightweight and consistent environment.

### **Key Advantages of Docker**
- **Portability**: Runs consistently across different OS and infrastructures.
- **Lightweight**: Uses fewer resources compared to virtual machines.
- **Scalability**: Easily deploy and scale multiple containers.
- **Fast Deployment**: Enables quick application deployment and rollback.
- **Consistency**: Ensures identical environments across development, testing, and production stages.
---
## Table of Contentss
- [Installing Docker](#installing-docker)
- [Logging into Docker](#logging-into-docker)
- [Writing a Dockerfile](dockerfile)
---

## Installing Docker
Docker is available for Windows, macOS, and Linux. Below is the installation process for Ubuntu.

### **Installing Docker on Ubuntu**
```bash
sudo apt update
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

### **Verifying the Installation**
```bash
docker --version
```
Check if Docker is running:
```bash
sudo systemctl status docker
```

---

## Logging into Docker
Logging into Docker Hub allows you to manage container images easily.

```bash
docker login
```
Enter your Docker Hub credentials when prompted.

To verify the login status:
```bash
docker info | grep Username
```
