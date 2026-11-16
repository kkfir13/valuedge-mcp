# ValuEdge MCP — Stock Valuation, Stock Screener & Portfolio Analysis for AI Agents

Connect **ValuEdge** to Claude and other compatible AI assistants through the remote **Model Context Protocol (MCP)**. Research stocks using **intrinsic value estimates, fundamental analysis, valuation comparisons, and a bounded stock screener**. With your own ValuEdge authorization, review portfolio holdings, watchlists, Smart Alerts, and dividend information.

**Start here:** [Connect ValuEdge to an AI assistant](https://valuedge.app/connect?utm_source=github&utm_medium=readme&utm_campaign=mcp_discovery&utm_content=valuedge-mcp) · [ValuEdge in Claude Directory](https://claude.ai/directory/valuedge) · [Stock Analysis focused plugin](https://github.com/kkfir13/stock-analysis) · [Official MCP Registry](https://registry.modelcontextprotocol.io/?q=io.github.kkfir13%2Fvaluedge) · [Glama MCP connector](https://glama.ai/mcp/connectors/app.valuedge/valu-edge)

> **Research, not brokerage trading.** Valuation outputs are model estimates, not price guarantees or buy/sell recommendations. Some account-management tools can change your own ValuEdge watchlist or manual portfolio records **only with the appropriate OAuth authorization and explicit user request/confirmation**. They do **not** place orders, move funds, or edit broker-synced transactions. Exact access depends on the client, tool, and ValuEdge plan.

## What can I ask ValuEdge MCP?

| Search intent / task | Example prompt | Relevant MCP capabilities |
| --- | --- | --- |
| Stock valuation and intrinsic value | "Analyze AAPL's fair value, margin of safety, and valuation assumptions. Show source dates." | `get_stock_valuation` |
| Fundamental stock analysis | "Review MSFT's profitability, cash-flow quality, and balance-sheet evidence." | `get_stock_fundamentals` |
| Stock screener for undervalued companies | "Screen supported US stocks with a positive margin of safety and explain the filters." | `screen_stocks` |
| Compare stocks | "Compare GOOGL and MSFT on valuation, then check their fundamentals." | `compare_stocks`, `get_stock_fundamentals` |
| Daily technical analysis | "Show NVDA's latest available daily RSI and moving averages, with the observation date." | `get_stock_technicals` |
| Portfolio tracker and diversification | "Analyze my portfolio's concentration and fair-value coverage." | `get_my_portfolio`, `analyze_my_portfolio` |
| Watchlist and stock alerts | "Show my watchlist and existing Smart Alerts." | `get_my_watchlist`, `get_my_smart_alerts` |
| Dividend tracker and calendar | "Show upcoming known dividend dates and my tracked dividend information." | `get_dividend_calendar`, `get_my_dividend_tracker` |

Tool availability varies by connected client, OAuth scope, plan allowance, data coverage, and server version. **Screener results are a bounded candidate set, not an exhaustive market scan.** Technical indicators describe daily/end-of-day data rather than live intraday signals. Do not infer missing values.

## How to connect ValuEdge MCP

- **Claude:** [Open the ValuEdge connector in Claude Directory](https://claude.ai/directory/valuedge), select the available connection flow, and authorize when prompted for account-scoped tools.
- **ChatGPT:** Find the available **ValuEdge** app in ChatGPT's app/plugin directory and use its connect flow. Availability and setup depend on your ChatGPT client; ChatGPT app installation is **not** the same process as manually adding an MCP URL.
- **Other compatible MCP clients:** If your client accepts remote Streamable HTTP servers, use the endpoint and its supported authentication flow below. [Full connection guide](https://valuedge.app/connect?utm_source=github&utm_medium=readme&utm_campaign=mcp_discovery&utm_content=valuedge-mcp-install).

| Setting | Value |
| --- | --- |
| Server endpoint | `https://valuedge.app/mcp` |
| Transport | Remote Streamable HTTP |
| API key | No key to copy or paste |
| Authentication | Public ticker discovery can be available without login; private and metered operations require ValuEdge OAuth |
| Costs and permissions | Existing ValuEdge plan allowances and user-granted scopes apply |

### Cline (manual remote MCP setup)

In **MCP Servers**, add `valuedge` with URL `https://valuedge.app/mcp` and Streamable HTTP transport, or use the tested Cline CLI configuration command:

```sh
cline mcp add valuedge https://valuedge.app/mcp --transport http --yes
```

For Cline configurations that accept an `mcpServers` object:

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

The Cline command above was checked with CLI 3.0.74 **for configuration generation only**. That check did not establish a successful end-to-end connection or complete an OAuth flow. Client configuration formats can change; follow your client version's documentation.

## MCP permissions and data accuracy

**Research / read:** Supported company lookup, intrinsic-value models, fundamentals, fair-value comparisons, bounded stock screens, and account-scoped portfolio, watchlist, alert, and dividend reads.

**Optional account record changes:** Where exposed by the connected client and permitted by the user, ValuEdge MCP can add/remove supported watchlist symbols, manage eligible watchlist folders, or create/edit/remove **manual** portfolio transaction records. The client must request appropriate permission and a confirmed user intention. Brokerage-synced and imported transaction data are not edited by these tools.

**Not supported:** Brokerage order execution, transfers of funds, automatic trading, guaranteed returns, exhaustive global screening, or a live intraday market feed. A feature available in the ValuEdge website is **not automatically** an MCP capability.

**Freshness and errors:** Quote data-as-of dates where supplied. If the server returns unavailable data, plan limits, or an authorization error, explain that status; do not replace it with fabricated valuations, zero values, or a generic stock recommendation.

## Frequently asked questions

### Can Claude analyze stocks or estimate intrinsic value through MCP?
Yes. Use ValuEdge's compatible Claude connection to request supported fair-value estimates, model assumptions, fundamentals, and comparisons. Estimates are model-dependent and access may require ValuEdge sign-in.

### Can I use a stock screener from an AI assistant?
Yes, when the `screen_stocks` tool is available to your authenticated connection and plan. It screens a bounded supported US-listed candidate set; it does not represent every available stock.

### Do I need a brokerage account or API key?
A brokerage link is not required to research public companies. No API key needs to be copied. ValuEdge OAuth is needed for private account data and other metered tools.

### Can the MCP modify my holdings or trade stocks?
It cannot trade through a brokerage. Some separately permissioned tools may edit **manual records inside your ValuEdge account** or change your watchlist, after an explicit request and the necessary authorization.

### Is the stock data real time?
Technical analysis is based on available daily/end-of-day observations, not live intraday quotes. Financial and valuation coverage varies by company and data date.

### How do I disconnect or revoke access?
Disconnect the app or MCP server in your AI client's connection settings; review your ValuEdge account's connection/authorization settings when available. Private data returned to third-party AI clients may be processed under those clients' privacy policies.

## Privacy, support, and documentation

- [ValuEdge connection and authorization guide](https://valuedge.app/connect)
- [ValuEdge Privacy Policy](https://valuedge.app/privacy)
- [Terms of Service](https://valuedge.app/terms)
- [Contact support](https://valuedge.app/contact)
- [Cline MCP overview](https://github.com/cline/cline/blob/main/docs/mcp/mcp-overview.mdx)
- [Claude-focused Stock Analysis plugin](https://github.com/kkfir13/stock-analysis)
- [Claude research, screener and portfolio plugin](https://github.com/kkfir13/valuedge-claude-stock-research-plugin)

This repository is **documentation for a hosted ValuEdge server**, not a copy of its backend. User information passed between the AI client and ValuEdge is subject to their respective privacy practices. The MCP connection is not investment advice.

## Connection test status (historical)

An isolated Cline CLI 3.0.74 run verified that the configuration command generated the expected Streamable HTTP settings. A separate live test from that environment was **blocked by Cloudflare HTTP 403 / error 1010 (`browser_signature_banned`)**; no MCP tool calls or private OAuth tests were completed in that attempt. This historical result is **not proof that all clients fail** and is **not an end-to-end pass**. Do not retry from an environment Cloudflare has explicitly blocked without resolving access with the operator.

## License

No license is specified in this repository. Do not assume the ValuEdge hosted backend or datasets are open source.
