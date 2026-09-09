# nagomi-observability

Observability stack for nagomi. For now just collects and visualises logs from most services.

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
| nagomi-core | `nagomi-core/nagomi-core.log` |
| nagomi-email-parser | `nagomi-email-parser/nagomi-email-parser.log` |
| nagomi-receipts | `nagomi-receipts/nagomi-receipts.log` |
| nagomi-gateway | `nagomi-gateway/nagomi-gateway.log` |
