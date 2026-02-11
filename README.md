# D. Michael Piscitelli

**Full-Stack Software Engineer** | Python, Docker, TypeScript, React, PostgreSQL

I build multi-tiered, loosely coupled systems. Currently running a microservices platform with **70+ Docker containers** across **44 services** with event-driven architecture, automated CI/CD, and full observability.

10 years of telecom infrastructure domain expertise. I understand both the code and the business it serves.

---

## Platform Architecture

```
                        ┌─────────────┐
                        │   nginx     │ SSL termination, reverse proxy
                        │  gateway    │ routing to 44+ services
                        └──────┬──────┘
                               │
              ┌────────────────┼────────────────┐
              │                │                │
     ┌────────┴───────┐ ┌─────┴──────┐ ┌───────┴────────┐
     │  Web Apps       │ │  APIs       │ │  Workers       │
     │  React/Next.js  │ │  Flask/Node │ │  Background    │
     │  frontends      │ │  backends   │ │  processors    │
     └────────┬───────┘ └─────┬──────┘ └───────┬────────┘
              │                │                │
              └────────────────┼────────────────┘
                               │
         ┌─────────────────────┼─────────────────────┐
         │                     │                     │
  ┌──────┴──────┐    ┌────────┴────────┐    ┌───────┴───────┐
  │ PostgreSQL   │    │  Redis          │    │ MongoDB       │
  │ (primary)    │    │  (cache/pubsub) │    │ (documents)   │
  └─────────────┘    └─────────────────┘    └───────────────┘
         │                     │                     │
  ┌──────┴─────────────────────┴─────────────────────┘
  │  Observability: Grafana + Prometheus + Loki + Alerting
  └──────────────────────────────────────────────────────
```

**70+ Docker containers** | **44 services** | **Automated deployment with health checks & rollback**

---

## Selected Projects

### Hercules Microservices Platform
`Python` `Docker` `Node.js` `nginx` `PostgreSQL` `Redis` `Grafana` `Prometheus`

Production infrastructure running 44+ loosely coupled services with:
- Event-driven inter-service communication (Redis pub/sub, WebSocket)
- Multi-tenant authentication (Authelia/LDAP/SSO with RBAC)
- Continuous delivery pipelines with automated builds, health monitoring, and rollback
- Full observability: Grafana dashboards, Loki log aggregation, Prometheus metrics
- Container lifecycle management, port allocation, and SSL termination

### TOS Analyzer
`Python` `PostgreSQL` `Redis` `NLP`

Automated Terms of Service analysis tool. Ingests ToS documents, applies NLP to identify concerning clauses, tracks changes over time, and generates plain-language summaries. Event-driven processing pipeline with persistent storage and caching.

[View Repository →](https://github.com/HeraclesBass/tos-analyzer)

### Sextant — Location-Aware WiFi Navigation
`Next.js` `PostgreSQL` `Redis` `Spatial Queries` `Docker`

Indoor positioning and WiFi signal mapping application with real-time location tracking, signal strength analysis, and spatial database queries. Supports disconnected-mode operation for intermittent connectivity environments.

### Fiber Tree Network Visualizer
`React` `Node.js` `Docker`

Interactive fiber optic network topology explorer. Hierarchical tree-view visualization of network infrastructure and design dependencies. Built for telecom engineering teams managing large-scale fiber deployments.

### Claude Trader Pro
`Flask` `React` `PostgreSQL` `Redis` `WebSocket`

Event-driven trading platform with real-time market data ingestion, strategy backtesting engine, and multi-service architecture: API gateway, trade execution engine, and background worker processes.

### Quits.ai — Behavioral Health Platform
`Python` `Twilio SMS` `Redis` `PostgreSQL`

AI-powered behavioral intervention system with real-time SMS integration, intelligent trigger pattern recognition, and escalating support protocols. Full SDLC from requirements through deployment and user support.

---

## Technical Stack

| Layer | Technologies |
|-------|-------------|
| **Languages** | Python, JavaScript, TypeScript, Go, Bash, SQL |
| **Frontend** | React, Next.js, Tailwind CSS, Three.js |
| **Backend** | Node.js, Flask, Express, REST APIs, WebSocket |
| **Databases** | PostgreSQL, MongoDB, Redis, SQLite |
| **Infrastructure** | Docker, nginx, Linux, Git, CI/CD automation |
| **Observability** | Grafana, Prometheus, Loki, automated alerting |
| **Architecture** | Event-driven, microservices, multi-tenant, SaaS |

---

## Background

10 years in telecom infrastructure at a Dycom Industries subsidiary, leading fiber network design teams. During that time, I built the software tools my teams needed — AI-powered workflow automation, equipment selection apps for field crews, and data processing pipelines. Delivered a major fiber deployment project 1 year ahead of schedule.

Now I build full-stack production systems. The domain expertise stays. The engineering ambition grew.

---

**Contact**: hello@herakles.dev | [LinkedIn](https://www.linkedin.com/in/d-michael-piscitelli-2932a281/)
