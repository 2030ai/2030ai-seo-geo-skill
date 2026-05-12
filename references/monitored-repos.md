# Monitored Repositories And References

This list is used by a periodic refresh workflow. Treat every external repo as a signal source, not a source of truth.

## Legacy / Local References

- If you maintain a private predecessor skill or local SEO workflow, keep its path in your private automation/orchestration repository, not in this public repo.
- Purpose: mine useful checklists and scripts, but do not inherit marketing footer, overbroad orchestration, or unsupported claims.

## SEO / Audit Skills And Tools

- https://github.com/JustinBeckwith/linkinator
- https://github.com/StanGirard/seo-audits-toolkit
- https://github.com/StJudeWasHere/seonaut
- https://github.com/JeffLi1993/seo-audit-skill
- https://github.com/seo-skills/seo-audit-skill
- https://github.com/huifer/claude-code-seo
- https://github.com/Suganthan-Mohanadasan/tech-seo-audit-skill
- https://github.com/Horosheff/google-yandex-seo-skill
- https://github.com/manojahi/serpiq

## GEO / AEO / AI Search

- https://github.com/onvoyage-ai/gtm-engineer-skills
- https://github.com/Auriti-Labs/geo-optimizer-skill
- https://github.com/amplifying-ai/awesome-generative-engine-optimization
- https://github.com/cxcscmu/AutoGEO
- https://github.com/luka2chat/awesome-geo
- https://github.com/geo-team-red/geo-optimizer
- https://github.com/ai-search-guru/getcito-worlds-first-open-source-aio-aeo-or-geo-tool
- https://github.com/DavidHuji/Awesome-GEO
- https://github.com/AIcling/agentic_geo
- https://github.com/alexpospekhov/searchstack-aeo
- https://github.com/multivmlabs/aeo.js

## llms.txt

- https://github.com/AnswerDotAI/llms-txt
- https://github.com/thedaviddias/llms-txt-hub
- https://github.com/firecrawl/llmstxt-generator
- https://github.com/krish-adi/llmstxt-site
- https://github.com/dotenvx/llmstxt
- https://github.com/pawamoy/mkdocs-llmstxt
- https://github.com/SecretiveShell/Awesome-llms-txt
- https://github.com/delucis/starlight-llms-txt

## Periodic Refresh Procedure

1. Check upstream changes in official docs from `sources.md`.
2. Check release/readme changes in the repos above.
3. Search GitHub for new high-signal repos:
   - `generative engine optimization`
   - `AI search optimization`
   - `AEO SEO skill`
   - `llms.txt`
   - `technical SEO audit skill`
   - `Yandex SEO skill`
4. Compare against current `SKILL.md` and references.
5. Update this skill only when the change affects methodology or workflow.
6. Add or refresh project `todo.md` reminders in your private project list when methodology changes.
7. If a repo is inactive, low-quality, or misleading, remove or demote it.

## Recent Signals

- 2026-05-11: `Auriti-Labs/geo-optimizer-skill` v4.10.3 added useful Tier 4 methodology signals: negative-signal scoring for `X-Robots-Tag`, `noai` / `noimageai`, high `Crawl-delay`, sitemap freshness ordering, schema completeness, and priority-aware batching. Keep using this as a discovery signal only; official crawler and robots behavior remains Tier 1.
