---
name: setup
description: Guides users through setting up the ClickHouse MCP server connection bundled with this plugin. Use when the user first installs the plugin or has trouble connecting to ClickHouse.
disable-model-invocation: true
---

# ClickHouse Plugin Setup

This plugin includes the [ClickHouse Cloud Remote MCP server](https://clickhouse.com/docs/cloud/features/ai-ml/remote-mcp) at `https://mcp.clickhouse.cloud/mcp`. It provides secure, read-only access to your ClickHouse Cloud clusters.

## Setup Steps

1. **Verify the MCP server is connected**: Check that the ClickHouse MCP server appears in your available tools. If it does, you're ready to go.

2. **Authenticate via OAuth**: The MCP server uses OAuth with your ClickHouse Cloud credentials. Follow the prompts when first connecting to authorize access.

3. **Test the connection**: Try listing databases or running a simple SELECT query to confirm everything works.

## Troubleshooting

- **Server not appearing**: Run `/reload-plugins` to reload plugin MCP servers.
- **Authentication errors**: Re-authenticate by following the OAuth flow when prompted.
- **Connection timeouts**: Verify your network can reach `https://mcp.clickhouse.cloud`. The MCP server is a remote HTTP endpoint and requires internet access.

## Claude Code Timeout Limitation

Claude Code enforces a **30-second timeout** on all MCP tool calls. This cannot be changed by the user or the MCP server. While the `run_select_query` tool accepts a `timeoutSeconds` parameter (default 300s, max 3600s), Claude Code will kill the connection after 30 seconds regardless of this setting.

**Implications:**
- Keep queries simple and fast — complex analytical queries that take longer than 30 seconds will fail
- Use `LIMIT` clauses to bound result sets
- Prefer querying materialized views or pre-aggregated tables over raw scans of large tables
- If a query times out, break it into smaller, faster queries rather than increasing `timeoutSeconds`

## What the MCP Server Provides

Once connected, the ClickHouse MCP server provides these tools:

### Organization & Service Management
- **get_organizations** — list all accessible ClickHouse Cloud organizations
- **get_organization_details** — details of a single organization
- **get_services_list** — list all services in an organization
- **get_service_details** — details of a single service

### Database Exploration
- **list_databases** — list all databases in a service
- **list_tables** — list tables in a database (supports `like`/`notLike` filtering)
- **run_select_query** — execute read-only SELECT queries (⚠️ subject to 30s Claude Code timeout)

### ClickPipes
- **list_clickpipes** — list all ClickPipes for a service
- **get_clickpipe** — details of a specific ClickPipe

### Backups
- **list_service_backups** — list all backups for a service
- **get_service_backup_details** — details of a specific backup
- **get_service_backup_configuration** — backup schedule and retention settings

### Billing
- **get_organization_cost** — billing and usage cost data (max 31-day window)

All tools are read-only. See the [ClickHouse MCP docs](https://clickhouse.com/docs/use-cases/AI/MCP/remote_mcp) for details.

## Best Practices Skill

This plugin also includes the `clickhouse-best-practices` skill with 28 rules covering schema design, query optimization, and insert strategy. That skill activates automatically when you work with ClickHouse -- no setup needed.
