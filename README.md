
## grok_exporter config & pattern

install grok_exporter:

```
https://github.com/fstab/grok_exporter/
```

add config & extra patterns from this repo. Start exporter

```
./grok_exporter -config config.yml
```

add job into prometheus.yml  under `scrape_configs:`
```
  - job_name: 'grok'
    static_configs:
    - targets: ['localhost:9144']
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
