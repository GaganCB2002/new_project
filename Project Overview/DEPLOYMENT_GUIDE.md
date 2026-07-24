# Deployment Guide

## Prerequisites
- Kubernetes Cluster (EKS/GKE).
- Managed PostgreSQL (RDS/Cloud SQL).
- Managed Redis.

## CI/CD Pipeline
GitHub Actions automatically builds Docker images on push to `main` and pushes them to AWS ECR.

## Kubernetes Deployment
Apply the manifests in the `kubernetes/` directory:
```bash
kubectl apply -f k8s/namespace.yaml
kubectl apply -f k8s/postgres-deployment.yaml
kubectl apply -f k8s/backend-deployment.yaml
kubectl apply -f k8s/frontend-deployment.yaml
kubectl apply -f k8s/ingress.yaml
```

## Environment Variables
Ensure Kubernetes Secrets are populated with:
- `DATABASE_URL`
- `JWT_SECRET`
- `KAFKA_BROKERS`
