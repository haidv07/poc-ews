# Kubernetes Manifests Repository

This repository contains Kubernetes manifests for deploying applications using ArgoCD.

## Structure

- `apps/` - Application manifests organized by application name
  - `sm-flexews/` - Microservices application
    - `base/` - Common manifests
    - `overlays/` - Environment-specific configurations (dc1, dc2, dr)
- `infrastructure/` - Infrastructure components (ingress, secrets, storage)
- `.argocd/` - ArgoCD application and project definitions

## Applications

### sm-flexews
A microservices application consisting of:
- user-service
- product-service
- order-service
- redis

## Usage

Configure ArgoCD to point to this repository and sync automatically.
