# 🚀 Flask + MongoDB CI/CD Pipeline

A containerized Flask + MongoDB web application with a complete CI/CD pipeline using **GitHub Actions, Docker, Docker Hub, and AWS EC2**.

The project automates the process from code push to application deployment.

---

## 📌 Project Overview

This project demonstrates how a Flask application can be:

- Version controlled using Git and GitHub
- Containerized using Docker
- Automatically validated using GitHub Actions
- Built into a Docker image
- Published to Docker Hub
- Automatically deployed to an AWS EC2 instance
- Connected to MongoDB through a Docker network

### 🔄 CI/CD Flow

```text
Developer
    │
    │ git push
    ▼
GitHub Repository
    │
    ▼
GitHub Actions
    │
    ├── Checkout Code
    ├── Setup Python
    ├── Install Dependencies
    ├── Python Syntax Check
    ├── Build Docker Image
    ├── Login to Docker Hub
    ├── Tag Docker Image
    └── Push Docker Image
             │
             ▼
        Docker Hub
             │
             ▼
       SSH into AWS EC2
             │
             ├── Pull Latest Image
             ├── Stop Old Container
             ├── Remove Old Container
             └── Start New Container
                     │
                     ▼
              Flask Container
                     │
                     ▼
              MongoDB Container
