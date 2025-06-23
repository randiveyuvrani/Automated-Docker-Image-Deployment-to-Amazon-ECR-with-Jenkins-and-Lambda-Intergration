# 🚀 Automated Docker Image Deployment to Amazon ECR with Jenkins and Lambda Integration

This project demonstrates an end-to-end CI/CD pipeline for deploying a Flask web application in a Docker container using **GitHub**, **Jenkins**, and **Amazon ECR**. The app is hosted on an **EC2 instance**, and Jenkins automates the Docker image build and container deployment process.

## 🧱 Tech Stack

- Flask (Python Web App)
- Docker
- Jenkins (CI/CD)
- Amazon EC2 (for hosting Jenkins and app)
- Amazon ECR (for storing Docker images)
- GitHub (for version control)

---

## 🛠️ Prerequisites

1. An AWS EC2 instance with:
   - Docker installed
   - Jenkins running on port `8080`
   - Port `8000` open for Flask app

2. GitHub repository with:
   - `app.py` (Flask app)
   - `Dockerfile`
   - `Jenkinsfile`

---

## 📂 Project Structure

```bash
.
├── app.py
├── Dockerfile
├── Jenkinsfile
└── README.md
---

## 👨‍💻 Author

**Yuvrani Sanjay Randive**  
🚀 Project #4 Completed  
📧 Email: yuvranirandive1@gmail.com  
🔗 GitHub: [@randiveyuvrani](https://github.com/randiveyuvrani)

---


