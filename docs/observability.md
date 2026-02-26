# Observability Stack

> [Back to README](../README.md) | [Architecture](architecture.md) | [Services](services.md)

## Overview

Full observability across all platform services using a modern monitoring ecosystem. Every service emits structured logs, exposes metrics, and participates in distributed tracing.

## Stack Components

| Component | Role |
|-----------|------|
| **Dashboards** | Visualization, alerting, log exploration |
| **Metrics Engine** | Scraping and time-series storage |
| **Log Aggregation** | Structured log collection and search |
| **Log Shipping** | Agent-based log forwarding |
| **Trace Collection** | Distributed request tracing |
| **Host Metrics** | CPU, memory, disk, network monitoring |
| **Container Metrics** | Per-container resource tracking |

## Structured Logging Standard

All services emit JSON-formatted logs with consistent fields:

```json
{
  "level": "info",
  "service": "service-name",
  "message": "Operation completed",
  "timestamp": "2026-02-22T12:00:00Z"
}
```

Required fields: `level`, `service`, `message`, `timestamp`

## Monitoring

Standard metrics exposed by each service include:
- HTTP request duration and status codes
- Active connection counts
- Custom business metrics per service

## Alerting

Automated alerts cover:
- Service availability
- Error rate spikes
- Resource utilization thresholds
- Certificate expiry monitoring

## Dashboards

- **Platform Overview** — All services at a glance: health, request rates, error rates
- **Per-Service Detail** — Deep dive with logs, metrics, and traces
- **Infrastructure** — Host resource utilization
- **Containers** — Resource usage, restart counts, image freshness
- **Proxy** — Request rates, response times, upstream health
