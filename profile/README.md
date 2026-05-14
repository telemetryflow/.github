<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/telemetryflow/.github/raw/main/docs/assets/tfo-logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://github.com/telemetryflow/.github/raw/main/docs/assets/tfo-logo-light.svg">
    <img src="https://github.com/telemetryflow/.github/raw/main/docs/assets/tfo-logo-light.svg" alt="TelemetryFlow Logo" width="80%">
  </picture>

  <h3>Community Enterprise Observability Platform (CEOP)</h3>

  <p>
    <strong>100% OpenTelemetry Compliant</strong> &bull;
    Built with <strong>DDD/CQRS</strong> &bull;
    Production-Ready &bull;
    Apache 2.0 Licensed
  </p>

[![Version](https://img.shields.io/badge/version-1.4.0-orange.svg)](#)
[![License](https://img.shields.io/badge/license-Apache--2.0-green.svg)](#)
[![NestJS](https://img.shields.io/badge/NestJS-11.x-E0234E?logo=nestjs)](https://nestjs.com/)
[![Vue](https://img.shields.io/badge/Vue-3.x-4FC08D?logo=vue.js)](https://vuejs.org/)
[![Go](https://img.shields.io/badge/Go-1.26+-00ADD8?logo=go)](https://golang.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.x-3178C6?logo=typescript)](https://www.typescriptlang.org/)
[![ClickHouse](https://img.shields.io/badge/ClickHouse-23+-FFCC00?logo=clickhouse)](https://clickhouse.com/)
[![OpenTelemetry](https://img.shields.io/badge/OTLP-100%25%20Compliant-success?logo=opentelemetry)](https://opentelemetry.io/)

</div>

---

## What is TelemetryFlow?

**TelemetryFlow** is an **enterprise-grade, open-source observability platform** that provides unified telemetry collection, storage, analysis, and visualization. It is **100% OpenTelemetry Protocol (OTLP) compliant**, designed as an open-source alternative to commercial solutions like Datadog, New Relic, and Dynatrace.

### Why Choose TelemetryFlow?

**OpenTelemetry Native**
- 100% OTLP Compliance — Full support for metrics, logs, traces, and exemplars
- Zero Vendor Lock-in — Standard OpenTelemetry SDKs and collectors
- Dual Endpoint Support — Community v1 + Platform v2 on same collector

**Enterprise Architecture**
- Domain-Driven Design — 25+ bounded contexts with clear module isolation
- CQRS Implementation — Optimized read/write with 40+ command/query handlers
- Event-Driven — NATS + BullMQ hybrid messaging for real-time events
- Multi-Tenancy — Hierarchical isolation (Region → Organization → Workspace → Tenant)

**Security First**
- 5-Tier RBAC System — Granular role-based access control
- AWS-Style API Keys — Dual-key authentication (tfk-*/tfs-*) with Argon2id hashing
- MFA + SSO — TOTP, Google, GitHub, Azure AD, Okta, SAML, OIDC
- Complete Audit Trail — Every action logged to ClickHouse

---

## Product Ecosystem

```mermaid
graph TB
    subgraph SDKs["Language SDKs"]
        PYSDK["Python SDK"]
        GOSDK["Go SDK"]
    end

    subgraph Collection["Data Collection"]
        AGENT["TFO Agent v1.2.0<br/>39+ Integrations"]
        COLLECTOR["TFO Collector v1.2.1<br/>OCB Native"]
    end

    subgraph Platform["Platform Core"]
        MONO["Platform Monolith<br/>NestJS + Vue 3"]
        VIZ["TFO-Viz<br/>Standalone Dashboard"]
    end

    subgraph AI["AI Layer"]
        GOMCP["Go MCP Server"]
        PYMCP["Python MCP Server"]
    end

    SDKs -->|"OTLP"| Collection
    Collection -->|"OTLP v1/v2"| Platform
    Collection -->|"OTLP"| VIZ
    Platform -->|"MCP"| AI

    style SDKs fill:#e8f5e9,stroke:#2e7d32,color:#000
    style Collection fill:#e3f2fd,stroke:#1565c0,color:#000
    style Platform fill:#fff3e0,stroke:#e65100,color:#000
    style AI fill:#f3e5f5,stroke:#6a1b9a,color:#000
```

### Ecosystem Components

| Repository | Language | Description |
|-----------|----------|-------------|
| [telemetryflow-platform](https://github.com/telemetryflow/telemetryflow-platform) | TypeScript (NestJS + Vue 3) | Core platform — backend API, frontend dashboard, dual database |
| [telemetryflow-agent](https://github.com/telemetryflow/telemetryflow-agent) | Go 1.26 | Infrastructure agent — replaces Prometheus, KSM, node-exporter, FluentBit |
| [telemetryflow-collector](https://github.com/telemetryflow/telemetryflow-collector) | Go 1.26 | OCB-native OTLP collector with TFO custom components |
| [telemetryflow-python-sdk](https://github.com/telemetryflow/telemetryflow-python-sdk) | Python 3.12+ | Python SDK for instrumenting applications |
| [telemetryflow-go-sdk](https://github.com/telemetryflow/telemetryflow-go-sdk) | Go 1.24+ | Go SDK for instrumenting applications |
| [telemetryflow-viz](https://github.com/telemetryflow/telemetryflow-viz) | TypeScript (Vue 3) | Standalone observability visualization dashboard |
| [telemetryflow-go-mcp](https://github.com/telemetryflow/telemetryflow-go-mcp) | Go | MCP server for Claude AI integration |
| [telemetryflow-python-mcp](https://github.com/telemetryflow/telemetryflow-python-mcp) | Python | MCP server for Claude AI integration |
| [telemetryflow-overview](https://github.com/telemetryflow/telemetryflow-overview) | Markdown | Comprehensive platform documentation |

---

## TFO Agent v1.2.0

The TFO Agent consolidates multiple monitoring tools into a single Go binary:

```mermaid
graph TB
    subgraph Replaced["Replaces These Tools"]
        PROM["Prometheus"]
        KSM["kube-state-metrics"]
        NE["node-exporter"]
        FB["FluentBit"]
        CAD["cAdvisor"]
    end

    subgraph Agent["TFO Agent (Go 1.26, OTEL SDK v1.43.0)"]
        NE_MOD["Node Exporter<br/>CPU, Memory, DiskIO,<br/>Filesystem, Network"]
        K8S_MOD["Kubernetes<br/>Nodes, Pods, Deployments,<br/>Services, HPA, PDB"]
        CAD_MOD["cAdvisor<br/>Container CPU, Memory,<br/>Network, Filesystem"]
        DB_MOD["Databases<br/>MySQL, PostgreSQL, MongoDB,<br/>MSSQL, ClickHouse, Aurora,<br/>CockroachDB, TimescaleDB"]
        EBPF_MOD["eBPF<br/>Syscalls, Network,<br/>File I/O, Scheduler"]
    end

    Replaced -.->|"Consolidated"| Agent
    Agent -->|"OTLP"| PLATFORM["TFO Platform"]

    style Replaced fill:#ffebee,stroke:#c62828,color:#000
    style Agent fill:#e8f5e9,stroke:#2e7d32,color:#000
```

**Key Capabilities:**
- 9 database collectors (MySQL, PostgreSQL, MongoDB, MSSQL, ClickHouse, CockroachDB, Aurora, TimescaleDB, SQLite3)
- 28 eBPF kernel-level metrics across 7 categories
- 39+ third-party integrations (Cloud, APM, OSS Observability, Streaming, Network)
- Docker container monitoring (32 per-container metrics)
- Disk-backed buffer for offline resilience
- Cross-platform: Linux, macOS, Windows

---

## TFO Collector v1.2.1

Enterprise-grade OTLP collector built on **OpenTelemetry Collector Builder (OCB)** with 85+ community components and 4 custom TFO components:

| Component | Type | Description |
|-----------|------|-------------|
| `tfootlp` | Receiver | OTLP receiver with v1/v2 dual endpoint support |
| `tfo` | Exporter | Platform exporter with automatic auth header injection |
| `tfoauth` | Extension | API key management for TFO authentication |
| `tfoidentity` | Extension | Collector identity and resource enrichment |

**Pipeline Architecture:**
- **Traces**: tfootlp → k8sattributes → batch → tfo + spanmetrics + servicegraph
- **Metrics**: tfootlp → k8sattributes → transform → batch → tfo + prometheus
- **Logs**: tfootlp → k8sattributes → batch → tfo

---

## Platform Capabilities

### Monitoring Modules (25+ Backend Modules)

| Category | Modules |
|----------|---------|
| **Core** | Auth, IAM, Tenancy, Cache |
| **Telemetry** | Metrics, Logs, Traces, Exemplars, Correlations |
| **Monitoring** | Agent, Kubernetes, VM, Uptime, Status Page, Service Map, Network Map, DB Monitoring |
| **Platform** | Dashboard, Alerting, Retention, Subscription, API Keys, Notification, SSO, Audit |
| **Intelligence** | AI Intelligence, LLM, Query (TFQL), Data Masking |
| **Reporting** | Reporting |

### Database Monitoring

Query Analytics (QAN) with native collectors for 9 databases:
- **MySQL/MariaDB/Percona** — InnoDB, replication, Galera, query analytics
- **PostgreSQL** — pg_stat_statements, activity, bgwriter, replication
- **Amazon Aurora** — 60+ CloudWatch metrics via AWS SDK
- **MongoDB** — Server status, replica set, sharding, profiler
- **MSSQL** — Wait stats, perf counters, query store, index usage
- **ClickHouse, CockroachDB, TimescaleDB, SQLite3**

### Component Registry System

| Registry | Entries | ID Scheme |
|----------|---------|-----------|
| Graph Registry | 260+ | XXX1#### |
| Stat Panel Registry | 158 | XXX2#### |
| DataTable Registry | 41 | XXX3#### |

**459 total** registry entries across 23 module codes, rendered by Vue composables → 13 chart types via `RegistryGraphPanel` (3 variants: default/mini/panel).

### Data Architecture

```mermaid
graph LR
    RAW["Raw<br/>TTL: 7-30d"]
    ONE_M["1m Agg<br/>TTL: 30-90d"]
    ONE_H["1h Agg<br/>TTL: 90-180d"]
    ONE_D["1d Agg<br/>TTL: 365d+"]

    RAW -->|"MV"| ONE_M -->|"MV"| ONE_H -->|"MV"| ONE_D

    style RAW fill:#ffebee,stroke:#c62828,color:#000
    style ONE_M fill:#fff3e0,stroke:#e65100,color:#000
    style ONE_H fill:#e3f2fd,stroke:#1565c0,color:#000
    style ONE_D fill:#e8f5e9,stroke:#2e7d32,color:#000
```

---

## Quick Start

```bash
# Clone and setup
git clone https://github.com/telemetryflow/telemetryflow-platform.git
cd telemetryflow-platform

# Start infrastructure
docker-compose --profile core up -d

# Install, migrate, seed
pnpm install && pnpm db:migrate && pnpm db:seed

# Start development
pnpm dev
```

| Service | URL |
|---------|-----|
| Frontend Dashboard | http://localhost:8080 |
| Backend API | http://localhost:3000/api/v2 |
| API Documentation | http://localhost:3000/api/docs |
| Health Check | http://localhost:3000/health |

---

## Project Statistics

| Metric | Count |
|--------|-------|
| Backend Modules | 25+ (DDD/CQRS) |
| Frontend Component Registry | 459 entries |
| API Endpoints | 120+ |
| Database Collectors | 9 databases |
| 3rd Party Integrations | 39+ |
| eBPF Metrics | 28 kernel-level |
| ClickHouse Materialized Views | 24 |
| Queue Workers | 6 (BullMQ) |

---

## Technology Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | Vue 3, TypeScript, Pinia, Naive UI, ECharts 5.x, Vite 6.x |
| **Backend** | NestJS 11.x, TypeORM, BullMQ, NATS |
| **Databases** | PostgreSQL 16, ClickHouse 23+, Redis 7+ |
| **Agent** | Go 1.26, OTEL SDK v1.43.0 |
| **Collector** | Go 1.26, OCB (Core v1.58.0, Contrib v0.152.0) |
| **Deployment** | Docker Compose, Kubernetes + Helm |

---

## Contributing

We welcome contributions! See individual repository CONTRIBUTING.md files for guidelines.

- **License**: Apache 2.0
- **Built by**: [DevOpsCorner Indonesia](https://devopscorner.id)
- **Website**: [telemetryflow.id](https://telemetryflow.id)
- **Docs**: [docs.telemetryflow.id](https://docs.telemetryflow.id)

---

<div align="center">

**Built with ❤️ by [DevOpsCorner Indonesia](https://github.com/devopscorner)**

**Version**: 1.4.0 | **Status**: Production Ready | **License**: Apache 2.0

---

⭐ **Star this repository** if you find it useful!

🐛 **Report bugs** via [GitHub Issues](https://github.com/telemetryflow/telemetryflow-platform/issues)

💡 **Share ideas** via [GitHub Discussions](https://github.com/telemetryflow/telemetryflow-platform/discussions)

</div>
