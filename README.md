🚀 MERN GitOps Platform
A MERN Stack Todo application deployed on Kubernetes using modern DevOps practices including Docker, Helm, Argo CD, Persistent Volumes, Ingress, and GitOps workflows.
-----------------------------------------------------------------
📌 Project Overview
This project started as a traditional MERN Stack Todo application and was transformed into a complete Kubernetes-based deployment platform.

The goal was not only to run the application but also to implement real-world DevOps concepts such as:

Docker containerization
Kubernetes deployments
Persistent storage
Ingress routing
Helm packaging
GitOps with Argo CD
--------------------------------------------------------------------
🏗 Architecture
GitHub
   │
   ▼
 Argo CD
   │
   ▼
 Helm Chart
   │
   ▼
 Kubernetes
   │
   ├── Frontend (React)
   ├── Backend (Node.js / Express)
   └── MongoDB
------------------------------------------------------------------
🛠 Technologies Used
Application Layer
React.js
Node.js
Express.js
MongoDB
Mongoose
DevOps Layer
Docker
Kubernetes (Kind)
NGINX Ingress Controller
Helm
Argo CD
GitHub
---------------------------------------------------------
🐳 Docker
The application was containerized by creating separate Docker images for:

Frontend
mern-frontend
Backend
mern-backend
Images are pushed to Docker Hub and used by Kubernetes Deployments.
-------------------------------------------------------
☸️ Kubernetes
The application is deployed using Kubernetes resources:

Deployments
frontend-deployment
backend-deployment
mongo-deployment
Services
frontend-svc
backend-svc
mongo-svc
Ingress
NGINX Ingress routes requests:

/
 └── frontend

/api
 └── backend
Persistent Storage
MongoDB uses a PersistentVolumeClaim:

mongodb-pvc
This allows database persistence beyond Pod restarts.
------------------------------------------------------
📦 Helm
The Kubernetes manifests were converted into a reusable Helm Chart.

Structure:

mern-chart/
│
├── Chart.yaml
├── values.yaml
└── templates/
The following values are configurable through:

values.yaml
Docker Images
Replica Counts
Service Ports
PVC Size
Ingress Configuration
Example:

backend:
  replicaCount: 1
  image: tameem325/mern-backend
-------------------------------------------------------
🔄 GitOps with Argo CD
The entire deployment is managed through Argo CD.

Workflow:

Git Push
   │
   ▼
 GitHub Repository
   │
   ▼
 Argo CD detects changes
   │
   ▼
 Sync Application
   │
   ▼
 Kubernetes updated automatically
Implemented features:

✅ Automated Sync

✅ Self Heal

✅ Prune Resources

✅ Helm Chart Deployment
-----------------------------------------
🌐 Access Flow
Browser
   │
   ▼
NGINX Ingress
   │
   ├── /
   │     └── Frontend
   │
   └── /api
         └── Backend
                   │
                   ▼
                MongoDB
📂 Helm Chart Structure
mern-chart/
│
├── Chart.yaml
├── values.yaml
│
└── templates/
    ├── frontend-deploy.yaml
    ├── frontend-svc.yaml
    ├── backend-deploy.yaml
    ├── backend-svc.yaml
    ├── mongo-deploy.yaml
    ├── mongo-svc.yaml
    ├── mongo-pvc.yaml
    └── ingress.yaml
---------------------------------------------------------------
🎯 DevOps Concepts Demonstrated
Docker Image Creation
Docker Hub Registry
Kubernetes Deployments
Kubernetes Services
Persistent Storage
NGINX Ingress
Helm Charts
Argo CD
-----------------------------------------------------------------
🙏 Credits
Original MERN Todo application:

https://github.com/chetannada/MERN-Todo

The infrastructure, containerization, Kubernetes deployment, Helm packaging and GitOps workflow were implemented as part of this DevOps project.