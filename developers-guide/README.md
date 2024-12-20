# Development Guide for Devtron
This document provides instructions for setting up a development environment to help you get started with contributing to Devtron. Make sure to review the contributing.md file for more details on contributing.This document will help guide you through understanding this build process. Note, below is the setup recommended for goland environment.


# Architecture of Devtron
![image](https://github.com/user-attachments/assets/1c639cf1-6540-4f8a-8563-3e2323915b9f)

## Requirements
- Go: The language Devtron is developed with (version 1.18 or higher) 
- Go land installed
- Docker installed
- A kubernetes cluster 
- Helm

# Set up Guide


## 1. Prepare Your Local Workspace

Navigate to the `github.com` directory on your local machine:

```bash
cd src/github.com
```

### Clone the Devtron Repository

```bash
git clone <repository-url>
```

### Open the Repository in Your IDE

Open the cloned repository in GoLand (or your preferred IDE) for development.

---

## 2. Configure Environment Variables

Set the following environment variables required for development:

```bash
export PG_PASSWORD=
export PG_PORT=5432
export PG_USER=postgres
export PLUGIN_IDENTIFIER_LIST_FOR_DIGEST_PULL=improved-image-scan,vulnerability-scanning
export RUNTIME_CONFIG_LOCAL_DEV=true
export TEST_PG_PASSWORD=
export USE_ARTIFACT_LISTING_API_V2=true
```

Use this command to extract the passoword 

```
kubectl exec -it -n devtroncd sts/postgresql-postgresql -c postgresql-postgresql -- bash -c 'export PGPASSWORD=$POSTGRES_PASSWORD && psql -U postgres -d orchestrator'
```

You can either export these variables in your terminal or configure them in your development environment settings.

---

## 3. Access the Devtron Dashboard

### Forward the Port to Access the Dashboard

```bash
kubectl port-forward svc/devtron-service-name <local-port>:<remote-port> -n <namespace>
```

### Retrieve the Password for the Dashboard

```bash
kubectl get secret <secret-name> -o jsonpath="{.data.password}" | base64 --decode
```

---

## 4. PostgreSQL Configuration

### Forward the Port to Access PostgreSQL

```bash
kubectl port-forward pod/<postgres-pod-name> 5432:5432 -n <namespace>
```

### Retrieve the PostgreSQL Password

Extract the password from the pod’s environment variables:

```bash
kubectl exec -it <postgres-pod-name> -- env | grep -i pass
```

---

## 6. Run the Application

Ensure all environment variables are correctly configured as mentioned above.

### Start Devtron

Run the necessary Go build and execution commands to start the application.

