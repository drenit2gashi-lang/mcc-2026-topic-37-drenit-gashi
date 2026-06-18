# Kubernetes Mini Lab for a Web API

## Project Description

This project is a small Web API created for the topic **Kubernetes Mini Lab for a Web API**.

The goal is to demonstrate how a simple API can be containerized with Docker and deployed using Kubernetes manifests.

The project includes:

- A Node.js/Express Web API
- Dockerfile for containerization
- Kubernetes Deployment
- Kubernetes Service
- Kubernetes ConfigMap
- Kubernetes Secret
- Horizontal Pod Autoscaler
- Health check endpoint

## Chosen Stack

Docker/Kubernetes service

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Returns basic API information |
| GET | `/health` | Health check endpoint |
| GET | `/config` | Shows configuration status |
| GET | `/tasks` | Returns all tasks |
| POST | `/tasks` | Creates a new task |
| PUT | `/tasks/:id` | Updates a task |
| DELETE | `/tasks/:id` | Deletes a task |

## Run Locally

```bash
npm install
npm start


```bash
docker build -t mini-api:1.0 .
```

## Run Docker Container

```bash
docker run -p 3000:3000 mini-api:1.0
```

Open:




## Deploy to Kubernetes

Apply the Kubernetes manifests:

```bash
kubectl apply -f k8s/configmap.yaml
kubectl apply -f k8s/secret.yaml
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl apply -f k8s/hpa.yaml
```

## Check Kubernetes Resources

```bash
kubectl get pods
kubectl get deployments
kubectl get services
kubectl get hpa
```

## Access the API in Kubernetes




kubectl port-forward service/mini-api-service 30080:80
```

Then open:

```text
http://localhost:30080
```

## Kubernetes Components

### Deployment


### Service

The Service exposes the API using NodePort. It maps external port `30080` to container port `3000`.

### ConfigMap


### Secret


### Horizontal Pod Autoscaler


## Project Structure

```text
kubernetes-mini-lab-api/
├── src/
│   └── server.js
├── k8s/
│   ├── configmap.yaml
│   ├── secret.yaml
│   ├── deployment.yaml
│   ├── service.yaml
│   └── hpa.yaml
├── package.json
├── Dockerfile
├── .dockerignore
├── .gitignore
├── README.md
└── AI-log.txt
```

## Author

Drenit Gashi  
drenit2.gashi@universitetiaab.com
