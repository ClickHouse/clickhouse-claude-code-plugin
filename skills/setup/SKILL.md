---
name: setup
description: Guides users through setting up the ClickHouse MCP server connection bundled with this plugin. Use when the user first installs the plugin or has trouble connecting to ClickHouse.
disable-model-invocation: true
---

# ClickHouse Plugin Setup

This plugin includes a remote MCP server at `https://mcp.clickhouse.cloud/mcp` that gives you access to ClickHouse documentation, query assistance, and live cluster interaction.

## Setup Steps

1. **Verify the MCP server is connected**: Check that the ClickHouse MCP server appears in your available tools. If it does, you're ready to go.

2. **If the server requires authentication**: The ClickHouse MCP server may prompt for authentication via OAuth or API key. Follow the prompts to authorize access to your ClickHouse Cloud account.

3. **Test the connection**: Try a simple request to the MCP server to confirm it's working, such as asking for ClickHouse documentation or running a test query.

## Troubleshooting

- **Server not appearing**: Run `/reload-plugins` to reload plugin MCP servers.
- **Authentication errors**: Re-authenticate by following the OAuth flow when prompted.
- **Connection timeouts**: Verify your network can reach `https://mcp.clickhouse.cloud`. The MCP server is a remote HTTP endpoint and requires internet access.

## What the MCP Server Provides

Once connected, the ClickHouse MCP server extends Claude with:

- Live ClickHouse documentation lookups
- Query assistance and optimization suggestions
- Direct interaction with ClickHouse Cloud clusters (when authenticated)

## Best Practices Skill

This plugin also includes the `clickhouse-best-practices` skill with 28 rules covering schema design, query optimization, and insert strategy. That skill activates automatically when you work with ClickHouse -- no setup needed.
