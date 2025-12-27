
---

```md
# 🚀 Jenkins CI/CD Pipeline with Docker & AWS EC2

## 📌 Project Overview
This project demonstrates a complete end-to-end CI/CD pipeline using **Jenkins**, **Docker**, and **AWS EC2**.
Every code push to GitHub automatically triggers the pipeline, builds a Docker image, pushes it to Docker Hub,
and deploys the application on an AWS EC2 instance.

This project follows real-world DevOps best practices and is fully automated.

---

## 🧱 Architecture Overview
GitHub → Jenkins → Docker Build → Docker Hub → AWS EC2 → Live Application

---

## 🛠️ Tech Stack
- Jenkins (CI/CD Automation)
- Docker (Containerization)
- AWS EC2 (Deployment)
- Python (Flask Web Application)
- GitHub (Source Code Management)

---

## ⚙️ CI/CD Pipeline Stages
- **Clone** – Pulls latest code from GitHub
- **Docker Build** – Builds Docker image
- **Docker Push** – Pushes image to Docker Hub
- **Deploy** – Runs the container on AWS EC2

---

## 🔔 Automation Trigger
- GitHub Webhook
- Pipeline is triggered automatically on every `git push`
- No manual intervention required

---

## 📂 Project Structure
```

cicd/
├── app.py
├── requirements.txt
├── Dockerfile
├── Jenkinsfile
└── templates/
└── index.html

```

---

## 🐍 Python Application
- Flask-based web application
- Serves an HTML frontend
- Runs on port `5000`
- Containerized using Docker

---

## 🐳 Docker Configuration
- Uses `python:3.10-slim` base image
- Installs dependencies inside Docker container
- Avoids system-level Python issues (PEP 668 compliant)

---

## 🔐 Security Best Practices
- Docker Hub credentials stored securely in Jenkins Credentials Manager
- No hardcoded secrets in Jenkinsfile
- Secure Docker login using `--password-stdin`

---

## 🚀 Deployment
- Application deployed on AWS EC2
- Docker container exposed on port `80`
- Application accessible via EC2 public IP

```

http://<EC2_PUBLIC_IP>

```

---

## 📸 Screenshots

### 🔹 Jenkins Pipeline – Successful Build
<img width="1897" height="869" alt="Jenkins Pipeline Success" src="https://github.com/user-attachments/assets/8e42920c-aba4-49a6-9077-a71c1dbfb66d" />

This shows the successful execution of all Jenkins pipeline stages triggered automatically by GitHub webhook.

---

### 🔹 Docker Image Pushed to Docker Hub
<img width="965" height="732" alt="Docker Hub Image" src="https://github.com/user-attachments/assets/c50b67fd-c1f0-4781-95e6-5417ed697e6a" />

Confirms that Jenkins successfully built and pushed the Docker image to Docker Hub.

---

### 🔹 Running Docker Container on AWS EC2
<img width="1895" height="226" alt="Docker Container Running" src="https://github.com/user-attachments/assets/90b0bed1-3c1d-42da-94f8-413335779cec" />

Shows the running Docker container on the AWS EC2 instance.

---

### 🔹 Application Live on Browser
<img width="953" height="536" alt="Application Live" src="https://github.com/user-attachments/assets/eb370f51-c9cc-423d-aec1-2effb281448e" />

The Flask application is live and accessible via the EC2 public IP, confirming successful deployment.

---

## 🎯 Key Learnings
- Jenkins Declarative Pipelines
- GitHub Webhooks for automation
- Docker & Jenkins integration
- Secure credential management
- AWS EC2 deployment
- End-to-end CI/CD automation

---

## 💬 Interview-Ready Explanation
“I built an automated Jenkins CI/CD pipeline that pulls code from GitHub, builds and pushes Docker images to Docker Hub, and deploys the application automatically on AWS EC2.”

---

## 👤 Author
**Varshith Chand**  
Aspiring DevOps Engineer 🚀

---

⭐ If you found this project useful, consider starring the repository!
```

---

