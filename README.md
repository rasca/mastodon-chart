<img src="https://img.shields.io/badge/status-early%20alpha-red" alt="early alpha status" />

# Mastodon Chart

A Helm chart for [Mastodon](https://github.com/mastodon/mastodon).
Mastodon is a free, open-source social network server.

This Helm chart is designed/tested with:

| Package | Version |
| ------- | ------- |
| Mastodon | [`v3.5.3`](https://github.com/mastodon/mastodon/releases) (glitch-soc) |
| Kubernetes | v1.24.6+k3s1 ([k3s](https://k3s.io/)) |

## Installing

Copy and edit `secrets.yaml.sample` and `values.yaml.sample` to provide your own `secrets.yaml` and `values.yaml` files, and then deploy the Helm chart with: 

```
helm upgrade --install -f secrets.yaml mastodon .
```

## Configuring

To use external postgresql and redis create a new secret with the postgres
password and the redis connetion url and in your values.yaml set:

```
redis:
  enabled: false
externalRedis:
  existingSecret: mastodon-redis
  existingSecretUrlKey: redis-url

postgres:
  enabled: false
externalPostgresql:
  host: example.com
  port: 5432
  user: mastodon
  database: mastodon
  existingSecret: mastodon-psql
  existingSecretPasswordKey: postgres-password
```

## Maintainer & License

Based on modifications by [Jared Allard](https://github.com/jaredallard/mastodon-chart), which were based on modifications by [Tim Walls](https://github.com/timwalls/mastodon-chart), which in turn were based on the original chart developed by [Ladicle](https://github.com/Ladicle/mastodon-chart).

Standing on the shoulders of giants, indeed.
