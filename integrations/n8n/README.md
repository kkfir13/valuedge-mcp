# ValuEdge Stock Research Chat for n8n

Import `valuedge-stock-research-chat.json` into an n8n instance with the built-in AI Agent, OpenAI Chat Model, Chat Trigger, and MCP Client Tool nodes.

## Setup

1. Import the JSON workflow.
2. Open **OpenAI Chat Model** and select your OpenAI credential. The workflow contains no API key or credential ID.
3. Open **ValuEdge Public Research Tools** and verify the endpoint is `https://valuedge.app/mcp`, transport is **Streamable HTTP**, and authentication is **None**. This template selects only the public research tools listed in the node.
4. Save the workflow and test it in the n8n chat interface with a question such as “Compare AAPL and MSFT on valuation and fundamentals.”
5. The chat trigger is private by default. If you want to publish it as a public chat, review the trigger's authentication and n8n's usage controls first; unauthenticated public access can consume your model/API quota.

## What it does

The workflow gives an AI Agent access to ValuEdge's public stock valuation, fundamentals, and comparison tools. It does not connect to private portfolios, watchlists, alerts, or account-changing tools. No ValuEdge OAuth setup is needed for this public-research-only template.

ValuEdge data coverage and dates vary by symbol and tool. Valuation results are model estimates, not guarantees or investment recommendations. Screener results are bounded rather than exhaustive.

## Compatibility

Uses n8n's built-in MCP Client Tool with Streamable HTTP transport. No community nodes are used. Set up the OpenAI credential in your own n8n instance after import.
