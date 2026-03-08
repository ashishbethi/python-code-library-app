**Python Code Library App**

A containerized Python microservices application that provides a simple library management system.
The project demonstrates how to build, scan, and deploy a multi-service Python application using Jenkins, Trivy, Sonar, Docker Swarm



**Detailed Project Info:**

•	Implemented an end-to-end CI/CD pipeline using Jenkins to automate build, security scanning, and deployment of a Python microservices application.
•	Integrated SonarQube for static code analysis to detect bugs, vulnerabilities, and maintain code quality.
•	Built Docker images for multiple microservices including authentication, book management, borrow service, and database components.
•	Implemented container security scanning using Trivy to identify vulnerabilities in Docker images before deployment.
•	Automated Docker image tagging and publishing to Docker Hub using Jenkins pipeline credentials.
•	Deployed the containerized application using Docker Stack with a compose configuration for service orchestration.
•	Integrated with new relic tool to monitor cpu, memory, storage, network usage of master, slave nodes of docker swarm and containers hosted in it to ensure high availability.



**🏗 Project Architecture**

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

                
**📂 Project Structure**

python-code-library-app
│
├── auth/           # Authentication microservice
├── book/           # Book management service
├── borrow/         # Borrow service
├── database/       # Database service
├── compose.yml     # Docker Compose file
├── Dockerfile      # Main application Dockerfile
└── README.md

**The project includes a Jenkins pipeline that automates:**

1️⃣ Code checkout from GitHub
2️⃣ Code quality analysis (SonarQube)
3️⃣ Docker image build
4️⃣ Security scanning (Trivy)
5️⃣ Image tagging
6️⃣ Push images to DockerHub
7️⃣ Deployment using Docker Stack


