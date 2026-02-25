# ClickHouse Claude Code Plugin

The official Claude Code Plugin for [ClickHouse](https://clickhouse.com/). Extends Claude Code with ClickHouse best practice skills, rules, and the ClickHouse MCP server.

## Installation

```bash
claude plugin add clickhouse/agent-skills
```

## What's included

- **Skills** — 28 ClickHouse best practice rules covering schema design, query optimization, and data ingestion, applied automatically when you work with ClickHouse
- **MCP Server** — connects Claude Code to the [ClickHouse MCP server](https://mcp.clickhouse.cloud/mcp) for live documentation and query capabilities
- **Rules** — ClickHouse-specific rules automatically applied during coding sessions

## Skills overview

| Category | Rules | Impact |
|----------|-------|--------|
| Primary Key Selection | 4 | CRITICAL |
| Data Type Selection | 5 | CRITICAL |
| JOIN Optimization | 5 | CRITICAL |
| Insert Batching | 1 | CRITICAL |
| Mutation Avoidance | 2 | CRITICAL |
| Partitioning Strategy | 4 | HIGH |
| Skipping Indices | 1 | HIGH |
| Materialized Views | 2 | HIGH |
| Async Inserts | 2 | HIGH |
| OPTIMIZE Avoidance | 1 | HIGH |
| JSON Usage | 1 | MEDIUM |

See [`skills/clickhouse-best-practices/`](./skills/clickhouse-best-practices/) for details.

## License

Apache 2.0 — see [LICENSE](./LICENSE) for details.
