# Hercules Platform

Production microservices infrastructure running **70+ Docker containers** across **44 services** with event-driven architecture, AI agent orchestration, and full observability.

**Live at [herakles.dev](https://herakles.dev)**

## Architecture

```
                        +---------------+
                        |    nginx      |  SSL termination, rate limiting
                        |   gateway     |  routing to 44+ services
                        +-------+-------+
                                |
              +-----------------+-----------------+
              |                 |                 |
     +--------+--------+ +-----+------+ +---------+--------+
     |   Web Apps       | |   APIs      | |   Workers        |
     |   React/Next.js  | |   Flask     | |   Background     |
     |   11 frontends   | |   Node.js   | |   processors     |
     +--------+--------+ +-----+------+ +---------+--------+
              |                 |                 |
              +-----------------+-----------------+
                                |
         +----------------------+----------------------+
         |                      |                      |
  +------+------+     +---------+---------+    +-------+-------+
  | PostgreSQL   |     |  Redis            |    | MongoDB       |
  | 5 instances  |     |  8 instances      |    | (documents)   |
  +--------------+     |  cache + pub/sub  |    +---------------+
                       +-------------------+
         |                      |                      |
  +------+----------------------+----------------------+
  |  Observability: Grafana + Prometheus + Loki + OpenTelemetry
  +-------------------------------------------------------------
```

## Services (44 deployed)

| Category | Count | Examples |
|----------|-------|---------|
| **AI Products** | 6 | FinePrint, Quits.AI, MBI-QC, Claude Trader |
| **Web Applications** | 11 | Zeus Terminal, CK Reynolds Tax, CTA Tracker |
| **APIs & Workers** | 8 | Scraper API, SMS Bridge, Audio Processing |
| **Infrastructure** | 12 | nginx, Authelia SSO, LLDAP, Vault, Portainer |
| **Observability** | 7 | Grafana, Prometheus, Loki, OTEL, exporters |

## Key Capabilities

- **AI Agent Orchestration**: 65+ specialized agents coordinated by meta-orchestrator with wave-based parallel execution
- **Event-Driven Communication**: Redis pub/sub and WebSocket for real-time inter-service messaging
- **Multi-Tenant Auth**: Authelia SSO with LDAP backend, role-based access control
- **Zero-Downtime Deployment**: Automated builds, health checks, rollback capability via Docker Compose
- **Full Observability**: Grafana dashboards per service, Loki log aggregation, Prometheus metrics scraping, automated alerting
- **50+ Live Domains**: SSL-terminated nginx reverse proxy with rate limiting zones

## Tech Stack

| Layer | Technologies |
|-------|-------------|
| **Languages** | Python, TypeScript, JavaScript, Go, Bash, SQL |
| **Frontend** | React, Next.js 14, Tailwind CSS, Three.js |
| **Backend** | Node.js, Flask, Express, FastAPI, WebSocket |
| **AI/ML** | Gemini 2.5 Pro, Claude API, OpenAI, Ollama |
| **Databases** | PostgreSQL (5), Redis (8), MongoDB, SQLite |
| **Infrastructure** | Docker, nginx, Linux, Kubernetes (kind) |
| **Observability** | Grafana, Prometheus, Loki, OpenTelemetry |
| **Security** | Authelia SSO, LLDAP, HashiCorp Vault, fail-closed rate limiting |

## Metrics

| Metric | Value |
|--------|-------|
| Running containers | 70+ |
| Deployed services | 44 |
| Live domains | 50+ |
| Codebase | 85K+ LOC |
| Databases | 14 instances (PostgreSQL, Redis, MongoDB) |
| Uptime monitoring | Prometheus + Grafana alerting |

## Products Built on This Platform

- **[FinePrint](https://fine-print.org)** — AI Terms of Service analyzer
- **[Zeus Terminal](https://terminal.herakles.dev)** — AI-powered development terminal
- **[Quits.AI](https://quits.herakles.dev)** — Behavioral health intervention platform
- **[CTA Tracker](https://cta.herakles.dev)** — Real-time Chicago transit tracking
- **[ICE-Aware](https://iceaware.herakles.dev)** — Geospatial intelligence (20 scrapers, 9.1M records)
- **[Sextant](https://sextant.herakles.dev)** — Indoor WiFi positioning system

---

Built and operated by [D. Michael Piscitelli](https://github.com/HeraclesBass) | [herakles.dev](https://herakles.dev) | hello@herakles.dev
