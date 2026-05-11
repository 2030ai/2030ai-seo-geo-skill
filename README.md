# 2030ai SEO/GEO Skill

An operator skill for SEO, GEO, AI-search visibility, and search-driven conversion work.

It is designed for agentic coding environments where the assistant can inspect a site or local repository, produce a prioritized backlog, implement safe fixes, verify the result, and update project tracking.

## What It Covers

- Technical SEO: crawlability, indexability, redirects, canonicals, sitemaps, robots, metadata, headings, internal links, image alt text, and rendered HTML checks.
- Structured data: JSON-LD/schema validation, visible-content alignment, entity graph, and `sameAs` hygiene.
- GEO and AI-search readiness: AI crawler policy, `llms.txt`, answer-first passages, quotable facts, citations, source clarity, and prompt-set tracking.
- Russian-market SEO: Yandex Webmaster/Metrica, Yandex schema behavior, ruble payments, Russian-language trust signals, Telegram/VK/Habr/vc.ru surfaces, privacy and legal-page checks.
- Execution workflow: audit, plan, implement, verify, and track progress.

## Repository Layout

```text
.
|-- SKILL.md
|-- agents/
|   `-- openai.yaml
`-- references/
    |-- execution.md
    |-- methodology.md
    |-- monitored-repos.md
    |-- russia.md
    `-- sources.md
```

`SKILL.md` is intentionally concise. The heavier methodology, source lists, Russian-market notes, and refresh watchlist live in `references/` so an agent can load only what it needs.

## Commands

The skill supports these task modes:

- `audit <url-or-project>`: inspect a site or local repo and produce a prioritized backlog.
- `plan <url-or-project>`: turn audit findings into a staged implementation plan.
- `execute <url-or-project>`: implement approved or obvious fixes in the local repo.
- `verify <url-or-project>`: rerun checks and compare against the baseline.
- `track <url-or-project>`: update project `todo.md` or search-visibility docs.
- `monitor`: refresh the skill methodology from official docs, research, and monitored repositories.

When no command is provided, default to `audit`. When the user asks to fix issues and a local repo is available, run `audit -> plan -> execute -> verify -> track`.

## Installation

Clone the repository:

```bash
git clone https://github.com/2030ai/2030ai-seo-geo-skill.git
```

Then expose it to your agent runtime as a skill. For example:

```bash
ln -sfn "$PWD/2030ai-seo-geo-skill" "$HOME/.codex/skills/2030ai-seo-geo-skill"
```

If your environment uses a different skill directory, symlink or copy the repository there.

## Refresh Model

The public repository contains the reusable skill and generic reference watchlist. If you run a private ecosystem or multi-project maintenance workflow, keep local project paths, private predecessor skills, and client-specific todo targets outside this repository.

A healthy refresh workflow should:

1. Check official documentation first: Google Search Central, Yandex Webmaster/Metrica, Schema.org, Bing, IndexNow, web.dev, and crawler docs from AI providers.
2. Check research and industry sources for material methodology changes.
3. Review monitored GitHub repositories as signal, not truth.
4. Update `SKILL.md` and `references/*.md` only when the change affects the actual workflow.
5. Validate YAML/frontmatter.
6. Commit and push the public repository.
7. Update any local installed skill symlink or checkout used by your private agent environment.

## Evidence Standard

The skill uses four evidence tiers:

- Tier 1: official documentation and first-party tool output.
- Tier 2: research papers with dates and citation details.
- Tier 3: industry studies with dates, samples, and uncertainty.
- Tier 4: GitHub repos, tools, blog posts, Reddit/forum observations.

Tier 4 is useful for discovery. It should not override official documentation.

## Non-Goals

- It does not promise AI-search rankings.
- It does not recommend fake reviews, hidden content, fake statistics, or unsupported compliance claims.
- It treats `llms.txt` as an emerging convention, not an official ranking requirement.
- It keeps robots decisions separate for search/referral crawlers and training crawlers.

## License

No license is declared yet. Treat the repository as source-available until a license is added.
