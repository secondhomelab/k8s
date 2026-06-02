# Local Path provisioner

## Install using Helm

```bash
helm upgrade \
  --install \
  --namespace local-path-provisioner \
  --create-namespace \
  --values values.yml \
  --version 0.0.36 \
  local-path-provisioner oci://ghcr.io/rancher/local-path-provisioner/charts/local-path-provisioner
```

[Reference for values](https://github.com/rancher/local-path-provisioner/blob/master/deploy/chart/local-path-provisioner/values.yaml)

## References

- [Talos documentation](https://docs.siderolabs.com/kubernetes-guides/csi/local-storage#local-path-provisioner)
- [Local Path Provisioner GitHub](https://github.com/rancher/local-path-provisioner)
