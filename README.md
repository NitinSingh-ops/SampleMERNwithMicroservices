# Sample MERN with Microservices on AWS EKS

## Project Overview

This project demonstrates the deployment of a MERN-based microservices application using Docker, Amazon Elastic Container Registry (ECR), Amazon Elastic Kubernetes Service (EKS), Kubernetes, Jenkins, and Helm.

The application consists of:

* Frontend (React)
* Hello Service (Node.js + Express)
* Profile Service (Node.js + Express + MongoDB)
* MongoDB Database

The project was completed as part of the **Hero Vired - Multi Cloud Architecture & DevOps Program**.

---

# Project Architecture

```
                User
                  │
                  ▼
        AWS LoadBalancer Service
                  │
                  ▼
          React Frontend (Pod)
                  │
       ┌──────────┴──────────┐
       ▼                     ▼
 Hello Service         Profile Service
                              │
                              ▼
                          MongoDB
```

---

# Technologies Used

* React
* Node.js
* Express.js
* MongoDB
* Docker
* Docker Hub / Amazon ECR
* Kubernetes
* Amazon EKS
* Helm
* Jenkins
* AWS CLI
* Git & GitHub

---

# Project Structure

```
SampleMERNwithMicroservices/

├── backend/
│   ├── helloService/
│   └── profileService/
│
├── frontend/
│
├── k8s/
│   ├── frontend-deployment.yaml
│   ├── frontend-service.yaml
│   ├── hello-deployment.yaml
│   ├── hello-service.yaml
│   ├── profile-deployment.yaml
│   ├── profile-service.yaml
│   ├── mongodb-deployment.yaml
│   └── mongodb-service.yaml
│
├── sample-mern-chart/
│
├── Jenkinsfile
│
└── README.md
```

---

# Docker Images

Docker images were built for:

* frontend
* hello-service
* profile-service

Example:

```bash
docker build -t frontend ./frontend

docker build -t hello-service ./backend/helloService

docker build -t profile-service ./backend/profileService
```

---

# Amazon ECR

Docker images were pushed to Amazon ECR.

Repositories:

* frontend
* hello-service
* profile-service

Example:

```bash
docker push <account-id>.dkr.ecr.ap-south-1.amazonaws.com/frontend:latest
```

---

# Jenkins Pipeline

A Jenkins Pipeline was created to automate:

* Git checkout
* Docker image build
* Docker image push
* Kubernetes deployment

Pipeline file:

```
Jenkinsfile
```

---

# Amazon EKS Cluster

Cluster Name

```
sample-mern
```

Node Group

```
workers
```

Region

```
ap-south-1
```

---

# Kubernetes Deployment

Deployments created:

* Frontend Deployment
* Hello Service Deployment
* Profile Service Deployment
* MongoDB Deployment

Services created:

* Frontend LoadBalancer Service
* Hello Service ClusterIP
* Profile Service ClusterIP
* MongoDB ClusterIP

Deploy using:

```bash
kubectl apply -f k8s/
```

Verify:

```bash
kubectl get nodes

kubectl get pods

kubectl get deployments

kubectl get services
```

---

# Helm

A Helm chart was created for the application.

Commands:

```bash
helm create sample-mern-chart

helm install sample-mern sample-mern-chart

helm list
```

---

# AWS Services Used

* Amazon EC2
* Amazon ECR
* Amazon EKS
* Elastic Load Balancer
* CloudFormation
* CloudWatch
* IAM

---

# Learning Outcomes

This project helped in understanding:

* Microservices Architecture
* Docker Containerization
* Dockerfile Creation
* Amazon ECR
* Kubernetes Deployments
* Kubernetes Services
* Helm Charts
* Jenkins CI/CD Pipeline
* Amazon EKS Cluster Management
* Cloud Native Application Deployment

---

# GitHub Repository

```
https://github.com/NitinSingh-ops/SampleMERNwithMicroservices
```

---

# Author

**Nitin Prakash Singh**

Windows Server Administrator | DevOps Learner

Hero Vired – Multi Cloud Architecture & DevOps Program

2026
