# ClickHouse Best Practices

Agent skill providing comprehensive ClickHouse guidance for schema design, query optimization, and data ingestion.

## Installation

This skill is included as part of the [ClickHouse Claude Code plugin](https://github.com/ClickHouse/clickhouse-claude-code-plugin). Install the plugin to get this skill automatically (pending marketplace approval):

```bash
claude plugin install clickhouse@claude-plugins-official
```

Or clone the repo and load it directly:

```bash
git clone --recursive https://github.com/ClickHouse/clickhouse-claude-code-plugin
claude --plugin-dir ./clickhouse-claude-code-plugin
```

## What's Included

**28 atomic rules** organized by prefix:

| Prefix | Count | Coverage |
|--------|-------|----------|
| `schema-pk-*` | 4 | PRIMARY KEY selection, cardinality ordering |
| `schema-types-*` | 5 | Data types, LowCardinality, Nullable |
| `schema-partition-*` | 4 | Partitioning strategy, lifecycle management |
| `schema-json-*` | 1 | JSON type usage |
| `query-join-*` | 5 | JOIN algorithms, filtering, alternatives |
| `query-index-*` | 1 | Data skipping indices |
| `query-mv-*` | 2 | Incremental and refreshable MVs |
| `insert-batch-*` | 1 | Batch sizing (10K-100K rows) |
| `insert-async-*` | 2 | Async inserts, data formats |
| `insert-mutation-*` | 2 | Mutation avoidance |
| `insert-optimize-*` | 1 | OPTIMIZE FINAL avoidance |

## Trigger Phrases

This skill activates when you:
- "Create a table for..."
- "Optimize this query..."
- "Design a schema for..."
- "Why is this query slow?"
- "How should I insert data into..."
- "Should I use UPDATE or..."

## Files

| File | Purpose |
|------|---------|
| `SKILL.md` | Quick reference and decision frameworks |
| `AGENTS.md` | Complete rule reference (auto-generated) |
| `rules/*.md` | Individual rule definitions |

## Related Documentation

All rules link to official ClickHouse documentation:
- [ClickHouse Best Practices](https://clickhouse.com/docs/best-practices)
