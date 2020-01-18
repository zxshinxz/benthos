---
title: prometheus
type: metrics
---

```yaml
prometheus:
  prefix: benthos
  push_interval: ""
  push_job_name: benthos_push
  push_url: ""
```

Host endpoints (`/metrics` and `/stats`) for Prometheus scraping.
Metrics paths will differ from [the list](about#paths) in that dot separators will
instead be underscores.

### Push Gateway

The field `push_url` is optional and when set will trigger a push of
metrics to a [Prometheus Push Gateway](https://prometheus.io/docs/instrumenting/pushing/)
once Benthos shuts down. It is also possible to specify a
`push_interval` which results in periodic pushes.

The Push Gateway is useful for when Benthos instances are short lived. Do not
include the "/metrics/jobs/..." path in the push URL.

