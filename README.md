# tailscale-metrics-sidecar

Scrapes the local Tailscale client's Prometheus metrics and forwards them to an upstream OpenTelemetry collector over OTLP.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) with Docker Compose
- [Tailscale](https://tailscale.com/download) installed and running on the host (metrics are scraped from `100.100.100.100/metrics`)

## Running

1. Copy the example environment file and fill in your values:

   ```sh
   cp .env.example .env
   ```

   | Variable             | Description                                  |
   | -------------------- | -------------------------------------------- |
   | `NODE_NAME`          | Name of this Tailscale node                  |
   | `COLLECTOR_ENDPOINT` | Upstream OpenTelemetry collector (host:port) |

2. Start the collector:

   ```sh
   docker compose up -d
   ```

## Contributing

Issues and pull requests are welcome.
