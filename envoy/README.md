# Envoy Gateway

Installation with Helm

```bash
helm upgrade \
  --install \
  -n envoy-gateway-system \
  --create-namespace \
  --version v1.8.0 \
  eg oci://docker.io/envoyproxy/gateway-helm
```

## TODO

- [ ] Figure out if the gateway, gatewayProxy and gatewayClass shouldn't better be in a separate namespace
