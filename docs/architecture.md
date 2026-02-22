# Hercules Platform Architecture

## System Overview

```
                        Internet
                           |
                    +------v------+
                    |  CDN / WAF  |  DDoS protection, DNS
                    +------+------+
                           |
                    +------v------+
                    | Reverse Proxy|  SSL termination, rate limiting
                    |              |  subdomain routing
                    +------+------+
                           |
         +-----------------+-----------------+
         |                 |                 |
  +------v------+  +------v------+  +-------v-------+
  |   Gateway   |  |  App Layer  |  | Observability |
  |             |  |  Docker     |  |   Stack       |
  +------+------+  +------+------+  +---------------+
         |                |
         |         +------v------+
         |         | Databases   |
         |         +-------------+
         |
  +------v------+
  |  Auth Layer  |  SSO + MFA
  |              |  RBAC
  +--------------+
```

## Design Decisions

### Hybrid Process + Container Architecture

The gateway runs as a lightweight process while applications run in isolated Docker containers. This gives us:

- **Fast gateway restarts** — No container build/pull overhead
- **Isolated app environments** — Each app has its own dependencies
- **Simple hot-reload** — File-watch for gateway development
- **Independent scaling** — Apps can be rebuilt without touching the gateway

### Subdomain-Per-App Routing

Each application gets its own subdomain rather than path-based routing. Benefits:

- Complete isolation between apps (no shared cookies, no path conflicts)
- Individual SSL certificates via automated issuance
- Per-app rate limiting zones
- Clean URLs for portfolio presentation

### Event-Driven Communication

Services communicate via pub/sub messaging and WebSocket rather than synchronous HTTP:

- Decoupled services — publishers don't know about subscribers
- Real-time updates — pushes to connected clients
- Resilience — failed consumers don't block publishers
- Audit trail — events can be logged and replayed

### Observability-First

Every service is instrumented from day one:

- Metrics scraped from each service
- Structured JSON logs aggregated centrally
- Per-service dashboards and alerting
- Distributed tracing across service boundaries

## Deployment Pipeline

```
Code change -> Build -> Pre-deploy health check -> Rolling restart -> Post-deploy verification -> Auto-rollback on failure
```

Zero-downtime deployment with health checks at each stage and automated rollback if the new deployment fails verification.

## Security Layers

| Layer | Purpose |
|-------|---------|
| **Edge** | DDoS protection, WAF, bot management |
| **TLS** | HTTPS for all subdomains |
| **Auth** | SSO, MFA, role-based access control |
| **Network** | Service isolation, no direct public access |
| **Secrets** | Encrypted at rest, never committed to version control |
| **Rate Limiting** | Multi-layer, per-IP sliding windows |
