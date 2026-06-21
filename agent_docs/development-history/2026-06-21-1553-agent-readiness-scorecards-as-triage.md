# 2026-06-21 15:53 — Agent-readiness scorecards добавлены как triage

Файл: `agent_docs/development-history/2026-06-21-1553-agent-readiness-scorecards-as-triage.md`

## Что сделано

- Версия skill обновлена до `0.1.5`.
- `isitagentready.com` добавлен в SEO/GEO workflow как внешний smoke/triage check для agent-readiness.
- В методологию и execution workflow добавлены guardrails: проверять actionable findings напрямую и не создавать fake API/OAuth/MCP/A2A/WebMCP/commerce metadata ради score.
- В reference sources добавлены Cloudflare Agent Readiness, RFC 8288, RFC 9727, Cloudflare Markdown for Agents, DNS-AID draft, Content Signals draft, Agent Skills Discovery и WebMCP.

## Зачем

На `zvasil.ru` внешний scorecard оказался полезен для обнаружения реальных низкорисковых улучшений (`Link` headers, Markdown negotiation, Content Signals), но также предлагал много неприменимых API/Auth/MCP/commerce checks. Skill теперь явно фиксирует эту границу, чтобы будущие SEO/GEO аудиты использовали такие scorecards как диагностический список, а не как повод публиковать несуществующие machine-readable surfaces.

## Обновлено

- [ ] agent_docs/architecture.md (не применимо)
- [ ] agent_docs/adr/YYYY-MM-DD-HHMM-title.md (новое архитектурное решение не принималось)
- [x] Тесты (markdownlint / diff review)
- [x] Документация

## Связанные решения

- Нет.

## Следующие шаги

- При следующих monitor-обновлениях проверять стабильность DNS-AID, Content Signals, Agent Skills Discovery и WebMCP только по первичным источникам.
