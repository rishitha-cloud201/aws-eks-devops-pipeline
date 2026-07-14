## Helm Deployment Support

This project includes a Helm chart for packaging and deploying the demo application to Kubernetes.

### Helm Chart Structure

```text
helm/demo-app/
├── Chart.yaml
├── values.yaml
└── templates/
    ├── deployment.yaml
    └── service.yaml
```

## Kubernetes Production Configuration

The project includes production-style Kubernetes manifests for:

- ConfigMap-based application configuration
- Kubernetes Secret examples for sensitive values
- NGINX Ingress routing
- Horizontal Pod Autoscaling based on CPU utilization

These manifests demonstrate externalized configuration, secure credential handling patterns, application routing, and workload scaling.

## GitOps Deployment with Argo CD

The repository includes Argo CD manifests for declarative Kubernetes application delivery.

The Argo CD `Application` watches the Helm chart stored in this repository and automatically synchronizes changes to the target Kubernetes namespace.

### GitOps Workflow

```text
Developer Commit
       |
       v
GitHub Repository
       |
       v
Argo CD Detects Change
       |
       v
Helm Chart Rendered
       |
       v
AWS EKS Deployment
```
