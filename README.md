# Kubernetes MongoDB and Mongo Express Demo

This project demonstrates a basic Kubernetes setup using Minikube, deploying MongoDB and Mongo Express. It serves as an introduction to Kubernetes YAML configurations and shows how various Kubernetes components interact.

## Components

1. MongoDB Deployment and Service
2. Mongo Express Deployment and LoadBalancer Service
3. ConfigMap for database URL
4. Secret for MongoDB credentials

## Files

- `mongo.yaml`: MongoDB Deployment and ClusterIP Service
- `mongo-express.yaml`: Mongo Express Deployment and LoadBalancer Service
- `mongo-configmap.yaml`: ConfigMap for database URL
- `mongo-secret.yaml`: Secret for MongoDB root username and password

## Prerequisites

- Minikube
- kubectl

## Setup

1. Start Minikube:

   ```bash
   minikube start
   ```

2. Apply the Secret:

   ```bash
   kubectl apply -f mongo-secret.yaml
   ```

3. Apply the ConfigMap:

   ```bash
   kubectl apply -f mongo-configmap.yaml
   ```

4. Deploy MongoDB:

   ```bash
   kubectl apply -f mongo.yaml
   ```

5. Deploy Mongo Express:

   ```bash
   kubectl apply -f mongo-express.yaml
   ```

## Accessing the Application

To access Mongo Express:

1. Get the URL:

   ```bash
   minikube service mongo-express-service
   ```

2. Open the URL in a web browser

## Cleanup

To delete all resources:

```bash
kubectl delete -f mongo-express.yaml
kubectl delete -f mongo.yaml
kubectl delete -f mongo-configmap.yaml
kubectl delete -f mongo-secret.yaml
```

## Note

This is a demo project for learning purposes. In a production environment, you would need to consider security, persistence, and scaling aspects more thoroughly.

This README provides an overview of your project, lists the components and files, outlines the setup process, explains how to access the application, and includes cleanup instructions. It also adds a note about the project's purpose.
