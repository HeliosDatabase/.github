# HeliosDatabase

HeliosDatabase builds developer-first database infrastructure for local AI systems, edge workloads, and application data platforms.

The public portfolio focuses on small-footprint databases, intelligent database routing, AI-ready tooling, and SDKs that make HeliosDB easier to embed in real products.

## Public Repositories

Recommended public pins for the organization profile:

- [HeliosDB-Nano](https://github.com/HeliosDatabase/HeliosDB-Nano) - embedded SQL database for local-first apps, AI memory, edge analytics, and fast developer workflows.
- [HeliosDB-Proxy](https://github.com/HeliosDatabase/HeliosDB-Proxy) - database proxy layer for routing, policy enforcement, observability, tenant-aware access, and protocol-aware deployments.
- [HeliosDB-CodeKB-MCP](https://github.com/HeliosDatabase/HeliosDB-CodeKB-MCP) - Model Context Protocol server that turns HeliosDB codebases and documentation into queryable technical knowledge for Claude Code, Codex, and other MCP clients.
- [HeliosDB-SDKs](https://github.com/HeliosDatabase/HeliosDB-SDKs) - client libraries, integrations, CLI tooling, and package metadata for building against HeliosDB projects.
- [HeliosDB-Proxy-Plugins](https://github.com/HeliosDatabase/HeliosDB-Proxy-Plugins) - extension points and plugin examples for HeliosDB Proxy.

## Architecture Themes

### HeliosDB Proxy + HeliosDB Nano

HeliosDB Proxy and HeliosDB Nano are designed to work together when applications need a lightweight local database with deployment-grade routing and policy control.

```text
Application / Agent / Service
        |
        v
HeliosDB Proxy
  - routing and tenancy
  - auth and policy checks
  - query visibility
  - deployment control
        |
        v
HeliosDB Nano
  - embedded SQL
  - local persistence
  - vector/search-oriented workloads
  - edge and AI memory use cases
```

This pairing is useful for local-first applications, private AI agents, edge deployments, customer-specific data sandboxes, and controlled database access from application runtimes.

### HeliosDB Nano For AI

HeliosDB Nano is the public embedded database layer for AI-centric applications. It is intended for cases where data needs to stay close to the agent, application, or device:

- agent memory and conversation state
- local RAG indexes and metadata
- private semantic search
- evaluation traces and experiment data
- edge analytics and small operational datasets
- offline-capable developer workflows

### HeliosDB CodeKB MCP

HeliosDB-CodeKB-MCP exposes repository knowledge through the Model Context Protocol.

```text
Claude Code / Codex / MCP Client
        |
        v
HeliosDB-CodeKB-MCP
        |
        v
Code, docs, architecture notes, examples, release notes
```

The goal is to give AI coding tools precise, evidence-backed answers from the actual codebase instead of relying only on prompt context. Typical uses include investor technical Q&A, architecture discovery, implementation evidence, onboarding, release analysis, and cross-repository knowledge retrieval.

### SDKs And Integrations

HeliosDB-SDKs keeps client libraries, integration packages, command-line tooling, and developer examples aligned with the public database components.

The SDK layer is where application developers should start when they want to connect HeliosDB components to application frameworks, automation systems, IDEs, local tools, or AI workflows.

## Public Documentation

Public documentation and product pages are maintained through the HeliosDB website and documentation channels. Some enterprise, internal, and investor-facing materials are intentionally not published from this organization profile.

