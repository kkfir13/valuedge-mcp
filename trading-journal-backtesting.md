# Trading Journal & Stock Backtesting for Claude | ValuEdge

ValuEdge Trading Journal & Backtesting is a remote MCP connector for reviewing your stock and ETF trade history and testing historical trading strategies. It connects Claude to your ValuEdge trading journal and Research Lab.

| Setting | Value |
| --- | --- |
| Claude connector name | ValuEdge Trading Journal & Backtesting |
| Server URL | `https://valuedge.app/mcp/trading` |
| Transport | Streamable HTTP |
| Authentication | ValuEdge OAuth through the registered Claude client |
| Eligible data | Your ValuEdge portfolio records and supported daily US stock and ETF price history |
| Support | [Contact ValuEdge](https://valuedge.app/contact) |

## Connect ValuEdge to Claude

1. In Claude, open **Customize → Connectors** and find **ValuEdge Trading Journal & Backtesting** when the directory listing is available to you.
2. Choose **Connect**, sign in to the ValuEdge account you want to use, and review the permissions on the ValuEdge consent screen.
3. Enable the connector in a conversation and try one of the prompts below. Select a portfolio if you have more than one.

A ValuEdge account and consent are required for private tools. Public security lookup can work before sign-in. A manual setup uses the same server URL and the Claude OAuth client registered by ValuEdge. [Contact ValuEdge](https://valuedge.app/contact) for access to the registered connection if the directory listing is unavailable.

## Trading journal and trade history

Review matched sales and FIFO realized profit and loss for stock and ETF trades recorded in your portfolio. Results can include trading performance by ticker and month, holding duration, and closed trades. Review fee and matching coverage with the figures and keep currencies separate. Missing cost basis or ambiguous records can exclude trades from the matched results.

- **Trading performance:** “Analyze my ValuEdge trading journal for the past 90 days. Show realized P&L by currency, the five most recent matched sales, and any missing fee or cost-basis data.”
- **Trade review:** “Show the latest portfolio transactions in my ValuEdge account. Which sales have matched FIFO cost basis?”

Where permissions allow, the connector can record, correct, or remove manual portfolio records with your confirmation. The records represent past transactions. Broker-synced records and brokerage order execution are outside this workflow.

## Stock and ETF strategy backtesting

Use daily price history to preview a supported long-only strategy in Research Lab. Check the executed rules, historical coverage, commissions, and slippage before confirming a run. A saved result can show performance versus buying and holding the same security, maximum drawdown, and example trades.

- **Backtest a strategy:** “Preview an AAPL daily RSI strategy for the past year. Enter when RSI crosses above 30 and exit when it crosses above 60. Use 5 basis points of commission and 5 basis points of slippage per side. Show the preview before running.”
- **Research strategy candidates:** “Explore daily long-only strategy candidates for AAPL over three years. Show which candidates passed the checks and summarize the available out-of-sample evidence.”

ValuEdge plan and Research Lab limits apply. Strategy discovery tests a bounded set of historical candidates and can return zero qualifying strategies. Simulated returns are historical and cannot establish future performance.

## Account access and privacy

The connector reads your own authorized ValuEdge records. You can remove the connection in Claude's connector settings. See the [ValuEdge Privacy Policy](https://valuedge.app/privacy) and [Terms of Service](https://valuedge.app/terms) for details.
