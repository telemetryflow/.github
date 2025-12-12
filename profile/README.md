# 👋 Welcome to TelemetryFlow Platform

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://github.com/telemetryflow/.github/blob/main/docs/assets/tfo-logo-dark.svg">
    <source media="(prefers-color-scheme: light)" srcset="https://github.com/telemetryflow/.github/blob/main/docs/assets/tfo-logo-light.svg">
    <img src="https://github.com/telemetryflow/.github/blob/main/docs/assets/tfo-logo-light.svg" alt="TelemetryFlow Logo" width="80%">
  </picture>

  <h3>Enterprise-Grade Observability Platform for Modern Cloud Infrastructure</h3>

  <p>
    <strong>100% OpenTelemetry Compliant</strong> • Built with <strong>DDD/CQRS</strong> • Production-Ready
  </p>

  [![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](../CHANGELOG.md)
  [![License](https://img.shields.io/badge/license-Apache--2.0-green.svg)](../LICENSE)
  [![NestJS](https://img.shields.io/badge/NestJS-11.x-E0234E?logo=nestjs)](https://nestjs.com/)
  [![Vue](https://img.shields.io/badge/Vue-3.5.24-4FC08D?logo=vue.js)](https://vuejs.org/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.9.3-3178C6?logo=typescript)](https://www.typescriptlang.org/)
  [![ClickHouse](https://img.shields.io/badge/ClickHouse-23+-FFCC00?logo=clickhouse)](https://clickhouse.com/)
  [![OpenTelemetry](https://img.shields.io/badge/OTLP-100%25%20Compliant-success?logo=opentelemetry)](https://opentelemetry.io/)
  [![DDD](https://img.shields.io/badge/Architecture-DDD%2FCQRS-blueviolet)](docs-ddd-backend/)
  [![RBAC](https://img.shields.io/badge/Security-5--Tier%20RBAC-red)](../backend/src/modules/iam/)

</div>

---

## 🎯 What is TelemetryFlow?

**TelemetryFlow** is an enterprise-grade observability platform that provides comprehensive monitoring, logging, and tracing capabilities for modern cloud-native applications. Built from the ground up with **Domain-Driven Design (DDD)** and **CQRS patterns**, it delivers industrial-strength reliability with developer-friendly APIs.

### 🌟 Why Choose TelemetryFlow?

#### ✅ OpenTelemetry Native
- **100% OTLP Compliance** - Full support for metrics, logs, and traces
- **Native Protocol Support** - OTLP/HTTP and OTLP/gRPC
- **Zero Vendor Lock-in** - Standard OpenTelemetry SDKs and collectors
- **Seamless Integration** - Works with existing OTEL instrumentation

#### 🏛️ Enterprise Architecture
- **Domain-Driven Design** - 15+ business modules + 10+ shared modules with clear boundaries
- **CQRS Implementation** - 40+ command/query handlers for optimal performance
- **Event-Driven** - NATS + BullMQ hybrid messaging for real-time events
- **Multi-Tenancy** - Hierarchical isolation (Region → Organization → Workspace → Tenant)
- **Modular Design** - LEGO-pattern modules for easy extension

#### 🔒 Security First
- **5-Tier RBAC System** - Granular role-based access control
- **AWS-Style API Keys** - Dual-key authentication (tfk-*/tfs-*)
- **Argon2id Hashing** - OWASP-recommended cryptographic security
- **MFA Support** - TOTP with backup codes
- **SSO Ready** - Google, GitHub, Azure AD, SAML, OIDC
- **Complete Audit Trail** - Every action logged to ClickHouse

#### ⚡ High Performance
- **ClickHouse Backend** - Columnar storage for 100x query performance
- **Horizontal Scaling** - Stateless authentication and distributed caching
- **Redis Caching** - Sub-millisecond response times
- **Optimized Ingestion** - Handle millions of data points per second

## 💻 Technology Stack

### Backend

| Technology | Version | Purpose |
|-----------|---------|---------|
| **NestJS** | 11.1.9 | Enterprise Node.js framework |
| **TypeScript** | 5.9.3 | Type-safe development |
| **TypeORM** | 0.3.x | Database ORM for PostgreSQL |
| **ClickHouse Client** | Latest | Time-series data storage |
| **Passport JWT** | Latest | Authentication middleware |
| **Argon2** | Latest | Password hashing |
| **OpenTelemetry SDK** | 0.208+ | Self-instrumentation |
| **Swagger** | 11.2.3 | API documentation |
| **BullMQ** | 5.x | Job queue processing |
| **NATS** | 2.x | Event streaming |

### Frontend

| Technology | Version | Purpose |
|-----------|---------|---------|
| **Vue 3** | 3.5.24 | Progressive JavaScript framework |
| **Vite** | 7.2.4 | Lightning-fast build tool |
| **TypeScript** | 5.8.3 | Type-safe development |
| **Naive UI** | 2.43.2 | Component library |
| **Pinia** | 3.0.4 | State management |
| **Vue Router** | 4.6.3 | Routing library |
| **Apache ECharts** | 6.0.0 | Data visualization |
| **UnoCSS** | 66.5.9 | Atomic CSS engine |
| **Axios** | 1.13.2 | HTTP client |
| **Socket.IO** | 4.8.1 | Real-time WebSocket |

### Databases

| Database | Version | Purpose | Performance |
|----------|---------|---------|------------|
| **PostgreSQL** | 15+ | Metadata & users | ACID compliance, JSON support |
| **ClickHouse** | 23+ | Telemetry data | 100x faster than PostgreSQL for analytics |
| **Redis** | 7+ | Cache & sessions | Sub-millisecond response times |

---

## 📚 Comprehensive Documentation

**49 Technical Documentation Files** covering every aspect of the platform:

### Architecture Documentation (5 files)
- System architecture and data flow
- Multi-tenancy implementation
- Security architecture
- Performance optimizations

### Backend Documentation (29 files)
- **Backend Overview** (4 files) - Tech stack, DDD/CQRS patterns, module structure
- **Business Modules** (15 files) - Core, Auth, API Keys, Telemetry, Monitoring, Alerts, SSO, Audit, Dashboard, etc.
- **Shared Modules** (10 files) - Cache, Email, Logger, Queue, Messaging, CORS, ClickHouse, OTEL, UI, Platform

### Frontend Documentation (5 files)
- Vue 3 architecture overview
- Technology stack and module structure
- State management with Pinia
- Routing and data visualization with ECharts 6.0

### Shared Resources (4 files)
- Database schema and quick reference
- OTLP ingestion guide with SDK examples
- Naming conventions and coding standards

### Deployment Documentation (4 files)
- Docker Compose deployment guide
- Kubernetes deployment
- Environment configuration
- Production deployment checklist

**Total:** 52,000+ lines of documentation | 151+ Mermaid diagrams

---

## 🗺️ Roadmap

### Current: v1.0.0-CE (Production Ready - Community Edition)

✅ **Completed Features:**
- Full OTLP support (metrics, logs, traces, exemplars)
- API Key authentication with AWS-style dual keys (tfk-*/tfs-*)
- 5-Tier RBAC system with 22 permissions
- Multi-tenancy architecture (Region → Org → Workspace → Tenant)
- DDD/CQRS implementation (40+ handlers)
- 15 backend business modules + 10 shared modules
- Modern Vue 3 frontend with Naive UI
- Real-time WebSocket updates with Socket.IO
- ECharts 6.0 data visualization
- Comprehensive documentation (49 files, 52,000+ lines, 151+ diagrams)
- Complete test infrastructure (280+ tests, 88-92% coverage)
- Docker Compose & Kubernetes deployment guides

## 📊 Project Statistics

| Metric | Count | Notes |
|--------|-------|-------|
| **Backend Modules** | 15+ | Core business modules (DDD) |
| **Backend Shared Modules** | 10+ | Reusable infrastructure modules |
| **Frontend Modules** | 12+ | Feature modules |
| **CQRS Handlers** | 40+ | Commands + Queries |
| **API Endpoints** | 120+ | RESTful APIs |
| **Database Tables (PostgreSQL)** | 35+ | Metadata & users |
| **Database Tables (ClickHouse)** | 10+ | Telemetry data |
| **Lines of Code** | 110,000+ | TypeScript |
| **Test Cases** | 280+ | Unit + E2E |
| **Test Coverage** | 88-92% | Backend modules |
| **Documentation Files** | 49 | Comprehensive technical docs |
| **Documentation Lines** | 52,000+ | Detailed technical content |
| **Mermaid Diagrams** | 151+ | Architecture visualizations |
| **OpenAPI Spec** | 2,866 lines | Complete API spec |
| **Docker Services** | 15+ | PostgreSQL, ClickHouse, Redis, NATS, Backend, Frontend, Monitoring stack |

---

## 🏆 Key Achievements

### ✅ Production-Ready Features
- ✅ **100% OpenTelemetry Compliant** - Full OTLP support for metrics, logs, traces
- ✅ **Enterprise Security** - AWS-style API keys with Argon2id hashing
- ✅ **High Test Coverage** - 88-92% backend coverage with 280+ tests
- ✅ **Complete Documentation** - 49 comprehensive files with 52,000+ lines and 151+ diagrams
- ✅ **OpenAPI Specification** - 2,866 lines of detailed API documentation
- ✅ **DDD/CQRS Architecture** - 15+ backend modules with 40+ CQRS handlers
- ✅ **Multi-Tenancy** - Hierarchical isolation with automatic context injection

### 🎖️ Technical Excellence
- **Domain-Driven Design** - Clean architecture with clear module boundaries
- **CQRS Pattern** - Optimized read/write operations
- **Event Sourcing** - Complete audit trail in ClickHouse
- **Type Safety** - 100% TypeScript across frontend and backend
- **Performance** - ClickHouse provides 100x query performance vs traditional SQL
- **Scalability** - Stateless authentication enables horizontal scaling
- **Documentation** - 49 comprehensive files with 151+ Mermaid diagrams covering architecture, modules, deployment, and best practices

### 🚀 Developer Experience
- **5-Minute Setup** - Bootstrap complete platform with `pnpm bootstrap`
- **Hot Module Reload** - Vite 7.2.4 provides lightning-fast HMR
- **Interactive API Docs** - Swagger UI with live testing
- **Comprehensive Documentation** - 49 technical files covering architecture, modules, deployment
- **Visual Documentation** - 151+ Mermaid diagrams for architecture understanding
- **Integration Guides** - OTLP integration examples for multiple programming languages
- **Clear Error Messages** - Detailed validation errors with fix suggestions

---

## 🔒 Security & Compliance

### Security Features

✅ **Authentication**
- JWT with refresh tokens
- TOTP-based MFA (Google Authenticator, Authy)
- SSO (Google, GitHub, Azure AD, SAML, OIDC)
- API keys with Argon2id hashing

✅ **Authorization**
- 5-tier RBAC system
- Permission-based access control (22 permissions)
- Multi-tenant data isolation
- Workspace-level resource quotas

✅ **Audit & Compliance**
- Complete audit trail in ClickHouse
- All API key operations logged
- User action tracking
- Security event monitoring

✅ **Data Protection**
- Encryption at rest (optional)
- TLS/SSL for data in transit
- Password complexity requirements
- Automatic session timeout

### Compliance Readiness

| Standard | Status | Notes |
|----------|--------|-------|
| **SOC2 Type II** | ✅ Ready | Audit trail, access controls, encryption |
| **ISO 27001** | ✅ Ready | Information security management |
| **GDPR** | ✅ Ready | Data privacy, right to erasure, consent |
| **HIPAA** | ⚠️ Partial | Additional encryption required |
| **PCI DSS** | ⚠️ Partial | Additional controls required |

### Cloud Providers

| Provider | Status | Documentation |
|----------|--------|---------------|
| **AWS** | ✅ Ready | ECS, EKS, RDS, ElastiCache |
| **Google Cloud** | ✅ Ready | GKE, Cloud SQL, Memorystore |
| **Azure** | ✅ Ready | AKS, Azure Database, Redis Cache |
| **DigitalOcean** | ✅ Ready | Kubernetes, Managed PostgreSQL |

---

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### Ways to Contribute

1. **Code Contributions**
   - Fix bugs
   - Add new features
   - Improve performance
   - Enhance documentation

2. **Bug Reports**
   - Report issues on GitHub
   - Provide reproduction steps
   - Include logs and screenshots

3. **Feature Requests**
   - Suggest new features
   - Propose architecture improvements
   - Share use cases

4. **Documentation**
   - Improve existing docs
   - Add tutorials
   - Translate documentation

---

## 📄 License

**Apache License 2.0**

```
Copyright 2024-2026 DevOpsCorner Indonesia

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

See [LICENSE](../LICENSE) for full details.

---

## 🙏 Acknowledgments

Built with these amazing open-source technologies:

| Project | Description |
|---------|-------------|
| **[NestJS](https://nestjs.com/)** | Enterprise Node.js framework |
| **[Vue 3](https://vuejs.org/)** | Progressive JavaScript framework |
| **[ClickHouse](https://clickhouse.com/)** | Fast columnar database |
| **[OpenTelemetry](https://opentelemetry.io/)** | Observability standard |
| **[Apache ECharts](https://echarts.apache.org/)** | Visualization library |
| **[Soybean Admin](https://github.com/soybeanjs/soybean-admin)** | Vue 3 admin template |
| **[Naive UI](https://www.naiveui.com/)** | Component library |
| **[TypeORM](https://typeorm.io/)** | TypeScript ORM |
| **[Vite](https://vitejs.dev/)** | Next-generation build tool |
| **[Pinia](https://pinia.vuejs.org/)** | Vue 3 state management |

Special thanks to all contributors and the open-source community!

---

## 📈 Performance Benchmarks

| Operation | Performance | Notes |
|-----------|-------------|-------|
| **Metric Ingestion** | 100K/sec | Single node |
| **Log Ingestion** | 50K/sec | Single node |
| **Trace Ingestion** | 10K/sec | Single node |
| **Query Latency (p50)** | 50ms | Aggregated metrics |
| **Query Latency (p99)** | 200ms | Complex queries |
| **UI Response Time** | < 100ms | Dashboard loading |
| **Storage Efficiency** | 10:1 | Compression ratio |
| **Concurrent Users** | 1,000+ | WebSocket connections |

---

## 🌐 Live Demo

**Coming Soon:** Public demo environment

---

<div align="center">

**Built with ❤️ by [DevOpsCorner Indonesia](https://github.com/devopscorner)**

**Version**: 1.0.0-CE | **Status**: Production Ready | **License**: Apache 2.0

---

⭐ **Star this repository** if you find it useful!

🐛 **Report bugs** via [GitHub Issues](https://github.com/telemetryflow/telemetryflow-platform/issues)

💡 **Share ideas** via [GitHub Discussions](https://github.com/telemetryflow/telemetryflow-platform/discussions)

</div>
