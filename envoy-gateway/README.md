# Envoy Gateway

```mermaid
flowchart LR
u1[User]
u2[User]
c[Cloudflare]
g[Envoy gateway]
a[App A]
b[App B]

u1 -- https://app1.secondhomelab.com --> c
u2 -- https://app2.secondhomelab.com --> c

c-- tunnel --> g
g -- HTTP --> a
g -- HTTP --> b
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
