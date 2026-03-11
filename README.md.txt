# End-to-End DevOps CI/CD Pipeline using Kubernetes on AWS

This project demonstrates a complete DevOps pipeline that automates the process of building, containerizing, and deploying an application using Kubernetes on AWS.

The application is deployed on Amazon EKS and exposed to the internet using a Kubernetes LoadBalancer service.

## Technologies Used

- Docker
- GitHub Actions
- Amazon ECR
- Amazon EKS
- Kubernetes
- Flask (Python)

##Architecture Diagram

Developer
   ↓
GitHub Repository
   ↓
GitHub Actions CI/CD
   ↓
Docker Build
   ↓
Amazon ECR
   ↓
Amazon EKS Cluster
   ↓
Kubernetes Deployment
   ↓
Kubernetes LoadBalancer Service
   ↓
Public Web Application

## Workflow

1. Developer pushes application code to GitHub.
2. GitHub Actions pipeline automatically triggers.
3. Docker image is built from the application code.
4. The image is pushed to Amazon Elastic Container Registry (ECR).
5. Kubernetes deployment pulls the image from ECR.
6. Pods are created inside the Amazon EKS cluster.
7. The application is exposed using a Kubernetes LoadBalancer service.

## Kubernetes Commands Used

Create EKS cluster:
     eksctl create cluster --name mohan-devops-cluster --region us-east-1
Deploy application:
     kubectl apply -f flask-deploy.yaml
Create service:
     kubectl apply -f flask-service.yaml
Check pods:
     kubectl get pods
Check services:
     kubectl get svc

## Challenges Faced

ImagePullBackOff error due to incorrect Docker image tag.

Pods stuck in Pending state because node resources were insufficient.

YAML indentation errors during Kubernetes deployment.

Prometheus monitoring stack required higher memory than available in t3.micro nodes.


## Skills Demonstrated

CI/CD pipeline automation

Containerization using Docker

Kubernetes orchestration

AWS cloud infrastructure

Debugging and troubleshooting Kubernetes deployments