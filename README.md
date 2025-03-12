# Autopilot Helm Chart

This repository deploys services to a Kubernetes cluster using Helm. Deployments are managed via automated pipelines.

## Where to Change CPU and Memory

In the file [`helm/autopilot/prod-values.yaml`](./helm/autopilot/prod-values.yaml), update the `resources` section:

```yaml
resources:
  limits:
    cpu: 1000m
    memory: 3000Mi
  requests:
    cpu: 1000m
    memory: 3000Mi
