# 🚀 Flask DevOps CI/CD Pipeline Project

## 🌍 Project Goal

This project demonstrates an end-to-end **DevOps CI/CD pipeline implementation** using a simple Flask application.

The purpose is to understand how modern DevOps systems automatically:

* Build application containers
* Push images to container registry
* Deploy application containers
* Enable automation through CI/CD pipelines

---

## 🧱 Project Architecture

```
Developer (Local Machine)
        ↓
     Git Push
        ↓
     GitHub Repository
        ↓
 GitHub Actions CI Runner (Temporary VM)
        ↓
 Docker Image Build
        ↓
 Push Image to Docker Hub
        ↓
 Run Container (CD Practice Deployment)
```

---

## 🛠️ Technology Stack

| Tool           | Purpose                 |
| -------------- | ----------------------- |
| Flask          | Backend Web Application |
| Docker         | Containerization        |
| Git            | Version Control         |
| GitHub         | Code Hosting            |
| GitHub Actions | CI/CD Automation        |
| Docker Hub     | Container Registry      |

---

## 📦 Application Overview

A minimal Flask application that runs inside a Docker container.

**Endpoint:**

```
GET /
```

**Response Example:**

```
Hello DevOps World 🚀
```

---

## 🐳 Docker Implementation

### Dockerfile Responsibilities

* Pull Python base image
* Copy application files
* Install dependencies
* Expose port 5000
* Run Flask server

### Build Command

```
docker build -t ravindra2sf/flask-app .
```

### Push Command

```
docker push ravindra2sf/flask-app
```

---

## ⚙️ Continuous Integration (CI)

CI pipeline automatically triggers when code is pushed to the `main` branch.

### CI Steps

1. Checkout repository code
2. Build Docker image
3. Authenticate with Docker Hub
4. Push image to Docker Hub

This ensures:

* No manual builds
* Consistent deployment artifact
* Automated verification

---

## 🚀 Continuous Deployment (CD) — Learning Phase

Pipeline also runs container inside GitHub Runner.

Example deployment command:

```
docker run -d -p 5000:5000 ravindra2sf/flask-app
```

⚠️ This deployment is **temporary**, because:

* GitHub Runner VM is destroyed after pipeline execution.

This phase helps understand deployment automation fundamentals.

---

## 🔐 Secrets Management

Docker Hub credentials are stored securely using GitHub Secrets:

* `DOCKER_USER`
* `DOCKER_PASS`

This avoids exposing sensitive data inside code.

---

## 📊 Pipeline Trigger Example

```
git add .
git commit -m "CI test"
git push
```

This will automatically start CI/CD workflow.

---

## 🧠 Key DevOps Learnings

* CI trigger lifecycle understanding
* Temporary cloud runner concept
* Docker image versioning & digest awareness
* Pipeline debugging using logs
* Automation verification strategies
* Container lifecycle management

---

## 📈 Next Project Phases (Planned)

* Deploy container on AWS EC2
* Introduce Docker Compose
* Kubernetes Deployment & Scaling
* Monitoring with Prometheus & Grafana
* Blue-Green Deployment Strategy

---

## 📷 Recommended Enhancements

* Add GitHub Actions pipeline screenshot
* Add Docker Hub repository link
* Add architecture diagram image
* Add status badges

