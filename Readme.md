# 🚀 Resume Project - Jenkins CI/CD Pipeline

This project demonstrates a complete **CI/CD Pipeline** using:

- GitHub
- Jenkins
- SonarQube
- Docker
- AWS EC2

The goal of this project is to automate the process of:

✅ Pulling code from GitHub  
✅ Building and testing the application  
✅ Running code quality analysis with SonarQube  
✅ Building Docker images  
✅ Deploying the application automatically  

---

# 🏗️ Architecture

```text
Developer → GitHub → Jenkins → SonarQube → Docker → Deployment
```

---

# ⚙️ Tech Stack

| Tool | Purpose |
|------|----------|
| GitHub | Source Code Management |
| Jenkins | CI/CD Automation |
| SonarQube | Code Quality & Static Analysis |
| Docker | Containerization |
| AWS EC2 | Hosting Jenkins & Deployment |
| HTML/CSS/JS | Sample Application |

---

# 📁 Project Structure

```bash
.
├── index.html
├── README.md
├── Dockerfile
└── Jenkinsfile
```

---

# 🔥 Features

- Automated CI/CD Pipeline
- Dockerized Application
- Jenkins Pipeline as Code
- SonarQube Integration
- Auto Deployment
- GitHub Integration

---

# 🖥️ Jenkins Pipeline Flow

## 1️⃣ Pull Source Code

Jenkins pulls the latest code from GitHub repository.

---

## 2️⃣ Build Stage

Application is prepared for deployment.

Example:

```bash
echo "Building Application..."
```

---

## 3️⃣ SonarQube Analysis

Code quality and vulnerabilities are checked using SonarQube.

---

## 4️⃣ Docker Build

Docker image is created.

```bash
docker build -t resume-project .
```

---

## 5️⃣ Docker Deployment

Container is deployed automatically.

```bash
docker run -d -p 80:80 resume-project
```

---

# 🐳 Docker Setup

## Build Image

```bash
docker build -t resume-project .
```

## Run Container

```bash
docker run -d -p 80:80 resume-project
```

---

# ☁️ AWS EC2 Setup

## Install Docker

```bash
sudo apt update
sudo apt install docker.io -y
```

## Start Docker

```bash
sudo systemctl start docker
sudo systemctl enable docker
```

---

# 🔧 Jenkins Setup

## Install Jenkins

```bash
sudo apt update
sudo apt install openjdk-17-jdk -y
```

```bash
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
```

```bash
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
```

```bash
sudo apt update
sudo apt install jenkins -y
```

---

# 🔑 Access Jenkins

```text
http://YOUR_EC2_PUBLIC_IP:8080
```

Get initial admin password:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

---

# 📦 Example Jenkins Pipeline

```groovy
pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git 'YOUR_GITHUB_REPO_URL'
            }
        }

        stage('Build') {
            steps {
                echo 'Building Application...'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                echo 'Running SonarQube Analysis...'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t resume-project .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 80:80 resume-project'
            }
        }
    }
}
```

---

# 📸 Screenshots

Add screenshots here:

- Jenkins Dashboard
- SonarQube Report
- Docker Container Running
- Successful Pipeline

---

# 🚀 Future Improvements

- Add Kubernetes Deployment
- Add ArgoCD
- Add Monitoring with Prometheus & Grafana
- Add Automated Testing
- Add Blue-Green Deployment

---

# 👨‍💻 Author

Abhijit Kumar

---

# ⭐ Conclusion

This project demonstrates a real-world DevOps CI/CD workflow using Jenkins, Docker, SonarQube, and AWS EC2.

It helps understand:
- CI/CD concepts
- Pipeline automation
- Docker deployment
- DevOps best practices

---