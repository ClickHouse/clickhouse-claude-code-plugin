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

- **Skills** — ClickHouse best practice rules covering schema design, query optimization, and data ingestion, applied automatically when you work with ClickHouse
- **MCP Server** — connects Claude Code to the [ClickHouse Cloud Remote MCP server](https://clickhouse.com/docs/cloud/features/ai-ml/remote-mcp) for schema inspection and read-only SQL queries against your clusters

See [`skills/clickhouse-best-practices/`](./skills/clickhouse-best-practices/) for the full rule set.

## Keeping skills up to date

Best practice rules are sourced from [ClickHouse/agent-skills](https://github.com/ClickHouse/agent-skills) and kept in sync via a weekly GitHub Action that pushes upstream changes directly to `main`. The source is tracked as a git submodule at `submodules/agent-skills`.

## License

Apache 2.0 — see [LICENSE](./LICENSE) for details.
