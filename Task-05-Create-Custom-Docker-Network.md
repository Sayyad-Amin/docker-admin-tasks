# Create a Custom Docker Network

## Task
The Nautilus DevOps team is planning to set up Docker containers on **App Server 3** in Stratos Datacenter.  
Before deploying the containers, some prerequisites need to be completed:

- Create a new Docker network named **`mysql-network`**.
- Use the **bridge** driver.
- Allocate subnet: `182.18.0.0/24`
- Configure gateway: `182.18.0.1`

---

## Solution

### Step 1: Create the Network
```bash
docker network create \
  --driver bridge \
  --subnet 182.18.0.0/24 \
  --gateway 182.18.0.1 \
  mysql-network
