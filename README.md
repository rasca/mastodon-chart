# Mastodon chart

A Helm chart for [Mastodon](https://github.com/tootsuite/mastodon).
Mastodon is a free, open-source social network server.

This Helm chart is designed/tested with:

| Package | Version |
| ------- | ------- |
| Mastodon | `v3.5.1` (glitch-soc) |
| Kubernetes | v1.23 |

## How to Install?
Copy and edit `secrets.yaml.sample` and `values.yaml.sample` to provide your
own `secrets.yaml` and `values.yaml` files, and then deploy the Helm chart
with: 

```
helm upgrade --install -f secrets.yaml mastodon .
```

### Maintainer & License
Based on modifications by Tim Walls - https://github.com/timwalls/mastodon-chart, which were based on the original chart developed by Ladicle - https://github.com/Ladicle/mastodon-chart.
