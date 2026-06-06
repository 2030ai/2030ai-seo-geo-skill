# SEO/GEO Methodology

## Goal

Improve qualified discovery and conversion from classic search, AI-assisted search, and answer engines. The objective is not "more SEO tasks"; it is more correct mentions, better cited answers, and more qualified leads or signups.

## Search Surfaces

- Classic search: Google, Yandex, Bing.
- AI search and answer engines: Google AI Overviews/AI Mode, Search agents and generative UI surfaces when relevant, ChatGPT Search, Claude Search, Perplexity, Bing Copilot, Grok, Gemini where relevant.
- Entity surfaces: YouTube, Telegram, VK, Habr, vc.ru, Dzen, GitHub, review sites, directories, university/corporate pages, partner pages.
- Local or regional surfaces: Yandex Business/Maps, 2GIS, Google Business Profile if applicable.

## Scoring

Use scores only as triage, not as pseudo-science.

| Area | Weight | Checks |
| --- | ---: | --- |
| Crawl/index | 20 | robots, sitemap, canonical, status codes, noindex, redirects, JS dependency |
| Content/entity | 20 | answer-first copy, topical coverage, E-E-A-T, author/org clarity, citations |
| Technical UX | 15 | Core Web Vitals, mobile, accessibility, navigation, image performance |
| Structured data | 10 | schema validity, visible-content alignment, sameAs/entity graph |
| GEO/AI readiness | 20 | crawler policy, Yandex AI/Alice controls when relevant, llms.txt, quotable passages, evidence, off-site entity footprint |
| Search conversion fit | 15 | intent/page match, CTA clarity, trust, analytics goals, funnel measurement |

## GEO Principles

- Retrieval comes before generation: if the page is blocked, not indexed, not linked, or invisible in HTML, it is unlikely to be cited.
- Citation and answer absorption are different. Track both: "was cited" and "did the answer use our facts/language".
- Content should be extractable: direct answer in the first 40-80 words, clear H2/H3 sections, tables, bullet lists, definitions, dates, prices, comparison points, and procedural steps.
- Strong GEO content includes evidence: primary sources, credible citations, original data, named case studies, and first-hand experience.
- Avoid keyword stuffing. Research shows citations, quotations, statistics, fluency/readability, and structure are more defensible than raw keyword repetition.
- Platform overlap is low. Do not assume visibility in Google AI Overviews means visibility in ChatGPT or Perplexity.
- For Google AI Overviews and AI Mode, there is no special AI-only schema, markup, or machine-readable file requirement. A page must be eligible for Google Search and snippets; keep fundamentals strong before adding experimental GEO artifacts.
- Google AI Mode can use query fan-out across subtopics and data sources. Audit whether priority pages cover the actual comparison, planning, troubleshooting, local, and commercial sub-questions users ask, and whether internal links expose those subtopics clearly.
- Search agents and generative UI shift some journeys from "find a page" to "complete a task." For calculators, product/service selection, bookings, local availability, and commerce, make visible facts, constraints, prices, availability, provider links, policies, and next actions explicit on canonical pages and first-party feeds.
- Generative UI/mini-app answers still need source material. Prefer useful public tools, tables, examples, datasets, and explainers that can be cited or transformed, not hidden schema or content written only for bots.
- Measure Google AI-surface visibility with the Search Console Generative AI performance report (Search + Discover impressions in AI Overviews, AI Mode, and Discover AI; breakdown by page, country, device, and date). Know its limits: impressions only with no clicks, data starts 2026-05-18, and rollout is staged (first available in UK from 2026-06-03 under the UK CMA / DMCCA 2024 mandate) — verify availability for the target market before relying on it. Pair it with Search Console Web performance plus analytics/conversion quality, because AI-feature clicks are still not separated into a dedicated Search Console search type.
- The Generative AI report has a companion opt-out toggle that removes the site from AI Overviews, AI Mode, and Discover AI without affecting ordinary Search or the regular Discover feed. It is a control/privacy lever, not a ranking signal, and does not block Gemini. Do not recommend it as an SEO tactic; only consider it when the user has a deliberate reason to suppress AI-feature presence, and note the toggle takes effect on a delay (2026-06-17 for the initial UK rollout).
- Perplexity has separate crawler surfaces: `PerplexityBot` for surfacing and linking sites in Perplexity search results, and `Perplexity-User` for user-triggered page fetches. Audit both when Perplexity visibility matters.
- Generated-answer crawlers can be distinct from search indexing crawlers. For Yandex, audit `YandexAdditionalBot` / `YandexAdditional` rules separately because they affect AI/Alice answer use of indexed pages.

## Negative Signals To Check

Negative signals do not automatically mean "bad"; they mean the site has an explicit policy or technical constraint that can suppress AI discovery or answer citation.

- `robots.txt` blocks for AI-answer crawlers such as `YandexAdditionalBot` / `YandexAdditional`, `GPTBot`, `OAI-SearchBot`, `ClaudeBot`, `PerplexityBot`, or `Google-Extended`.
- WAF/CDN rules that block AI-search fetches even when `robots.txt` allows them. For Perplexity, check both `PerplexityBot` and `Perplexity-User` against the current official IP JSON endpoints when a WAF/CDN is present.
- `X-Robots-Tag` response headers with `noindex`, `none`, or bot-specific restrictions on priority pages.
- `<meta name="robots">` or bot-specific meta directives that conflict with the target visibility strategy.
- Emerging AI exclusion directives such as `noai` / `noimageai` when present.
- Excessively high or broad `Crawl-delay` rules that can slow discovery or refresh for important crawlers.
- Stale sitemap timestamps, stale `llms.txt` ordering, or schema missing required basics such as `@context`, `@type`, and canonical `url`.
- Google Search Console AI-features opt-out toggle enabled on the property, which deliberately removes the site from AI Overviews, AI Mode, and Discover AI. Confirm whether this is intentional before treating low AI-feature impressions as an optimization problem.

## Backlog Priority

- `Critical`: blocks indexing/crawling, exposes wrong canonical, breaks conversion tracking, or creates legal/trust risk.
- `High`: likely affects visibility or conversion on priority pages within 1-2 weeks.
- `Medium`: meaningful improvement but not blocking.
- `Low`: useful cleanup or monitoring.

Each item needs a verification method: command, URL check, Search Console/Yandex Webmaster check, Lighthouse/CWV, schema validator, or AI prompt set.

## AI Visibility Prompt Set

For each project keep 20-50 prompts:

- Brand/entity: "Who is <brand/person>?", "What does <product> do?"
- Category: "best <category> in Russia", "AI courses for managers in Russian", etc.
- Problem/solution: "how to automate <task> with AI", "where to learn <skill>".
- Comparison: "<brand> vs alternatives", "ChatGPT alternative in Russia".
- Commercial intent: "course/mentor/platform for <audience>".
- Planning/action: "plan <task>", "book/find/buy <thing> with <constraints>", "best option for <specific situation>".
- Generative UI/tool intent: "build a calculator/checklist/tracker/simulation for <problem>", "compare <options> in a table/dashboard".

Record date, platform, answer summary, cited sources, whether target URL appears, factual errors, competitors.

## Off-Site GEO

On-site pages are not enough. Build corroborating sources:

- Habr/vc.ru articles with original cases and links.
- YouTube videos and descriptions mentioning the entity and core offers.
- Telegram/VK/Dzen posts that repeat stable facts and link to canonical pages.
- GitHub repos/docs for technical products.
- Partner, university, conference, and podcast pages.
- Wikidata/Wikipedia only when eligibility and notability are real; do not force spam.
