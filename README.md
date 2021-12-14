
grok_exporter config & pattern

```
https://github.com/fstab/grok_exporter/
```

## Grafana panel
```
rate(orchestrator_relayer_error_count{job="grok"}[1h])
```

## Grafana alert

```
rate(orchestrator_relayer_error_count[1h])*1000
```

```
last() > 1
```
