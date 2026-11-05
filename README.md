# Kubernetes NodePort Service – Hands-on Lab
## Project Overview
This project demonstrates how to expose an NGINX application running inside a Kubernetes cluster using a NodePort Service.
The application is deployed using Kubernetes Deployment and exposed externally using NodePort.
## Technologies Used
- Docker Desktop Kubernetes
- Kubernetes
- NGINX
- YAML
- Git and GitHub
- Git Bash

## Architecture

- Namespace: nodeport-lab
- Deployment: nginx-deployment
- Replicas: 3
- Application: NGINX
- Container Port: 80
- Service Type: NodePort
- Service Port: 80
- NodePort: 30080

## Repository Structure

- namespace/namespace.yaml
- deployment/nginx-deployment.yaml
- service/nginx-nodeport.yaml

## Deployment Instructions

1. Create Kubernetes namespace.
2. Deploy NGINX using Deployment YAML.
3. Expose the application using NodePort Service.
4. Verify Pods and Service.
5. Access the application using NodePort.

## Deployment Commands

```bash
kubectl apply -f namespace/namespace.yaml
kubectl apply -f deployment/nginx-deployment.yaml
kubectl apply -f service/nginx-nodeport.yaml
```

## Verification

```bash
kubectl get pods -n nodeport-lab
kubectl get deployments -n nodeport-lab
kubectl get svc -n nodeport-lab
kubectl describe svc nginx-nodeport-service -n nodeport-lab
```

kubectl port-forward -n nodeport-lab svc/nginx-nodeport-service 30080:80
minikube service nginx-nodeport-service -n nodeport-lab --url

## Application Access

http://localhost:30080

Note: Direct localhost access depends on Docker Desktop networking configuration.

## Practical Exercises

- Deploy NGINX using Kubernetes Deployment.
- Expose NGINX using NodePort.
- Verify Service endpoints.
- Scale Pods from 3 to 5.
- Troubleshoot selector and targetPort issues.
- Test application connectivity.

## Learning Outcomes

Understanding Kubernetes Services, NodePort networking, Service selectors, Pod endpoints, traffic distribution and troubleshooting.
