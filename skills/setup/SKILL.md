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

## What the MCP Server Provides

Once connected, the ClickHouse MCP server provides:

- **List databases** on your ClickHouse Cloud cluster
- **List tables** in a database
- **Inspect schemas** for table structure
- **Run read-only SELECT queries** against your cluster

All queries are scoped to SELECT operations for security. See the [ClickHouse MCP docs](https://clickhouse.com/docs/use-cases/AI/MCP/remote_mcp) for details.

## Best Practices Skill

This plugin also includes the `clickhouse-best-practices` skill with 28 rules covering schema design, query optimization, and insert strategy. That skill activates automatically when you work with ClickHouse -- no setup needed.
