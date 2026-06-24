# ArgoCD

```bash
helm upgrade \
  --install \
  --namespace argocd \
  --create-namespace \
   --version 9.5.21 \
   --values values.yml \
  argocd argo/argo-cd
```
