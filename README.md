# ValuEdge MCP

ValuEdge's remote Model Context Protocol (MCP) server lets compatible AI assistants access ValuEdge stock research and, after you sign in, read-only data from your own ValuEdge account.

- **Endpoint:** `https://valuedge.app/mcp`
- **Transport:** Remote HTTP (Streamable HTTP)
- **Authentication:** Public research tools work without signing in. The ValuEdge sign-in flow is required for private account data.
- **Permissions:** Read-only. The MCP connection does not place trades, move funds, or change your ValuEdge account, holdings, watchlist, or Smart Alerts.
- **API key:** None to copy or configure.
- **Marketplace icon:** [400×400 PNG](assets/valuedge-400.png), resized from the official [ValuEdge brand icon](https://github.com/kkfir13/valuedge-claude-stock-research-plugin/blob/main/assets/logo-icon.jpg).

## Connect from Cline

In the Cline MCP Servers view, add a remote server with:

- Name: `valuedge`
- URL: `https://valuedge.app/mcp`
- Transport: Streamable HTTP

Or use the Cline CLI:

```sh
cline mcp add valuedge https://valuedge.app/mcp --transport http --yes
```

If you prefer editing the Cline MCP settings JSON, add this entry under `mcpServers`:

```json
{
  "valuedge": {
    "type": "streamableHttp",
    "url": "https://valuedge.app/mcp",
    "disabled": false,
    "autoApprove": []
  }
}
```

After connecting, use ValuEdge's sign-in prompt when Cline requests private account data. You can ask for public stock research without signing in. Access to private ValuEdge information is tied to the ValuEdge account that completes authentication. Disconnect ValuEdge from the MCP settings of your AI client to end that connection.

## What it provides

ValuEdge MCP exposes read-only research tools, including public stock search, valuations, fundamentals, comparisons, and screening. With authentication, it can also read data available to your signed-in account, including portfolio, watchlist, and Smart Alerts information.

ValuEdge provides investment research and analytics, not personalized investment advice. Estimates and other outputs are research information, not a recommendation to buy, sell, or hold a security. Review results and make your own decisions.

## Privacy

When you use a third-party AI client, information returned from ValuEdge is transmitted to that AI provider and may be processed under its own terms and privacy practices. Review the ValuEdge and AI provider privacy information before connecting private account data.

## Documentation

- [ValuEdge MCP connection guide](https://valuedge.app/connect)
- [ValuEdge Terms of Service](https://valuedge.app/terms)
- [ValuEdge Privacy Policy](https://valuedge.app/privacy)
- [Cline MCP documentation](https://github.com/cline/cline/blob/main/docs/mcp/mcp-overview.mdx)

## Test status

Cline CLI 3.0.74 was tested in an isolated configuration: `cline mcp add valuedge https://valuedge.app/mcp --transport http --yes` completed and generated the expected Streamable HTTP configuration. This verified configuration only, not a server connection or tool discovery.

A live connection test from the test environment was blocked by Cloudflare with HTTP 403, error 1010 (`browser_signature_banned`). No MCP tools were called, and OAuth for private data was not tested. Do not treat this as an end-to-end Cline installation test or a passed OAuth test. Cloudflare's response said not to retry from that environment.

## License

No license is specified in this repository.
