# MongoDB and Mongo Express Deployment on Kubernetes

This project demonstrates deploying **MongoDB** and **Mongo Express** on Kubernetes using a single manifest file.  
The deployment follows core DevOps and Kubernetes best practices including **Services**, **Secrets**, and **ConfigMaps** to ensure secure and organized configuration management.

---

## Project Overview

The project deploys:
- MongoDB as a backend database
- Mongo Express as a web-based UI for MongoDB
- Secure credentials using Kubernetes Secrets
- Application configuration using ConfigMaps
- Internal and external access using Kubernetes Services

All resources are defined and applied using Kubernetes YAML manifests.

---

## Architecture Summary

- MongoDB runs inside a Kubernetes Deployment
- MongoDB is exposed internally using a ClusterIP Service
- Mongo Express runs in a separate Deployment
- Mongo Express connects to MongoDB using Kubernetes DNS
- Mongo Express is exposed externally using a NodePort Service
- Database credentials are stored in Secrets
- Non-sensitive configuration is stored in ConfigMaps

---

## Kubernetes Resources Used

- Deployments
  - MongoDB
  - Mongo Express
- Services
  - MongoDB ClusterIP Service
  - Mongo Express NodePort Service
- Secrets
  - MongoDB root username
  - MongoDB root password
- ConfigMaps
  - Mongo Express configuration variables

---

## Prerequisites

- Kubernetes cluster (Minikube, Kind, or Cloud Kubernetes)
- kubectl installed and configured
- Internet access to pull container images

---

## Deployment Steps

Apply all Kubernetes resources using a single command:

```bash
kubectl apply -f deployment.yaml
