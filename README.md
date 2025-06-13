# Enterprise Java CI/CD with GitOps and Kubernetes Observability

## Overview

This project demonstrates a complete CI/CD pipeline for a Java-based microservice using industry-standard DevOps practices and tools. It includes source code management with GitHub, continuous integration using Jenkins, code quality checks with SonarQube, containerization and image pushing to Amazon ECR, GitOps deployment with Argo CD, and observability through Prometheus and Grafana.

---

## 🔧 Tools & Technologies

- **Java (Spring Boot)**: Backend application
- **Maven**: Build tool
- **Jenkins**: CI/CD pipeline
- **SonarQube**: Code quality scanning
- **Docker**: Containerization
- **Amazon ECR**: Container image repository
- **Amazon EKS**: Kubernetes hosting
- **Argo CD**: GitOps-based deployment
- **Prometheus & Grafana**: Monitoring and observability
- **GitHub**: Source code and manifest repositories

---

## 🏗️ Architecture
![Image](https://github.com/user-attachments/assets/be62eaf7-0da0-47cd-ab9b-34e2dd0b1262)

1. Developers push code to **GitHub**
2. A **webhook** triggers the **Jenkins** pipeline
3. Jenkins:
   - Builds the project using **Maven**
   - Analyzes code with **SonarQube**
   - Builds and tags Docker images
   - Pushes image to **Amazon ECR**
   - Updates the GitOps repo (manifests) with the new image tag
4. **Argo CD** detects Git changes and syncs to **Amazon EKS**
5. **Prometheus** scrapes metrics and **Grafana** visualizes performance dashboards

---

## 📂 Project Structure

```bash
.
├── spring-boot-app/                 # Java application
│   └── src/
├── Jenkinsfile                      # CI/CD pipeline definition
├── gitops/                          # GitOps repo (manifest repo)
│   ├── deployment.yaml              # Kubernetes deployment
│   ├── service.yaml                 # Kubernetes service
│   └── argocd-app.yaml              # Argo CD application
└── README.md                        # Project documentation
