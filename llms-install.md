# Install ValuEdge MCP in Cline

ValuEdge is a hosted remote MCP server. Do not clone or build a local server.

## Add the server

In Cline's MCP Servers panel, use Remote Servers and enter:

- Server name: `valuedge`
- Server URL: `https://valuedge.app/mcp`
- Transport: Streamable HTTP

For Cline CLI, run:

```sh
cline mcp add valuedge https://valuedge.app/mcp --transport http --yes
```

The equivalent entry in Cline's `cline_mcp_settings.json` is:

```json
{
  "mcpServers": {
    "valuedge": {
      "type": "streamableHttp",
      "url": "https://valuedge.app/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

Do not add an API key or bearer token. Public stock research can be requested without signing in. When private ValuEdge account information is requested, complete the ValuEdge sign-in flow shown by the client. Authentication is tied to the ValuEdge user who authorizes the connection.

## Scope and privacy

The current ValuEdge MCP connection is read-only. It does not place/cancel trades, transfer funds, change holdings, edit watchlists, modify Smart Alerts, or modify the ValuEdge account.

Data returned by ValuEdge is shared with the connected AI provider and may be processed under that provider's terms and privacy practices.

## Sources and verification status

Endpoint, access model, and permission claims: https://valuedge.app/connect, https://valuedge.app/terms, and https://valuedge.app/privacy. Cline remote HTTP configuration: https://github.com/cline/cline/blob/main/docs/mcp/mcp-overview.mdx.

Cline CLI 3.0.74 accepted the add command and generated the expected Streamable HTTP configuration in an isolated test. The CLI configuration was not followed by successful live connection or tool discovery. A direct initialize request from the test environment was blocked by Cloudflare HTTP 403 error 1010 (`browser_signature_banned`); no tools were called and OAuth was not tested. Cloudflare said not to retry from that environment. Therefore Cline setup has not been verified end to end, and this cannot be marked as a successful Cline installation test for marketplace submission.
