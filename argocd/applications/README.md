# Argo CD applications

This folder is scanned by Argo CD and has auto-sync enabled.
As such, it can be used to create and deploy applications by simply adding an application manifest.

## Example

```diff
  ./
  ├── argocd/
  │   └── applications/
  │       ├── app1.yml
  │       ├── app2.yml
+ │       └── my-app.yml
  ├── app1
  ├── app2
+ └── my-app/
+     └── index.html
```

```yml
# argocd/applications/my-application.yml
project: default
source:
  repoURL: https://github.com/secondhomelab/k8s.git
  path: my-app # Configure this
  targetRevision: HEAD
destination:
  server: https://kubernetes.default.svc
  namespace: my-namespace # Configure this
syncPolicy:
  automated:
    prune: false
    selfHeal: false
    enabled: true
  syncOptions:
    - CreateNamespace=true
```

```yml
# my-app/deployment.yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 1
  selector:
    matchLabels:
      app.kubernetes.io/name: my-app
  template:
    metadata:
      labels:
        app.kubernetes.io/name: my-app
    spec:
      containers:
        - name: my-app
          image: nginx
```
