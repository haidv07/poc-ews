# sm-flexews Application

Microservices application for flexible enterprise web services.

## Components

- **user-service**: User management and authentication
- **product-service**: Product catalog management
- **order-service**: Order processing and management
- **redis**: In-memory cache for session storage

## Deployment

### Using Kustomize directly
```bash
# Deploy to DC1
kubectl apply -k overlays/dc1

# Deploy to DC2
kubectl apply -k overlays/dc2

# Deploy to DR
kubectl apply -k overlays/dr
```

### Using ArgoCD
ArgoCD will automatically sync from the configured Git repository.

## Configuration

Replica counts per environment:
- **DC1**: 2 replicas per service
- **DC2**: 3 replicas per service (higher capacity)
- **DR**: 1 replica per service (minimal footprint)

## Network Policies

The application uses NetworkPolicies for security:
- Default deny all traffic
- Allow traffic within same namespace
- Allow DNS egress
- Allow external egress for order-service only
