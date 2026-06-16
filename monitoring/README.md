# Monitoring

```mermaid
flowchart LR


p[Prometheus]
g[Grafana]
ups[UPS]
wifi[Wi-Fi AP]
t[Talos VM]
ne[node-exporter]
snmpe[snmp-exporter]
apcupsde[apcupsd-exporter]


t --> ne
wifi --> snmpe
ups --> apcupsde

snmpe --> p
apcupsde --> p
ne --> p

p --> g
```
