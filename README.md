# Kubernetes AI Landing Zone

This repository provides a template for setting up a secure, GPU‑enabled
Kubernetes cluster to host AI workloads.  It includes sample manifests,
Helm values, and scripts to configure GPU node pools, RBAC policies,
ingress controllers, and monitoring.

## Components

- **GPU node pool:** Example node selector and taints to schedule
  GPU‑intensive pods on dedicated nodes.
- **Ingress controller:** A basic NGINX ingress deployment with TLS and
  RBAC rules.
- **Namespace and RBAC:** Isolation for AI workloads via namespaces,
  roles, and service accounts.
- **Monitoring:** Prometheus and Grafana manifests for cluster and
  application metrics.

## Usage

Apply the provided manifests in the `manifests/` directory to your
cluster.  If you use Helm, the `charts/` directory contains a
parameterized chart you can customize via values files.

```bash
kubectl apply -f manifests/namespace.yaml
kubectl apply -f manifests/gpu-node-selector.yaml
kubectl apply -f manifests/ingress-controller.yaml
kubectl apply -f manifests/monitoring.yaml
```

## Extending

You can integrate this landing zone with your CI/CD pipeline by adding
GitHub Actions or ArgoCD workflows.  Additional components such as
Secrets management (e.g., HashiCorp Vault), logging stacks, and
service meshes can be layered on top as needed.