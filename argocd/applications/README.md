# Argo CD applications

This folder is scanned by Argo CD and has auto-sync enabled.
As such, it can be used to create and deploy other applications by simply adding an application manifest.

## Example

```yml
project: default
source:
  repoURL: https://github.com/secondhomelab/k8s.git
  path: nextcloud
  targetRevision: HEAD
destination:
  server: https://kubernetes.default.svc
  namespace: nextcloud
syncPolicy:
  automated:
    prune: false
    selfHeal: false
    enabled: true
  syncOptions:
    - CreateNamespace=true
```
