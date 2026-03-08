📚 Python Code Library App

A containerized Python microservices application that provides a simple library management system.
The project demonstrates how to build, scan, and deploy a multi-service Python application using Docker, DevSecOps tools, and CI/CD pipelines.

This repository is designed for learning DevOps practices such as containerization, security scanning, and automated deployment.

🚀 Features

📖 Library management system

🔐 Authentication service

📚 Book management service

📦 Borrow management service

🗄 Database service

🐳 Containerized using Docker

🔎 Security scanning with Trivy

📊 Code quality analysis with SonarQube

⚙️ CI/CD pipeline using Jenkins

📦 Docker image registry integration

🏗 Project Architecture

The application is built using a microservices architecture.

                +-------------+
                |   Frontend  |
                +------+------+
                       |
                       v
                +-------------+
                |  App Service|
                +------+------+ 
                       |
   -----------------------------------------
   |               |              |
   v               v              v
+-------+     +--------+     +---------+
| Auth  |     |  Book  |     | Borrow  |
|Service|     |Service |     | Service |
+---+---+     +---+----+     +----+----+
    |             |              |
    --------------------------------
                     |
                     v
                +---------+
                |Database |
                +---------+
📂 Project Structure
python-code-library-app
│
├── auth/           # Authentication microservice
├── book/           # Book management service
├── borrow/         # Borrow service
├── database/       # Database service
├── compose.yml     # Docker Compose file
├── Dockerfile      # Main application Dockerfile
└── README.md
🐳 Running the Application with Docker
1️⃣ Clone the repository
git clone https://github.com/ashishbethi/python-code-library-app.git
cd python-code-library-app
2️⃣ Build Docker images
docker build -t dbimage database/
docker build -t authimage auth/
docker build -t bookimage book/
docker build -t borrowimage borrow/
docker build -t appimage .
3️⃣ Run the application

Using Docker Compose:

docker-compose up -d
🔐 Security Scanning

The project integrates Trivy to scan Docker images for vulnerabilities.

Example:

trivy image appimage
📊 Code Quality Analysis

Static code analysis is performed using SonarQube to ensure high code quality and security.

Example scanner command:

sonar-scanner -Dsonar.projectKey=MyProject
⚙️ CI/CD Pipeline

The project includes a Jenkins pipeline that automates:

1️⃣ Code checkout from GitHub
2️⃣ Code quality analysis (SonarQube)
3️⃣ Docker image build
4️⃣ Security scanning (Trivy)
5️⃣ Image tagging
6️⃣ Push images to DockerHub
7️⃣ Deployment using Docker Stack

📦 Docker Images

Images are pushed to DockerHub repository:

ashbethi10/myproj

Services include:

dbimage

authimage

bookimage

borrowimage

appimage

🛠 Tech Stack

Python

Docker

Docker Compose

Jenkins

SonarQube

Trivy

GitHub

Python is widely used for automation and DevOps workflows, making it suitable for building backend services and operational tooling.

🎯 Learning Objectives

This project demonstrates:

Microservices architecture

Containerization using Docker

DevSecOps practices

CI/CD pipeline implementation

Container security scanning

Automated deployments

🤝 Contributing

Contributions are welcome.

Steps:

Fork the repository

Create a feature branch

Commit changes

Push your branch

Open a Pull Request
