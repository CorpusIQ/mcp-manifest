# CorpusIQ MCP manifest

Published manifest of record for the CorpusIQ MCP server, `io.corpusiq/multi-source-mcp`.

This repository holds metadata only. The server source code is not public.

- MCP endpoint: https://mcp2.corpusiq.io/mcp (Streamable HTTP)
- Website: https://www.corpusiq.io
- Documentation: https://docs.corpusiq.io
- Registry record: https://registry.modelcontextprotocol.io/v0.1/servers?search=corpusiq

`server.json` follows the MCP registry schema 2025-12-11. Registry versions are immutable, so each
published version carries its own revision of this file.

Current version: 1.0.2

## Verify the live record

```
curl "https://registry.modelcontextprotocol.io/v0.1/servers?search=corpusiq"
```

The `isLatest` version should match `version` in `server.json`, and its `repository.url` should point
back at this repository.
