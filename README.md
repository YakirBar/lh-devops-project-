# 🚀 Final Project – Kubernetes + GitHub Actions + ArgoCD + Grafana Stack

## 🎯 Project Overview

In this project you will build a complete cloud-native platform that includes:

* 🌐 Frontend Application
* ⚙️ Backend API
* 🗄 Database
* 🐳 Docker
* ☸️ Kubernetes
* 📦 Nexus Repository
* 🧪 GitHub Actions
* 🚀 ArgoCD
* 📊 Grafana Stack
* 🗂 Git Workflow

The project is divided into **4 main parts**.

---

# 📦 Part 1 – Three-Tier Application (25 Points)

## 🎯 Objective

Build a complete hotel reservation system using a three-tier architecture.

---

## 🌐 Layer 1 – Frontend Application

### Requirements

Develop a frontend application using:

* JavaScript
* OR TypeScript

The application must contain multiple screens.

---

### Screen 1 – New Reservation

The user must:

* Select a hotel from the available list
* Enter:

  * Full Name
  * Email Address
  * Check-In Date
  * Check-Out Date

If the selected dates are available, the user should receive a confirmation message indicating that the reservation was successfully completed.

---

### Screen 2 – Reservation Lookup

The user must:

* Enter Full Name or Email Address

The application should:

* Retrieve reservation details from the database
* Display reservation information if found
* Allow the user to cancel the reservation

---

## ⚙️ Layer 2 – Backend Application

### Requirements

Develop a backend application using:

* JavaScript
* OR Python

---

### Function 1 – Create Reservation

The backend must:

* Validate reservation details
* Verify business rules
* Store reservation data in the database
* Return a success message

---

### Function 2 – Reservation Lookup

The backend must:

* Receive a Reservation ID
* Verify the reservation exists
* Return reservation details

---

### Function 3 – Cancel Reservation

The backend must:

* Receive a Reservation ID
* Verify the reservation exists
* Remove the reservation from the database
* Return a cancellation confirmation

---

## 🗄 Layer 3 – Database

You may choose:

* MySQL
* OR MongoDB

---

### Table / Collection 1 – Hotels

Each hotel must contain:

```text
Hotel ID
Hotel Name
Description
Location
Price Per Night
```

---

### Table / Collection 2 – Reservations

Each reservation must contain:

```text
Reservation ID
Full Name
Email Address
Check-In Date
Check-Out Date
Hotel ID
```

---

### Database Client UI

You must deploy a database client UI based on your selected database.

Examples:

* Mongo Express
* phpMyAdmin
* Adminer

---

# ☸️ Part 2 – Deployment & Artifact Registry (25 Points)

## 🎯 Objective

Deploy the entire platform into a local Kubernetes cluster and implement artifact registry.

---

## 🚀 Deployment Requirements

Supported platforms:

* Minikube
* Kind
* Docker Desktop Kubernetes

---

### Kubernetes Requirements

Deploy all components from Part 1.

Use:

* Dedicated Namespaces
* Persistent Volumes
* ConfigMaps
* Secrets

---

### Replica Requirements

#### Frontend

```text
5 Replicas
```

#### Backend

```text
5 Replicas
```

#### Database

```text
3 Replicas
```

---

## 📦 Artifact Registry Requirements

Deploy a local Nexus Repository inside Kubernetes.

---

### Nexus Requirements

Use:

* Dedicated Namespace
* Persistent Volumes
* ConfigMaps
* Secrets

Nexus will serve as the private container registry for the project.

---

# 🧪 Part 3 – Build Process (25 Points)

## 🎯 Objective

Use GitHub Actions and automate the build process.

---

## ⚙️ Pipeline 1 – Build Pipeline

### Trigger

```text
PUSH → DEV Branch
```

### Responsibilities

1. Build application artifacts
2. Build Docker images
3. Push images to NexusHub Repository

---

## ⚙️ Pipeline 2 – Deployment Preparation Pipeline

### Trigger

```text
After Build Pipeline Completes
```

### Responsibilities

1. Update image tag references
2. Replace old image version with new version
3. Open Pull Request to MAIN
4. Approve Pull Request
5. Merge Pull Request

