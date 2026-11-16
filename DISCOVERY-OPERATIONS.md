# ValuEdge MCP — Search Discovery & Measurement Operations

**Updated:** 2026-11-16. This file records copy/measurement decisions; it is **not** a search-engine indexing guarantee, a replacement for live registry publication, or evidence that GitHub About fields have been applied.

## Search intent ownership

| Surface | Primary search intent | Canonical next step |
| --- | --- | --- |
| [ValuEdge main MCP](README.md) | stock valuation MCP; stock screener MCP; portfolio tracker MCP; Claude/AI stock research | ValuEdge Connect / Claude directory |
| [Focused Stock Analysis](https://github.com/kkfir13/stock-analysis) | stock analysis for Claude; intrinsic value; fundamentals; daily RSI | Focused plugin / connection guide |
| [Claude research plugin](https://github.com/kkfir13/valuedge-claude-stock-research-plugin) | Claude stock screener; ValuEdge plugin; portfolio analysis | Existing Claude connector / plugin when approved |
| [Stock research skill](https://github.com/kkfir13/valuedge-stock-research-skill) | equity research skill; company fundamentals; evidence-first valuation research | Install skill; optionally connect ValuEdge |

Descriptions and topics are especially important for default GitHub repository search, which does not search README content without `in:readme`. Do not stuff synonyms, invent free/live capabilities, or claim any ranking guarantee.

## Proposed GitHub About fields (manual repo-settings change required)

The GitHub connector used to update README files does **not** provide a repository-description or Topics write method. The entries below are **proposals**, not confirmed live metadata.

| Repository | Suggested About description |
| --- | --- |
| `valuedge-mcp` | ValuEdge remote MCP for stock valuation, intrinsic value, stock screening, Claude AI research and portfolio analysis. |
| `stock-analysis` | Claude stock analysis MCP plugin: intrinsic value, fundamentals, daily technical analysis and stock comparisons by ValuEdge. |
| `valuedge-claude-stock-research-plugin` | Claude plugin for ValuEdge stock screener, DCF valuation, fundamentals, watchlists and authorized portfolio research. |
| `valuedge-stock-research-skill` | Evidence-first AI stock research skill for Claude, Codex and other agents: fundamentals, cash flow and valuation. |

Suggested GitHub Topics (all lower-case, hyphenated and capability-matched):
- `valuedge-mcp`: `mcp`, `model-context-protocol`, `stock-valuation`, `stock-screener`, `intrinsic-value`, `portfolio-tracker`, `financial-analysis`, `claude`, `ai-agents`
- `stock-analysis`: `claude-plugin`, `mcp`, `stock-analysis`, `fundamental-analysis`, `intrinsic-value`, `technical-analysis`, `stock-valuation`
- `valuedge-claude-stock-research-plugin`: `claude`, `claude-plugin`, `mcp`, `stock-screener`, `stock-analysis`, `portfolio-analysis`, `valuation`
- `valuedge-stock-research-skill`: `agent-skills`, `stock-research`, `equity-research`, `fundamental-analysis`, `valuation`, `value-investing`

Use **GitHub repository → About → Edit** to publish these fields. GitHub indexes its own description/topics separately from README. Do not change repository URLs unnecessarily.

## Official MCP Registry

- Published namespace (historically observed): `io.github.kkfir13/valuedge`.
- Canonical hosted endpoint: `https://valuedge.app/mcp`.
- Repository metadata declaration: [server.json](server.json).
- Publication workflow: [.github/workflows/publish-mcp-registry.yml](.github/workflows/publish-mcp-registry.yml).
- The official `mcp-publisher` command, not a README or GitHub PR by itself, updates a registry listing. The GitHub Action attempts schema validation, GitHub OIDC login and `publish` on qualifying changes.
- **Verify the Action's result and the live official registry listing** before asserting that version 1.1.0 or the source-repository link has been published. A third-party cached directory can still display old metadata.
- Glama and other directories may crawl asynchronously or require a separate claim/review; a successful official registry publish does not prove those external listings changed.

## Measurement: baseline and definitions

**Change date:** 2026-11-16. **Primary acquisition goal:** successful ValuEdge MCP research sessions and qualified account conversions, not GitHub impressions alone.

### Observed pre-change baseline

- Connected GA4 **Valuedge property 538556310**, 2026-10-17 through 2026-11-15: no GA4 `sessionSource` row containing `github` was returned in the 102 source/medium/campaign rows queried. **This does not prove that zero users visited via GitHub:** referral stripping, redirects, blockers and attribution classification can hide visits.
- Same GA4 period: `claude.ai / ai-assistant` had **422 sessions / 387 users**; `chatgpt.com / ai-assistant` had **96 sessions / 40 users**. These are source-classification figures for the overall ValuEdge site, **not** installs attributed to these repositories.
- Connected Search Console domain property `sc-domain:valuedge.app` (2026-08-01 through 2026-11-12): query `intrinsic value screener` **58 impressions / 14 clicks**; `intrinsic value stock screener` **29 impressions / 3 clicks**. These belong to the website domain, **not the GitHub README**.
- No verified Google keyword-volume / difficulty numbers were available at change time; do not invent them.

### Tagged links placed in READMEs

`utm_source=github&utm_medium=readme&utm_campaign=mcp_discovery&utm_content=<repo-or-placement>`

Every GitHub README uses its own `utm_content` value on `valuedge.app/connect` links where applicable. Track `sessionCampaignName=mcp_discovery` and `sessionSource=github` in GA4. Referral tracking does not establish that an MCP tool executed, that OAuth succeeded, or that a paid subscription resulted.

### 7-day / 28-day review checklist

1. Record **GitHub views/unique visitors** if available to the repository administrator (GitHub Traffic's retention is limited); separate this from outbound sessions.
2. Read **GA4** sessions/users by `sessionCampaignName=mcp_discovery`, `sessionSource` and `utm_content` where supported; compare equal durations with preceding periods.
3. Use **Google Search Console** for ValuEdge website queries mentioning MCP, Claude, stock valuation, intrinsic value and stock screener. It does not report GitHub's separate search performance.
4. Read **Claude / directory** listing impressions, clicks, installs or connected accounts only if directly surfaced and scoped to the correct connector vs plugin.
5. Join to actual OAuth completions, first useful successful MCP tool response, returning users and paid upgrades **only using authorized first-party evidence**. Never equate raw HTTP 200 or tool-request count with user success.
6. Compare with pre-change baselines; distinguish attribution quality, indexing lag, copy updates and independent product changes. No SEO uplift can be claimed before measurable evidence exists.

## Editorial guardrails

Use source dates, truthful quota limitations and the actual tool list. Not supported as MCP claims: brokerage trading, live intraday indicators, unlimited market coverage, guaranteed returns, all-accounts access, and website-only backtesting features. Updating these README files has **not** changed the hosted API, OAuth scopes, plan quotas, or valuation calculations.
