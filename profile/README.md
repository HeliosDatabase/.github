# HeliosDatabase

HeliosDatabase builds developer-first database infrastructure for local AI systems, edge workloads, and application data platforms.

The public portfolio focuses on small-footprint databases, intelligent database routing, migration tooling, AI-ready developer tooling, and SDKs that make HeliosDB easier to embed in real products.

## Public Repositories

- [HeliosDB-Nano](https://github.com/HeliosDatabase/HeliosDB-Nano) - embedded SQL database for local-first apps, AI memory, edge analytics, and fast developer workflows. A single self-contained binary that speaks the PostgreSQL and MySQL wire protocols natively, with HNSW vector search, full-text search, copy-on-write branching, and time-travel queries. Runs embedded in-process, as a server, or as an MCP server for AI agents.
- [HeliosDB-Proxy](https://github.com/HeliosDatabase/HeliosDB-Proxy) - programmable data plane for PostgreSQL-wire-compatible databases. Connection pooling, query routing, failover with transaction replay, caching, auth, and rate limiting at the wire-protocol level, extensible with sandboxed WebAssembly plugins. Works with PostgreSQL, HeliosDB, and other PostgreSQL-protocol backends without application changes.
- [Any2HeliosDB](https://github.com/HeliosDatabase/Any2HeliosDB) - migration toolkit for moving Oracle, MySQL, PostgreSQL, and SQL Server into HeliosDB or into stock PostgreSQL. Interactive setup wizard, parallel and resumable data loading, a live migration monitor, structural and row-level validation, and change-data-capture for cutover. The command-line tool is `a2h`.
- [HeliosDB-CodeKB-MCP](https://github.com/HeliosDatabase/HeliosDB-CodeKB-MCP) - Model Context Protocol server that turns codebases and documentation into a queryable knowledge base for Claude Code, Codex, Cursor, Aider, and other MCP clients.
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

Database branching is the feature most relevant to agentic workloads: an agent run can fork the database, operate on real data, and have the branch discarded afterwards, leaving the original untouched.

### Migration With Any2HeliosDB

Any2HeliosDB moves existing databases onto HeliosDB, or onto stock PostgreSQL, over the PostgreSQL wire protocol.

```text
Oracle / MySQL / PostgreSQL / SQL Server
        |
        v
Any2HeliosDB (a2h)
  - setup wizard and connection smoke tests
  - parallel, resumable data load
  - live migration monitor
  - structural and row-level validation
  - change data capture for cutover
        |
        v
HeliosDB   or   stock PostgreSQL
```

The validation and change-data-capture stages are the point: row counts and column values are checked against the source, and changes continue to stream while validation runs, so cutover does not require freezing the source database.

Because stock PostgreSQL is a first-class target, Any2HeliosDB is usable as a general Oracle, MySQL, or SQL Server to PostgreSQL migrator, independently of the rest of this portfolio.

### HeliosDB CodeKB MCP

HeliosDB-CodeKB-MCP exposes repository knowledge through the Model Context Protocol.

```text
Claude Code / Codex / Cursor / MCP Client
        |
        v
HeliosDB-CodeKB-MCP
        |
        v
Code, docs, architecture notes, examples, release notes
```

The goal is to give AI coding tools precise, evidence-backed answers from the actual codebase instead of relying only on prompt context. Typical uses include architecture discovery, implementation evidence, onboarding, release analysis, and cross-repository knowledge retrieval.

### SDKs And Integrations

HeliosDB-SDKs keeps client libraries, integration packages, command-line tooling, and developer examples aligned with the public database components.

The SDK layer is where application developers should start when they want to connect HeliosDB components to application frameworks, automation systems, IDEs, local tools, or AI workflows.

## Licensing

Every public repository in this organization is licensed under Apache-2.0. Each repository carries the full licence text in its own `LICENSE` file.

## Public Documentation

Public documentation and product pages are maintained through the HeliosDB website and documentation channels. Some enterprise, internal, and investor-facing materials are intentionally not published from this organization profile.
