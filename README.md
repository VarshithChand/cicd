Got it 👍
Below is a **PLAIN `README.md`** — **no explanations, no extra text**.
Just **copy–paste directly** into your GitHub repository.

---

```md
# 🚀 Jenkins CI/CD Pipeline with Docker & AWS EC2

## 📌 Project Overview
This project demonstrates a complete CI/CD pipeline using Jenkins, Docker, and AWS EC2.
Every code push to GitHub automatically triggers the pipeline to build, push, and deploy
a Python Flask application.

---

## 🧱 Architecture

GitHub → Jenkins → Docker Build → Docker Hub → AWS EC2 → Live Application

---

## 🛠️ Tech Stack
- Jenkins
- Docker
- AWS EC2
- Python (Flask)
- GitHub

---

## ⚙️ Pipeline Stages
- Clone source code from GitHub
- Build Docker image
- Push image to Docker Hub
- Deploy container on AWS EC2

---

## 🔔 Automation Trigger
- GitHub Webhook
- Pipeline runs automatically on every `git push`

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
- Serves an HTML page
- Runs on port 5000
- Containerized using Docker

---

## 🐳 Docker Configuration
- Python 3.10 slim base image
- Dependencies installed inside Docker container
- Avoids system-level Python conflicts

---

## 🔐 Security Best Practices
- Docker Hub credentials stored in Jenkins Credentials Manager
- No hardcoded secrets in Jenkinsfile
- Secure Docker login using `--password-stdin`

---

## 🚀 Deployment
The application is deployed on AWS EC2 and exposed on port 80.

Access the app:
```

http://<EC2_PUBLIC_IP>

```

---

## 🎯 Key Learnings
- Jenkins Declarative Pipeline
- GitHub Webhooks
- Docker & Jenkins integration
- CI/CD automation
- AWS EC2 deployment

---

## 💬 Interview Explanation
"I built an automated Jenkins CI/CD pipeline that pulls code from GitHub, builds and pushes Docker images, and deploys the application automatically on AWS EC2."

---

## 👤 Author
Varshith Chand

