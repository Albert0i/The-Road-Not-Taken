# 🚀 WinBoat Tutorial on Zorin OS 18: Fixing Docker & Permission Issues

This tutorial will guide you through diagnosing your Docker installation, removing problematic versions, reinstalling Docker + Docker Compose the correct way, and finally verifying that everything works so WinBoat runs smoothly on **Zorin OS 18**.

---

## 🔍 Step 1: Check Your Current Docker Installation
Run these commands to see how Docker was installed:

```bash
snap list | grep docker
dpkg -l | grep docker
which docker
docker --version
```

- **Snap version** → shows up in `snap list` or path `/snap/bin/docker`  
- **Apt/DEB version** → shows up in `dpkg -l` or path `/usr/bin/docker`  

👉 If you see Snap, that’s the source of most permission problems.

---

## 🧹 Step 2: Remove Existing Docker
Depending on what you found:

- **Snap version:**
  ```bash
  sudo snap remove docker
  ```
- **Apt version:**
  ```bash
  sudo apt-get purge docker-ce docker-ce-cli containerd.io docker-compose-plugin
  sudo apt-get autoremove -y
  ```

Clean up leftovers:
```bash
sudo rm -rf /var/lib/docker
sudo rm -rf /var/lib/containerd
```

---

## 📦 Step 3: Install Docker CE (Official Method)
Add Docker’s official repository and install:

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg lsb-release -y

sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
```

---

## 👥 Step 4: Fix Permissions
Add your user to the `docker` group:

```bash
sudo groupadd docker   # may already exist
sudo usermod -aG docker $USER
newgrp docker
```

---

## 🛠 Step 5: Install Docker Compose (Non-Snap)
If you need the standalone `docker-compose` binary:

```bash
sudo curl -L "https://github.com/docker/compose/releases/download/v2.27.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```

---

## ✅ Step 6: Verify Docker & Docker Compose Work
Run these test commands:

```bash
docker run hello-world
```

Expected output:  
- A message saying *“Hello from Docker!”*  
- Confirmation that your installation works.

Then test Docker Compose:

```bash
mkdir ~/compose-test && cd ~/compose-test
cat <<EOF > docker-compose.yml
version: "3.9"
services:
  web:
    image: nginx:alpine
    ports:
      - "8080:80"
EOF

docker-compose up -d
docker-compose ps
```

Expected output:  
- A running container named `compose-test_web_1`  
- Accessible at `http://localhost:8080` showing the default Nginx welcome page.

---

## 🚤 Step 7: Run WinBoat
Now you can safely run WinBoat with Docker Compose:

```bash
cd ~/.winboat
docker-compose up -d
```

No more **permission denied** errors — Compose can access your directories, and your user has Docker group rights.

---

## 🧾 Troubleshooting Checklist
- **Error: Permission denied** → Ensure you ran `usermod -aG docker $USER` and restarted your session.  
- **Error: Cannot access ~/.winboat/** → Confirm you removed the Snap version of Docker Compose.  
- **Error: docker-compose not found** → Reinstall using the curl method above.  
- **Containers won’t start** → Check logs with `docker-compose logs`.

---
