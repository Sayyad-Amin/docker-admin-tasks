# 📝 Task 04 – Copy Files Into and From a Running Container

## 📌 Objective
Understand how to securely copy files **into a running container** and how to **copy files out of a container** using the `docker cp` command.

---

## 🔹 Copy File From Host → Container

### Syntax 
bash
docker cp <local_path> <container_name>:/path/in/container/ 

### 📂 Real-World Scenario (Nautilus DevOps)

The Nautilus DevOps team possesses confidential data on App Server 1 in the Stratos Datacenter.
A container named ubuntu_latest is running on the same server.

### Task:
Copy an encrypted file located at /tmp/nautilus.txt.gpg on the Docker host to the /opt/ directory inside the container. The file must be transferred without any modification.

### Solution:

docker cp /tmp/nautilus.txt.gpg ubuntu_latest:/opt/



