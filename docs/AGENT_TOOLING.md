# Agent Tooling — Web Automation Stack

> **Org-wide standard for TAURUS AI Corp repositories.** Pick the right tool by *task shape*, not by habit. Mixing them up wastes tokens and money.

## Three jobs, three tools

| Task shape | Tool | License | Cost | When |
|---|---|---|---|---|
| **Read static HTML** ("markdown of these 50 pages") | `webclaw` (Rust CLI) | AGPL-3.0 | Free local | Static sites, docs, blogs, marketing pages |
| **Read JS-rendered or anti-bot pages** | `firecrawl` | AGPL self-host / hosted SaaS | Free tier + paid | SPAs, dashboards, Cloudflare-gated, has search API |
| **Act on a page** ("login + form + screenshot") | `browser-use` | **MIT** | Free with local LLM / paid with Claude or OpenAI | Clicks, types, navigates, multi-step flows |
| **Deterministic flows with known selectors** | Playwright direct | Apache-2.0 | Free | When you don't need an AI brain |

## Decision tree

```
Does the task involve clicking, typing, navigating, or screenshotting a flow?
├─ YES → browser-use
└─ NO → does the task need to extract content from URLs?
        ├─ YES → is the content client-rendered (React/Vue SPA) or behind anti-bot?
        │       ├─ YES → firecrawl
        │       └─ NO  → webclaw
        └─ NO → is it "search the web for X"?
                ├─ YES → firecrawl (search API)
                └─ NO  → reconsider task framing
```

## Quick install

```bash
# browser-use (Python, MIT)
uv tool install browser-use
browser-use install                    # downloads Chromium

# webclaw (Rust, AGPL)
brew tap 0xMassi/webclaw && brew install webclaw

# firecrawl — typically used via hosted SaaS API or as MCP server
# Self-host: see https://github.com/firecrawl/firecrawl
```

All three are wired as MCP servers in TAURUS development environments, so Claude Code, Cursor, OpenCode, and Antigravity discover them automatically.

## browser-use LLM provider routing

browser-use needs an LLM brain to decide what to click/type. **Default to free; escalate when needed.**

| Provider | Use when | Cost per task |
|---|---|---|
| Local LLM (Ollama) | Internal tools, dev work, privacy-sensitive | $0 |
| Claude Sonnet | Hard sites, multi-step flows, customer demos | ~$0.005-0.05 |
| GPT-4o-mini | Backup if Claude rate-limited | ~$0.001-0.01 |
| Browser Use Cloud | When you need their stealth + proxy infra | per-token paid |

**Escalation rule:** try local LLM first; on second failure escalate to Claude; never just retry the local model in a loop.

## License watch — AGPL trip wire

Strict copyleft applies to two tools in this stack. Read this once, save the legal review later.

| Tool | License | What's allowed | What triggers AGPL § 13 |
|---|---|---|---|
| `webclaw` | AGPL-3.0 | Calling as CLI subprocess from any TAURUS product | **Bundling as library inside customer-facing SaaS** → must release entire SaaS source |
| `firecrawl` (self-host) | AGPL-3.0 | CLI/MCP use is fine | Same trip wire if embedded as library |
| `firecrawl` (hosted SaaS via API) | proprietary | Use freely with API key | Not affected |
| `browser-use` | **MIT** | Embed anywhere, including customer-facing products | None |
| Playwright | Apache-2.0 | Embed anywhere | None |

**Default safe pattern:** invoke webclaw / firecrawl as **subprocesses** (`subprocess.run`, `os.exec`, etc.), not as imported libraries. This keeps you on the right side of AGPL § 13.

## Worked examples

| Real task | Right tool | Wrong tool (and why it'd waste tokens) |
|---|---|---|
| "Scrape a competitor's pricing page (React app) for proposal generation" | `firecrawl` | webclaw — would return JS stub |
| "Get markdown of 200 PQC research papers (static PDFs/HTML)" | `webclaw` | firecrawl — slower + costs credits unnecessarily |
| "Log into a customer dashboard and screenshot the metrics page" | `browser-use` | firecrawl — auth flow needs a real browser session |
| "Submit a multi-step compliance form on a regulator portal" | `browser-use` | webclaw — can't fill forms |
| "Search the web for 'EU AI Act enforcement 2026'" | `firecrawl` (search API) | webclaw — no search; browser-use — wrong tool |
| "Run end-to-end form regression tests against a TAURUS product" | `browser-use` | Playwright direct works too if selectors known |

## Common pitfalls

1. **Reaching for browser-use to "scrape a page."** That's slow and expensive. If you're not clicking or typing, use webclaw or firecrawl.
2. **Reaching for firecrawl on every page.** Static blog/docs pages don't need a headless browser. webclaw is 10–50× faster and free.
3. **Using a local LLM on hard sites and retrying in a loop.** Two failures = escalate to Claude. Don't burn 30 retries.
4. **Hardcoding selectors when the page changes weekly.** That's where browser-use beats Playwright direct — the LLM adapts to layout shifts; selector-based scripts shatter.
5. **Bundling AGPL tools as libraries in customer SaaS.** Use them as subprocesses, never as imports. Or use MIT-licensed alternatives (browser-use, Playwright).

## Per-repo adoption

Each TAURUS repository should reference this playbook from its own `CLAUDE.md` or `README.md`. The standard pattern:

```markdown
## Web Automation

See [TAURUS AI Corp Agent Tooling](https://github.com/Taurus-Ai-Corp/.github/blob/main/docs/AGENT_TOOLING.md) for the org-wide routing rules between `browser-use`, `firecrawl`, and `webclaw`.
```

For new repos, an internal scaffold script handles this automatically.

---

**Maintainer:** [admin@taurusai.io](mailto:admin@taurusai.io)
**Last updated:** 2026-05-08
**Source of truth:** this file. Forks should pin a commit and resync periodically.
