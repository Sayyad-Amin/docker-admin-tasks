# 🐳 Task 01 – Install Docker Packages and Start Docker Service

## 📌 Objective
Learn how to install Docker on a Linux system, verify the installation, and start the Docker service.

---

## 🔹 Step 1: Update Package Index
Always update the package list before installation:

**On CentOS / RHEL**

sudo yum update -y

**On Ubuntu / Debian**

sudo apt update -y

## Step 2: Install Required Dependencies

**CentOS / RHEL**

sudo yum install -y yum-utils device-mapper-persistent-data lvm2


**Ubuntu / Debian**

sudo apt install -y apt-transport-https ca-certificates curl software-properties-common

## 🔹 Step 3: Add Docker Repository

**CentOS / RHEL**

sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo


**Ubuntu / Debian**

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"

## 🔹 Step 4: Install Docker Packages


**CentOS / RHEL**

sudo yum install -y docker-ce docker-ce-cli containerd.io


**Ubuntu / Debian**

sudo apt install -y docker-ce docker-ce-cli containerd.io

## 🔹 Step 5: Start and Enable Docker Service

sudo systemctl start docker
sudo systemctl enable docker


## Verify the status:

systemctl status docker

## 🔹 Step 6: Verify Installation

Check the Docker version:

## docker --version


## Run a test container:

sudo docker run hello-world