---

# 🚀 Part 4 – Deployment Process (25 Points)

## 🎯 Objective

Deploy applications automatically using ArgoCD.

---

## 📌 Requirements

Deploy ArgoCD using:

* Dedicated Namespace
* Persistent Volumes
* ConfigMaps
* Secrets

---

## Application 1 – Frontend

### Trigger

```text
Changes in MAIN Branch
```

### Responsibilities

* Detect manifest changes
* Deploy frontend updates automatically

---

## Application 2 – Backend

### Trigger

```text
Changes in MAIN Branch
```

### Responsibilities

* Detect manifest changes
* Deploy backend updates automatically

---

## 🔐 Repository Authentication

Connect GitHub using:

* SSH Keys
* OR Personal Access Token (PAT)

---

# 📊 Bonus: Part 5 – Monitoring Platform (10 Points)

## 🎯 Objective

Deploy a complete monitoring and observability solution.

---

## 📌 Requirements

Deploy Grafana Stack inside Kubernetes.

### Components

* Prometheus
* Loki
* Grafana

---

### Deployment Requirements

Use:

* Dedicated Namespace
* Persistent Volumes
* ConfigMaps
* Secrets

---

## Monitoring Requirements

The platform must collect:

### Logs

Collect logs from:

* Frontend
* Backend
* Database
* ArgoCD
* Nexus

---

## Validation

Demonstrate monitoring in real time.

---

# 🔐 Git Requirements

* Create a 3 Private Repositories

Branch strategy:

```text
MAIN → Production
DEV → Development
```

* Work ONLY on DEV
* Open Pull Requests to MAIN

---

## 👤 Add Collaborator

You must add:

* Email: [yakirbar7820@gmail.com](mailto:yakirbar7820@gmail.com)
* GitHub: [https://github.com/YakirBar](https://github.com/YakirBar)

Only after PR approval will it be merged into MAIN.

---


# 📁 Recommended Folder Structure

```text
frontend-repo/
│
├── .github/workflows
├── src/
├── Dockerfile
└── README.md

backend-repo/
│
├── .github/workflows
├── src/
├── Dockerfile
└── README.md

infra-repo/
│
├── kubernetes/
│   ├── secrets/
│   ├── volumes/
│   ├── services/
│   └── deployments/
│
├── argocd/
│   ├── frontend-app.yaml
│   └── backend-app.yaml
│
└── README.md
```

---

# 📋 Mandatory Files for Submission

* Dockerfile – Frontend
* Dockerfile – Backend
* Kubernetes Manifests
* Nexus Deployment Files
* GitHub Actions Deployment Files
* Build Pipeline
* Deployment Preparation Pipeline
* ArgoCD Frontend Application
* ArgoCD Backend Application
* Grafana Deployment Files
* README.md
* Architecture Diagram

---

# 🧮 Grading Breakdown

| Section                                        | Points |
| ---------------------------------------------- | ------ |
| Part 1 – Three-Tier Application                | 25     |
| Part 2 – Deployment & Artifact Registry        | 25     |
| Part 3 – Build Process                         | 25     |
| Part 4 – Deployment Process                    | 25     |
| Bonus: Part 5 – Monitoring Platform            | 10     |

---

# ⚠️ Important Technical Requirements

## 🔐 Security

* Use Kubernetes Secrets
* Use GitHub Actions Credentials
* No hardcoded credentials
* Use ConfigMaps for non-sensitive configuration

---

## ☸️ Kubernetes

* Use dedicated namespaces
* Use Persistent Volumes
* Use ConfigMaps
* Use Secrets
* Maintain required replica counts

---

## 🔁 Best Practices

* Use meaningful resource names
* Maintain clean folder structure
* Follow GitOps principles
* Separate infrastructure and application resources

---

# 💡 Expected Skills

This project simulates a real-world enterprise DevOps platform including:

* Frontend Development
* Backend Development
* Database Management
* Kubernetes Administration
* CI/CD Automation
* GitOps Workflows
* Artifact Management
* Monitoring & Observability
