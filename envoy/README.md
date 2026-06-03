# Envoy Gateway

```mermaid
flowchart LR
u[User] -- HTTPS --> c[Cloudflare]
c-- tunnel --> g[Envoy gateway]
g -- HTTP --> a[App A]
g -- HTTP --> b[App B]
```

## Controller installation

With Helm

```bash
helm upgrade \
  --install \
  -n envoy-gateway-system \
  --create-namespace \
  --version v1.8.0 \
  eg oci://docker.io/envoyproxy/gateway-helm
```

## Gateway, EnvoyProxy, GatewayClass

Installed using manifest, same namespace
