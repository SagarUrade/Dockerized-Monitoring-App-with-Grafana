# 🚀 DevOps Mini Project: Dockerized Monitoring App with Grafana

A beginner-friendly DevOps project that demonstrates how to build, containerize, deploy, and monitor a web application using Docker, Prometheus, and Grafana.

---

# 📌 Project Overview

This project helps you understand core DevOps concepts and workflow using:

- Linux
- Git
- GitHub
- Docker
- Prometheus
- Grafana

The application is containerized using Docker and monitored using Prometheus and Grafana dashboards.

---

---

# 🛠️ Tools & Technologies Used

| Tool | Purpose |
|------|----------|
| Linux | Server environment |
| Git | Version control |
| GitHub | Code hosting |
| Docker | Containerization |
| Docker Compose | Multi-container management |
| Prometheus | Metrics collection |
| Grafana | Monitoring & visualization |
| Nginx | Web server |

---

---

# ⚙️ Step-by-Step Setup

## 1️⃣ Clone Repository

```bash
git clone https://github.com/SagarUrade/Dockerized-Monitoring-App-with-Grafana.git
```

---

## 2️⃣ Install Required Tools

### Update System

```bash
sudo apt update && sudo apt upgrade -y
```

### Install Git

```bash
sudo apt install git -y
```

### Install Docker

```bash
sudo apt install docker.io -y
```

### Start Docker

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

### Verify Installation

```bash
git --version
docker --version
```

---

# 🌐 Web Application

## app/index.html

```
https://github.com/SagarUrade/Dockerized-Monitoring-App-with-Grafana/blob/develop/app/index.html

```

---

# 🐳 Dockerfile

## app/Dockerfile

```dockerfile
FROM nginx:latest

COPY index.html /usr/share/nginx/html/index.html
```

---

# 📊 Prometheus Configuration

## prometheus/prometheus.yml

```yaml
global:
  scrape_interval: 5s

scrape_configs:
  - job_name: "prometheus"
    static_configs:
      - targets: ["prometheus:9090"]

  - job_name: "docker-app"
    static_configs:
      - targets: ["app:80"]
```

---

# 🐙 Docker Compose Configuration

## docker-compose.yml

```yaml
version: '3'

services:

  app:
    build: ./app
    container_name: monitoring-app
    ports:
      - "8080:80"

  prometheus:
    image: prom/prometheus
    container_name: prometheus
    ports:
      - "9090:9090"
    volumes:
      - ./prometheus/prometheus.yml:/etc/prometheus/Prometheus.yml

  grafana:
    image: grafana/grafana
    container_name: grafana
    ports:
      - "3000:3000"
```

---

# ▶️ Run Project

## Start Containers

```bash
docker compose -f docker-compose.yml up -d
```

## Check Running Containers

```bash
docker ps
```

---

# 🌍 Access Applications

| Service | URL |
|----------|-----|
| Web App | http://localhost:8080 |
| Prometheus | http://localhost:9090 |
| Grafana | http://localhost:3000 |

---

# 📈 Configure Grafana

## Login Credentials

```text
Username: admin
Password: admin
```

---

## Add Prometheus Data Source

### Go To:

```text
Connections → Data Sources → Add Data Source
```

### Select:

```text
Prometheus
```

### Add URL:

```text
http://prometheus:9090
```

### Click:

```text
Save & Test
```

---

# 📊 Example Grafana Metrics

## Check Container Status

```promql
up
```

## CPU Usage

```promql
rate(container_cpu_usage_seconds_total[1m])
```

## Memory Usage

```promql
container_memory_usage_bytes
```

---

# 🔄 DevOps Workflow

```text
Write Code
   │
   ▼
Git Commit
   │
   ▼
Push to GitHub
   │
   ▼
Pull on Linux Server
   │
   ▼
Build Docker Image
   │
   ▼
Run Containers
   │
   ▼
Prometheus Collects Metrics
   │
   ▼
Grafana Visualizes Data
```

---

# 📚 Key Learning Outcomes

| Concept | Learning |
|----------|----------|
| Linux | Server management |
| Git | Version control |
| GitHub | Repository hosting |
| Docker | Application containerization |
| Docker Compose | Multi-container orchestration |
| Prometheus | Metrics monitoring |
| Grafana | Dashboard visualization |
| DevOps Workflow | Deployment & monitoring pipeline |

---

---

# 🧠 Real-World DevOps Concepts Covered

✅ Containerization  
✅ Monitoring & Visualization  
✅ Infrastructure Basics  
✅ Git Workflow  
✅ Linux Administration  
✅ Docker Networking  
✅ Multi-Container Deployment  
✅ DevOps Lifecycle Understanding  

---


```

---

# 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Push to branch
5. Open Pull Request

---

# 📄 License

This project is open-source and available under the MIT License.

---

# 👨‍💻 Author

Sagar Urade

- GitHub: https://github.com/SagarUrade
- LinkedIn: Sagar Urade

---

# ⭐ Support

If you found this project useful:

⭐ Star the repository  
🍴 Fork the project  
📢 Share with others  

---