# null-observability

Observability stack for null. For now just collects and visualises logs from most services.

## stack

- **Alloy** — tails log files and ships them to Loki
- **Loki** — log storage and query engine
- **Grafana** — dashboards, accessible at `http://localhost:56000` (admin/admin)

## running

```sh
docker compose up -d
```

## adding a service

1. Add a new source + process block in `config.alloy` with the appropriate `app` label
2. Mount the log file in `compose.yml`

The service will appear automatically in the Grafana dashboard dropdown.

## services

| service | log file |
|---|---|
| null-core | `null-core/null-core.log` |
| null-email-parser | `null-email-parser/null-email-parser.log` |
| null-receipts | `null-receipts/null-receipts.log` |
| null-gateway | `null-gateway/null-gateway.log` |
