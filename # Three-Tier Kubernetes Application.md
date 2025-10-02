# Three-Tier Kubernetes Application

This project demonstrates a three-tier web application architecture using Kubernetes. The application is a **ToDo application** that allows users to create, view, and manage tasks.

The stack consists of:

- **Frontend:** React.js (containerized, custom image)
- **Backend:** Node.js (Express, containerized, custom image)
- **Database:** MongoDB (official Docker image)

All custom components are containerized and images are pushed to Docker Hub. MongoDB uses the official image from Docker Hub.

---

## Architecture Overview

### Frontend (React.js)
- Deployed using a Kubernetes Deployment for managing replicas.
- Exposed externally with a LoadBalancer Service.
- Horizontal Pod Autoscaler is configured to scale pods automatically when CPU usage exceeds 50%.
- Provides a user interface for interacting with the ToDo application.

### Backend (Node.js)
- Deployed using a Kubernetes Deployment for managing replicas.
- Exposed externally with a LoadBalancer Service.
- Uses Kubernetes Secrets to securely access MongoDB credentials.
- Handles API requests from the frontend and communicates with the database.

### Database (MongoDB)
- Deployed using a Kubernetes Deployment with the official MongoDB image.
- Uses a Persistent Volume and Persistent Volume Claim for data persistence.
- Credentials are managed with Kubernetes Secrets.
- Exposed internally using a ClusterIP Service.
- Stores all ToDo tasks and related data.

---

## Key Features

- Clear separation of frontend, backend, and database tiers.
- Scalability through Kubernetes Deployments and Horizontal Pod Autoscaler.
- Secure management of sensitive data using Kubernetes Secrets.
- Persistent storage for database data.
- Application images for frontend and backend are stored on Docker Hub for portability.

---

## Project Context

This project was developed as part of my master's studies to showcase my skills in designing, containerizing, and orchestrating a scalable, secure, and persistent three-tier web application using Kubernetes and Docker.