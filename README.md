# task-7-devops

✅ TASK 7: Monitor System Resources Using Netdata
🎯 Objective
Install and run Netdata using Docker to monitor real-time system metrics like:

CPU, memory, disk, network

Docker containers (if any)

View a dashboard and take a screenshot

🧱 Step-by-Step Instructions (Start to Finish)
🐳 1. Prerequisites
You need:

Ubuntu instance (local or cloud like AWS)

Docker installed

If Docker is not installed:
Run this:

bash
Copy
Edit
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable --now docker
sudo usermod -aG docker $USER
Log out and back in again to apply group changes (or use newgrp docker).

🚀 2. Run Netdata Container
Start Netdata using Docker:

bash
Copy
Edit
docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
This does the following:

Runs Netdata in detached mode (-d)

Maps port 19999 on host to container

Allows system-level monitoring with required permissions

🌐 3. Access the Netdata Dashboard
In your browser, go to:

Edit
http://<your-server-ip>:19999
Replace <your-server-ip> with your actual IP address (e.g., from AWS or localhost)

✅ You should see the Netdata real-time monitoring dashboard

📸 4. Take Screenshot
Take a screenshot of:

The Netdata dashboard showing CPU, RAM, and Disk metrics

Any charts or alerts

📁 5. Prepare GitHub Repository
Create a new GitHub repo called something like netdata-monitoring

Add:

Screenshot(s)

A README.md file

📘 Sample README.md
markdown
Copy
Edit
# 🖥️ System Monitoring with Netdata (Docker)

## 📌 Task
This project demonstrates how to monitor real-time system and Docker resource metrics using **Netdata**, a lightweight monitoring tool.

## 🛠 Tools Used
- Netdata (Docker container)
- Ubuntu Server
- Web browser (to access dashboard)

## 🔧 How to Run

1. Make sure Docker is installed and running:
```bash
sudo apt update
sudo apt install docker.io -y
Start Netdata container:

bash
Copy
Edit
docker run -d --name=netdata -p 19999:19999 \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
Open the dashboard:


Copy
Edit
http://<your-server-ip>:19999
📊 What I Monitored
CPU usage

Memory (RAM)

Disk I/O

Docker container metrics

System performance alerts

📸 Screenshot

✅ Outcome
Successfully deployed Netdata in Docker and explored real-time monitoring features.

