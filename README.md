# CorpusIQ MCP manifest

Published manifest of record for the CorpusIQ MCP server, `io.corpusiq/multi-source-mcp`.

This repository holds metadata only. The server source code is not public.

- MCP endpoint: https://mcp2.corpusiq.io/mcp (Streamable HTTP, OAuth 2.1 with dynamic client registration)
- Website: https://www.corpusiq.io
- Documentation: https://docs.corpusiq.io
- Registry record: https://registry.modelcontextprotocol.io/v0.1/servers?search=corpusiq

`server.json` follows the MCP registry schema 2025-12-11. Registry versions are immutable, so each
published version carries its own revision of this file.

Current version: 1.0.3

## Connect

CorpusIQ is a remote MCP server. There is no package to install and no local process to run. Any
client that supports Streamable HTTP can connect.

Generic client configuration:

```json
{
  "mcpServers": {
    "corpusiq": {
      "url": "https://mcp2.corpusiq.io/mcp"
    }
  }
}
```

Claude Code:

```
claude mcp add --transport http corpusiq https://mcp2.corpusiq.io/mcp
```

The first connection opens a sign-in. Authorization is discovered from
`https://mcp2.corpusiq.io/.well-known/oauth-protected-resource`, and client registration is automatic,
so no client ID or secret is needed.

Tools are read-only. CorpusIQ retrieves from the systems the user has connected and returns answers
with source citations. Customer data is not stored.

Hosted assistants such as ChatGPT, Claude and Perplexity accept the same endpoint URL as a custom
connector.

## Verify the live record

```
curl "https://registry.modelcontextprotocol.io/v0.1/servers?search=corpusiq"
```

The `isLatest` version should match `version` in `server.json`, and its `repository.url` should point
back at this repository.
