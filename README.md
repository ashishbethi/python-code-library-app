**Python Code Library App**

A containerized Python microservices application that provides a simple library management system.<br>
The project demonstrates how to build, scan, and deploy a multi-service Python application using Jenkins, Trivy, Sonar, Docker Swarm<br>



**Detailed Project Info:** <br>

•	Implemented an end-to-end CI/CD pipeline using Jenkins to automate build, security scanning, and deployment of a Python microservices application. <br>
•	Integrated SonarQube for static code analysis to detect bugs, vulnerabilities, and maintain code quality. <br>
•	Built Docker images for multiple microservices including authentication, book management, borrow service, and database components. <br>
•	Implemented container security scanning using Trivy to identify vulnerabilities in Docker images before deployment. <br>
•	Automated Docker image tagging and publishing to Docker Hub using Jenkins pipeline credentials. <br>
•	Deployed the containerized application using Docker Stack with a compose configuration for service orchestration. <br>
•	Integrated with new relic tool to monitor cpu, memory, storage, network usage of master, slave nodes of docker swarm and containers hosted in it to ensure high availability.<br>

                
**📂 Project Structure** <br>

<img width="452" height="242" alt="image" src="https://github.com/user-attachments/assets/f2ac2246-1d5c-4a83-9f47-e4006caf57ce" />


**The project includes a Jenkins pipeline that automates:** <br>

1️⃣ Code checkout from GitHub <br>
2️⃣ Code quality analysis (SonarQube) <br>
3️⃣ Docker image build <br>
4️⃣ Security scanning (Trivy) <br>
5️⃣ Image tagging <br>
6️⃣ Push images to DockerHub <br>
7️⃣  Deployment using Docker Stack <br>
 

