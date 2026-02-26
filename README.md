# Hercules Platform

Production microservices infrastructure running **70 Docker containers** across **31 projects** with event-driven architecture, AI agent orchestration, and full observability.

**Live at [herakles.dev](https://herakles.dev)** | [Resume (PDF)](D-Michael-Piscitelli-Resume.pdf) | [Resume](RESUME.md) | [hello@herakles.dev](mailto:hello@herakles.dev)

> **Docs:** [Architecture](docs/architecture.md) | [Services](docs/services.md) | [Observability](docs/observability.md)

## Architecture

```
                        +---------------+
                        |    nginx      |  SSL termination, rate limiting
                        |   gateway     |  routing to 31+ projects
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
  |              |     |  cache + pub/sub  |    |               |
  +--------------+     +-------------------+    +---------------+
         |                      |                      |
  +------+----------------------+----------------------+
  |  Observability Stack (dashboards, metrics, logs, traces)
  +-------------------------------------------------------------
```

## Services (31 projects, 70 containers)

| Category | Count | Examples |
|----------|-------|---------|
| **AI Products** | 6 | FinePrint, Quits.AI, MBI-QC, Claude Trader |
| **Web Applications** | 11 | Zeus Terminal, CK Reynolds Tax, CTA Tracker |
| **APIs & Workers** | 8 | Scraper API, SMS Bridge, Audio Processing |
| **Infrastructure** | 12 | Reverse proxy, SSO, secrets management, container orchestration |
| **Observability** | 7 | Dashboards, metrics, log aggregation, distributed tracing |

## Key Capabilities

- **[AI Agent Orchestration](https://github.com/HeraclesBass/claude-orchestrator-showcase)**: 103 specialized agents coordinated by meta-orchestrator with wave-based parallel execution, 48 skills, 12 lifecycle hooks ([architecture showcase](https://github.com/HeraclesBass/claude-orchestrator-showcase))
- **Event-Driven Communication**: Redis pub/sub and WebSocket for real-time inter-service messaging
- **Multi-Tenant Auth**: SSO with MFA and role-based access control
- **Zero-Downtime Deployment**: Automated builds, health checks, rollback capability via Docker Compose
- **Full Observability**: Grafana dashboards per service, Loki log aggregation, Prometheus metrics scraping, automated alerting
- **66 Live Domains**: SSL-terminated nginx reverse proxy with rate limiting zones

## Tech Stack

| Layer | Technologies |
|-------|-------------|
| **Languages** | Python, TypeScript, JavaScript, Go, Bash, SQL |
| **Frontend** | React, Next.js 14, Tailwind CSS, Three.js |
| **Backend** | Node.js, Flask, Express, FastAPI, WebSocket |
| **AI/ML** | Gemini 2.5 Pro, Claude API, OpenAI, Ollama |
| **Databases** | PostgreSQL, Redis, MongoDB, SQLite |
| **Infrastructure** | Docker, Linux, reverse proxy, container orchestration |
| **Observability** | Grafana, Prometheus, Loki, OpenTelemetry |
| **Security** | SSO + MFA, secrets management, fail-closed rate limiting |

## Metrics

| Metric | Value |
|--------|-------|
| Running containers | 70+ |
| Active projects | 30+ |
| Live subdomains | 60+ |
| Codebase | 400K+ LOC |
| Database engines | PostgreSQL, Redis, MongoDB |
| Uptime monitoring | Prometheus + Grafana alerting |

## Project Repos

| Project | Description | Stack |
|---------|-------------|-------|
| [tos-analyzer](https://github.com/HeraclesBass/tos-analyzer) | AI-powered Terms of Service analyzer ([live](https://tos.herakles.dev)) | Next.js, TypeScript, Gemini, PostgreSQL, Redis |
| [claude-trader-pro](https://github.com/HeraclesBass/claude-trader-pro) | Crypto trading platform with AI predictions | Python, FastAPI, React, WebSocket, PostgreSQL |
| [3-body-problem](https://github.com/HeraclesBass/3-body-problem) | GPU-accelerated N-body physics simulation | Python, NVIDIA Warp, OpenGL |
| [manifold-visualizer](https://github.com/HeraclesBass/manifold-visualizer) | WebGPU mathematical surface renderer ([live](https://manifold.herakles.dev)) | Python, Flask, WebGPU, WGSL |
| [claude-orchestrator-showcase](https://github.com/HeraclesBass/claude-orchestrator-showcase) | V11 agent orchestration framework | JSON Schema, Bash hooks |
| [iolaus-zeus](https://github.com/HeraclesBass/iolaus-zeus) | Dual-interface AI platform (CLI + web) | TypeScript, React, Python, FastAPI |

## Live Products

- **[FinePrint](https://tos.herakles.dev)** — AI Terms of Service analyzer
- **[CTA Tracker](https://cta.herakles.dev)** — Real-time Chicago transit tracking
- **[Sextant](https://sextant.herakles.dev)** — Indoor WiFi positioning system
- **Zeus Terminal** — AI-powered web terminal (authenticated)
- **Manifold Visualizer** — WebGPU mathematical surfaces (authenticated)

---

Built and operated by [D. Michael Piscitelli](https://github.com/HeraclesBass) | [herakles.dev](https://herakles.dev) | hello@herakles.dev
