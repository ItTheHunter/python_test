This repository sets up services in a Kubernetes cluster via helm.

Services are deployed by automated pipelines.

Systems services charts: argocd, cert manager, ingress-nginx.

Projects applications charts: argoapps.

Pipelines are separated by branches:
- test-env - deploys to test-environment in AWS cluster using a test domain
- preprod - deploys to prod AWS cluster using a temporary domain
- prod - deploys to prod AWS cluster with a production domain

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
