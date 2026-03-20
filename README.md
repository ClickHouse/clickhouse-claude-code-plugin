# ClickHouse Claude Code Plugin

The official Claude Code Plugin for [ClickHouse](https://clickhouse.com/). Extends Claude Code with ClickHouse best practice skills, rules, and the ClickHouse MCP server.

## Installation

Install from the Claude Code plugin directory (pending marketplace approval):

```bash
claude plugin install clickhouse@claude-plugins-official
```

Or clone the repo and load it directly:

```bash
git clone --recursive https://github.com/ClickHouse/clickhouse-claude-code-plugin
claude --plugin-dir ./clickhouse-claude-code-plugin
```

## What's included

- **Skills** — 28 ClickHouse best practice rules covering schema design, query optimization, and data ingestion, applied automatically when you work with ClickHouse
- **MCP Server** — connects Claude Code to the [ClickHouse Cloud Remote MCP server](https://clickhouse.com/docs/cloud/features/ai-ml/remote-mcp) for schema inspection and read-only SQL queries against your clusters

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

## Keeping skills up to date

Best practice rules are sourced from [ClickHouse/agent-skills](https://github.com/ClickHouse/agent-skills) and kept in sync via a weekly GitHub Action that opens a PR when upstream changes are detected. The source is tracked as a git submodule at `submodules/agent-skills`.

## License

Apache 2.0 — see [LICENSE](./LICENSE) for details.
