# Cloudflare tunnel

Configured in the Cloudflare dashboard to point to Envoy Gateway

## Secret

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: tunnel-token
  namespace: cloudflare
stringData:
  token: XXX
```

## References

- https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/deployment-guides/kubernetes/
