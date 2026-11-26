# DevOps Practical 5: CI/CD Pipeline & Kubernetes Deployment

A containerized Node.js web application automated with Jenkins, Docker Hub, and Kubernetes (Minikube).

## Tech Stack
- **Application:** Node.js (`app.js`, `package.json`)
- **Containerization:** Docker (`Dockerfile`)
- **CI/CD:** Jenkins Pipeline (`Jenkinsfile`) building and pushing `nyirarukundo/my-web-app:latest` to Docker Hub
- **Orchestration:** Kubernetes (`k8s/deployment.yaml`, `k8s/service.yaml`) running 2 replicas exposed via NodePort on Minikube

## Run Locally on Kubernetes
```bash
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
minikube service my-web-app-service --url
