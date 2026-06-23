# Execution Workflow

## Audit

1. Identify target:
   - Domain and canonical origin.
   - Local repo path and framework.
   - Primary market: Russia, global, or mixed.
   - Priority conversions and pages.
2. Collect URLs:
   - `sitemap.xml`, `robots.txt`, `llms.txt`, navigation links.
   - Priority commercial pages, articles, docs, legal pages.
3. Crawl and inspect:
   - HTTP status, redirects, canonical, title/meta, H1 count, headings, links, images/alt, noindex, robots.
   - Rendered vs source HTML for important content.
   - Schema JSON-LD and visible-content alignment.
   - Performance: PageSpeed Insights for priority pages/templates on mobile and desktop when network/API access allows; include Lighthouse `performance`, `accessibility`, `best-practices`, and `seo` categories.
   - PSI evidence: record tested URL, final URL, strategy, locale, categories, timestamp, Lighthouse/PageSpeed version, category scores, Core Web Vitals status, top failed audits, and whether field data came from page-level or origin fallback.
   - CrUX: use PSI `loadingExperience` / `originLoadingExperience` only when present; for recurring field monitoring or missing PSI field data, prefer CrUX API/History API.
   - Analytics: Yandex Metrica/GA events when repo or deployed HTML reveals them.
4. GEO checks:
   - AI crawler policy by user-agent category, separating search/linking crawlers, user-triggered fetchers, training crawlers, and regional generated-answer crawlers.
   - External agent-readiness scan when relevant and network access allows:
     `curl -sS -X POST https://isitagentready.com/api/scan -H 'content-type: application/json' --data '{"url":"https://example.com/"}'`.
     Record the score and pass/fail checks, then independently verify actionable findings with direct HTTP/DNS/browser checks.
   - For Perplexity scopes: `PerplexityBot` policy separately from `Perplexity-User` access, plus WAF/CDN allowlist checks against the current official IP JSON endpoints when a WAF/CDN is present.
   - For Russian/Yandex scopes: `YandexBot` indexing policy separately from `YandexAdditionalBot` / `YandexAdditional` generated-answer policy for Yandex AI/Search with Alice.
   - `X-Robots-Tag`, robots meta, bot-specific meta, and emerging `noai` / `noimageai` directives on priority pages.
   - Broad or excessive `Crawl-delay` rules that may slow discovery or freshness.
   - `llms.txt` presence, freshness, coverage, and accuracy.
   - Answer-first paragraphs, quotable passages, evidence, source citations.
   - Entity graph: `sameAs`, author/org/project clarity, off-site references.
   - AI prompt-set baseline if the user asks or current tools allow.

## Implementation

Safe automatic fixes:

- Metadata, descriptions, canonical URL bugs.
- Missing or stale sitemap/robots/llms entries.
- Clarifying crawler policy comments when robots rules intentionally separate indexing, AI-answer use, and training crawlers.
- JSON-LD builders when visible content supports them.
- Heading hierarchy and duplicate H1 issues.
- Image alt text when context is clear.
- Internal links between relevant pages.
- Visible FAQ sections only when useful to users.
- Direct-answer ledes for commercial pages.
- Analytics event naming in code when the project already has analytics.
- Conservative discovery metadata that points to real existing resources, such as an RFC 8288 `Link` header for `llms.txt` or sitemap, when it does not misrepresent site capabilities.

Require explicit confirmation or owner fact-check:

- Security/compliance claims.
- Pricing, guarantees, testimonials, client logos, case-study numbers.
- Legal policy text.
- Large IA changes, mass programmatic pages, backlink campaigns.
- Creating new external publications under a person's name.
- DNS changes, DNSSEC, Web Bot Auth, OAuth/OIDC, MCP/A2A, WebMCP, API catalogs, or commerce protocols unless the project already has the corresponding public surface and owner-approved operating model.

## Verification

Use project-native checks first:

- Typecheck/lint/build.
- Local production server smoke if applicable.
- `curl -I` and content checks for deployed/static outputs.
- Browser screenshot/Playwright for important UX changes.
- Lighthouse or PageSpeed Insights where feasible, rerun mobile and desktop for pages touched by performance fixes and compare against the saved baseline.
- Schema validator or JSON-LD parse checks.
- Sitemap/robots/llms fetch checks.
- Header and meta checks for `X-Robots-Tag`, `noindex`, `noai`, `noimageai`, and bot-specific directives.
- External scorecard recheck when one was part of the audit, plus direct verification of each accepted finding. For `isitagentready.com`, store or summarize the JSON result and avoid claiming that a higher score equals better SEO/GEO.
- WAF/CDN checks for AI-search crawlers when the project uses a security proxy. For Perplexity, compare allow rules and logs with the current official `PerplexityBot` and `Perplexity-User` IP JSON endpoints.
- Yandex-specific robots checks for `Yandex`, `YandexBot`, `YandexAdditionalBot`, and `YandexAdditional` where the market is Russia/CIS.

For AI visibility, record platform/date and do not overclaim. AI answers are dynamic.

## Tracking

Preferred project artifacts:

- `todo.md` in project root for active follow-ups.
- `agent_docs/search-visibility.md` for baseline and recurring audit history when the project has `agent_docs/`.
- `agent_docs/development-history.md` or equivalent only when the project convention requires it.

Each tracking entry should include:

- Date.
- Skill version.
- Scope/pages.
- Completed fixes.
- Remaining backlog.
- Verification commands/results.
- Next review date.

## Final Answer

Keep final output short:

- What changed.
- What was verified.
- What remains.
- Links to changed files.
