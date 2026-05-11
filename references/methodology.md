# SEO/GEO Methodology

## Goal

Improve qualified discovery and conversion from classic search, AI-assisted search, and answer engines. The objective is not "more SEO tasks"; it is more correct mentions, better cited answers, and more qualified leads or signups.

## Search Surfaces

- Classic search: Google, Yandex, Bing.
- AI search and answer engines: Google AI Overviews/AI Mode, ChatGPT Search, Claude Search, Perplexity, Bing Copilot/Grok/Gemini where relevant.
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
| GEO/AI readiness | 20 | crawler policy, llms.txt, quotable passages, evidence, off-site entity footprint |
| Search conversion fit | 15 | intent/page match, CTA clarity, trust, analytics goals, funnel measurement |

## GEO Principles

- Retrieval comes before generation: if the page is blocked, not indexed, not linked, or invisible in HTML, it is unlikely to be cited.
- Citation and answer absorption are different. Track both: "was cited" and "did the answer use our facts/language".
- Content should be extractable: direct answer in the first 40-80 words, clear H2/H3 sections, tables, bullet lists, definitions, dates, prices, comparison points, and procedural steps.
- Strong GEO content includes evidence: primary sources, credible citations, original data, named case studies, and first-hand experience.
- Avoid keyword stuffing. Research shows citations, quotations, statistics, fluency/readability, and structure are more defensible than raw keyword repetition.
- Platform overlap is low. Do not assume visibility in Google AI Overviews means visibility in ChatGPT or Perplexity.

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

Record date, platform, answer summary, cited sources, whether target URL appears, factual errors, competitors.

## Off-Site GEO

On-site pages are not enough. Build corroborating sources:

- Habr/vc.ru articles with original cases and links.
- YouTube videos and descriptions mentioning the entity and core offers.
- Telegram/VK/Dzen posts that repeat stable facts and link to canonical pages.
- GitHub repos/docs for technical products.
- Partner, university, conference, and podcast pages.
- Wikidata/Wikipedia only when eligibility and notability are real; do not force spam.
