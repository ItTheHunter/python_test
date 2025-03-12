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

```
limits: The maximum CPU and memory available to the container.  
Example: cpu: 1000m = 1 CPU core  
Example: memory: 3000Mi = 3 GB  
requests: The minimum guaranteed CPU and memory reserved for the container.  

Example: Increase CPU/Memory  
to increase to 2 CPUs and 4 GB of memory.

```yaml
resources:
  limits:
    cpu: 2000m
    memory: 4000Mi
  requests:
    cpu: 2000m
    memory: 4000Mi
