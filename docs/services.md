# Service Inventory

> 31 project codebases, 44 service definitions, 70+ running containers
>
> [Back to README](../README.md) | [Architecture](architecture.md) | [Observability](observability.md)

## AI Products (6 services)

| Service | Stack | Status |
|---------|-------|--------|
| **FinePrint** | Next.js, TypeScript, Gemini, PostgreSQL, Redis | [Live](https://tos.herakles.dev) |
| **Quits.AI** | AI-powered analysis | Running |
| **MBI-QC** | Quality control automation | Running |
| **Claude Trader Pro** | Python, FastAPI, React, WebSocket, PostgreSQL | Running |
| **V11 Agent Orchestrator** | JSON Schema, Bash hooks, Claude CLI | Running |
| **Iolaus + Zeus** | Python, FastAPI, React, TypeScript, xterm.js | Authenticated |

## Web Applications (11 services)

| Service | Stack | Status |
|---------|-------|--------|
| **CTA Tracker** | Real-time transit tracking | [Live](https://cta.herakles.dev) |
| **Sextant** | Indoor WiFi positioning | [Live](https://sextant.herakles.dev) |
| **Manifold Visualizer** | Flask, WebGPU, WGSL, Three.js | Authenticated |
| **CK Reynolds Tax** | Business web application | Running |
| **WiFi Designer** | Static HTML/CSS/JS | Healthy |
| **Agents Manifest** | Next.js | Healthy |
| **Moody Time Machine** | Flask + React | Healthy |
| **Keymakers Console** | React + Express | Healthy |
| **Zeus Terminal** | React, xterm.js, WebSocket | Authenticated |
| **Gateway** | Node.js/Express | Running |
| **Portfolio Hub** | Static / Markdown | Healthy |

## APIs & Workers (8 services)

| Service | Purpose |
|---------|---------|
| **Scraper API** | Web scraping and data extraction |
| **SMS Bridge** | Messaging integration |
| **Audio Processing** | Media transcoding and analysis |
| **Event Bus** | Redis pub/sub inter-service messaging |
| **WebSocket Server** | Real-time client push |
| **Background Workers** | Async job processing |
| **Cron Scheduler** | Periodic task execution |
| **Notification Service** | Alert delivery |

## Infrastructure (12 services)

| Service | Purpose |
|---------|---------|
| **Reverse Proxy (nginx)** | SSL termination, subdomain routing, rate limiting |
| **SSO / Auth** | Multi-tenant authentication with MFA and RBAC |
| **Secrets Management** | Encrypted credential storage |
| **Container Orchestration** | Docker Compose lifecycle management |
| **Build Pipeline** | Automated builds with health checks and rollback |
| **DNS / CDN** | Cloudflare edge, DDoS protection |
| **Certificate Manager** | Automated SSL issuance and renewal |
| **Backup Service** | Database and volume snapshots |
| **Log Router** | JSON log forwarding to aggregation |
| **Health Monitor** | Endpoint availability checks |
| **Firewall / WAF** | Network-layer protection |
| **Volume Manager** | Persistent storage orchestration |

## Observability (7 services)

| Service | Purpose |
|---------|---------|
| **Dashboards (Grafana)** | Visualization, alerting, log exploration |
| **Metrics (Prometheus)** | Scraping and time-series storage |
| **Log Aggregation (Loki)** | Structured log collection and search |
| **Log Shipping** | Agent-based log forwarding |
| **Trace Collection (OpenTelemetry)** | Distributed request tracing |
| **Host Metrics Exporter** | CPU, memory, disk, network monitoring |
| **Container Metrics Exporter** | Per-container resource tracking |

---

**Totals: 31 projects | 44 services | 70+ containers**

## Adding a New Service

1. Register in the service inventory
2. Create containerized deployment configuration
3. Configure subdomain routing
4. Add monitoring integration (metrics endpoint + dashboard)
5. Deploy and verify health
