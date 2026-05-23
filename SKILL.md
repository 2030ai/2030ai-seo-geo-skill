---
name: 2030ai-seo-geo-skill
description: "Operator skill for SEO, GEO/AI search visibility, and search-driven conversion work. Use for SEO/GEO audits, technical search visibility, AI Overviews/ChatGPT/Claude/Perplexity readiness, Yandex/Google visibility, robots/sitemap/llms.txt/schema checks, content citability, Russian-market SEO specifics, creating prioritized implementation backlogs, applying fixes in a local repo, verifying results, and tracking progress over time."
user-invokable: true
argument-hint: "[audit|plan|execute|verify|track|monitor] [url-or-project]"
metadata:
  owner: "2030AI"
  version: "0.1.3"
  category: "seo-geo"
---

# SEO/GEO Operator

This skill is an execution workflow, not a report generator. Use it to improve search visibility for Google/Yandex and AI-answer surfaces, then verify and track the change.

## Commands

- `audit <url-or-project>`: inspect a site or local repo and produce a prioritized backlog.
- `plan <url-or-project>`: turn audit findings into a staged implementation plan.
- `execute <url-or-project>`: implement approved or obvious fixes in the local repo.
- `verify <url-or-project>`: rerun checks and compare against baseline.
- `track <url-or-project>`: update project `todo.md` / `agent_docs/` with status and next actions.
- `monitor`: refresh this skill's references from monitored sources and update project todo files when methodology changes.

If the user asks for "full SEO", "GEO", "AI search", "AI Overviews", "Yandex SEO", "site visibility", or "search audit" without a command, default to `audit`. If a local repository is open and the user asks to fix or improve, do `audit -> plan -> execute -> verify -> track` in one turn when feasible.

## Operating Contract

1. Establish scope: target domain, local repo path, market, primary conversions, priority pages, and whether off-site work is allowed.
2. Build a baseline: crawl/indexability, robots, sitemap, metadata, canonical, hreflang if relevant, schema, headings, internal links, images, performance, analytics, content quality, GEO/AI readiness, and conversion path.
3. Use evidence tiers. Prefer official docs and first-party tool output over vendor claims or anecdotal SEO posts.
4. Produce an action backlog with `priority`, `impact`, `confidence`, `effort`, `owner`, `verification`.
5. Implement local code/content fixes when the user asked for execution and repo context is available.
6. Verify with project-native commands plus HTTP/browser checks. Do not claim completion without verification or a stated blocker.
7. Track progress in the target project's `todo.md` or search-visibility docs.

## Evidence Tiers

- **Tier 1:** official documentation from Google Search Central, Yandex Webmaster/Metrica, Yandex AI/Search with Alice docs, Schema.org, OpenAI, Anthropic, Perplexity, Bing, W3C/IETF/web.dev.
- **Tier 2:** peer-reviewed or preprint research with citation details and date.
- **Tier 3:** industry studies from Ahrefs, Semrush, SparkToro, Cloudflare, Similarweb, DataForSEO, etc. Include date, sample, and uncertainty.
- **Tier 4:** GitHub repos, tools, blog posts, Reddit/forum observations. Use as leads to test, not as truth.

When a claim can change over time, browse or inspect the current source before using it.

## Core References

Read only the files needed for the task:

- `references/methodology.md`: SEO/GEO framework, scoring, backlog shape.
- `references/sources.md`: canonical source list and current reference URLs.
- `references/russia.md`: Yandex, Russian search/market, legal and conversion specifics.
- `references/execution.md`: concrete audit, implementation, verification, and tracking workflow.
- `references/monitored-repos.md`: old skill and GitHub repositories to watch for changes.

## Non-Negotiables

- Do not optimize for AI search by adding unverifiable claims, fake reviews, invented statistics, fake client logos, or hidden FAQ/schema content.
- Do not recommend deprecated or restricted schema for Google benefit. FAQ content may be useful visibly, but FAQ rich results are restricted/deprecated; state that nuance.
- Keep schema aligned with visible content.
- Keep Russian projects usable for Russian users: payment in rubles, no VPN where true, Telegram/VK/Yandex surfaces, 152-FZ/privacy language, and Yandex Metrica/Webmaster checks.
- Treat `llms.txt` as a useful emerging convention, not an official ranking requirement.
- Separate search/referral crawlers from training crawlers in robots decisions.
- For Google AI Overviews and AI Mode, do not invent special markup or AI-only files. Eligibility still depends on Google Search eligibility and snippets; methodology should focus on crawlable useful content, visible structured facts, source clarity, and measurement.
- For Google AI Mode query fan-out, Search agents, generative UI, and agentic commerce/local booking, audit whether important facts, comparisons, tools, product/service availability, and action paths are visible to users and backed by canonical pages or first-party feeds.
- For Perplexity, audit `PerplexityBot` and `Perplexity-User` separately: one is search/linking crawler policy, the other is user-triggered fetch access. If a WAF/CDN is present, verify current official IP JSON allowlists alongside user-agent rules.
- For Yandex AI/Search with Alice, audit `YandexAdditionalBot` / `YandexAdditional` rules separately from primary Yandex indexing: they affect generated-answer use of already indexed pages, not ordinary indexing itself.

## Output Shape

For audits and plans, return:

```markdown
## Executive Summary
Score: SEO XX/100, GEO XX/100, Conversion Search Fit XX/100

## Critical Findings
| Priority | Issue | Evidence | Fix | Verify |

## Backlog
| Priority | Page/Area | Action | Impact | Confidence | Effort | Owner | Verification |

## Implemented
...

## Verification
...

## Tracking
...
```

For implementation tasks, keep the final response concise and reference changed files.
