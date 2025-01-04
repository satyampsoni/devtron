# Development Guide for Devtron

This document provides instructions for setting up a development environment to help you get started with contributing to Devtron. Make sure to review the [contributing.md](https://github.com/devtron-labs/devtron/blob/main/CONTRIBUTING.md) file for more details on contributing. This document will help guide you through understanding the build process.

## Requirements
- Programming Language: Go
- Docker should be installed
- Any Kubernetes Cluster (Devtron is K8s Cluster & Cloud Agnostic)
- Helm v3

## Setup Guide

### Install Devtron in a Kubernetes cluster

1. [Create a Kubernetes Cluster](https://docs.devtron.ai/getting-started#create-a-kubernetes-cluster)
   - 2 vCPUs
   - 4GB+ of free memory
   - 20GB+ free disk space

2. [Install Devtron with CI/CD along with GitOps (Argo CD) - Full mode](https://docs.devtron.ai/install/install-devtron-with-cicd-with-gitops)

    ```bash
    helm repo add devtron https://helm.devtron.ai
    helm repo update devtron
    helm install devtron devtron/devtron-operator \
      --create-namespace --namespace devtroncd \
      --set installer.modules={cicd} \
      --set argo-cd.enabled=true
    ```

    Note: If you want to install Devtron on a Managed Kubernetes cluster, please [refer to the guide](https://docs.devtron.ai/install/demo-tutorials).

3. Set the kubeconfig file to access the cluster. It is recommended to set up the kubeconfig locally and set-context to the particular cluster.

4. Forward the port of PostgreSQL service and Devtron NATS service:

    ```bash
    kubectl -n devtroncd port-forward svc/devtron-nats 4222:4222 
    kubectl -n devtroncd port-forward svc/postgresql-postgresql 5432:5432
    # Optional
    kubectl -n devtroncd port-forward svc/argocd-dex-server-ent-5 5556:5556
    ```

5. Use this command to extract the password of PostgreSQL (Required to put in ENV):

    ```bash
    kubectl exec -it -n devtroncd postgresql-postgresql-0 -- printenv | grep POSTGRES_PASSWORD
    ```

### 1. Prepare Your Local Workspace

Navigate to the `github.com` directory on your local machine:

- `cd go/src/github.com`
- `git clone http://github.com/devtron-labs/devtron`
- Configure [Environment Variables](https://github.com/devtron-labs/devtron/blob/main/scripts/dev-conf/envfile.env)
- Run the server:

    ```bash
    make run
    ```

This will start your server on `localhost:8080`.

