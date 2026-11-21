# Kubernetes Multi-Environment GitOps Platform — Work in Progress

> **Status: Initial concept / repository scaffold.** The repository currently contains a short project description and an overview image. Environment overlays, Argo CD applications, Helm/Kustomize configuration and deployment evidence still need to be committed before this can be considered a working platform.

## Project objective

Create a GitOps-oriented Kubernetes platform that separates application configuration by environment and makes Git the auditable source of desired state.

The planned platform should make it possible to promote a change through development, staging and production while keeping environment-specific configuration controlled and reviewable.

## Proposed design

The following is the intended learning scope, not a description of resources already running:

- A reusable Kubernetes base for shared application resources.
- Separate overlays or Helm values for development, staging and production.
- Argo CD Applications to reconcile each environment from Git.
- Environment-specific replica counts, ingress settings and resource requests/limits.
- A documented promotion process using pull requests.
- Health checks and a clear rollback procedure.

## Planned technology stack

| Area | Candidate technology |
|---|---|
| Container orchestration | Kubernetes |
| GitOps controller | Argo CD |
| Packaging/configuration | Helm and Kustomize |
| Source control | Git and GitHub |
| Local validation | Minikube or kind |
| Infrastructure provisioning | Terraform (future extension) |

Only list a tool as implemented after the corresponding configuration is added and tested.

## Intended repository structure

The following is a proposed structure to build toward:

```text
.
├── apps/
│   └── sample-app/
├── environments/
│   ├── dev/
│   ├── staging/
│   └── production/
├── argocd/
│   ├── projects/
│   └── applications/
├── charts/
├── docs/
└── README.md
```

## Implementation checklist

- [ ] Add a minimal sample application and container image.
- [ ] Add Kubernetes base manifests or a Helm chart.
- [ ] Add a working development environment configuration.
- [ ] Add Argo CD Application configuration and verify sync.
- [ ] Add staging and production overlays with deliberate differences.
- [ ] Demonstrate promotion through a pull request.
- [ ] Demonstrate drift correction or rollback.
- [ ] Add architecture and deployment screenshots from a real test cluster.
- [ ] Document resource cleanup and local setup.

## Current visual

The image below is an overview visual only; it does not establish that the described environments or controllers are deployed.

<img width="1920" alt="GitOps platform overview" src="https://github.com/user-attachments/assets/438f073c-8413-4eab-bd25-d2b438571375" />

## Completion criteria

The project is ready to be presented as implemented when a reviewer can follow the setup guide, inspect the committed environment configuration, see Argo CD reconcile the application, and reproduce an environment-specific change.

## Author

[JOSH801251](https://github.com/JOSH801251)
