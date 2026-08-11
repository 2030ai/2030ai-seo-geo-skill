# [2026-08-12 09:50] AI visibility and crawler guidance refresh

Файл: `agent_docs/development-history/2026-08-12-0950-ai-visibility-crawler-refresh.md`

## Что сделано

- Добавлены Bing Webmaster Tools AI Visibility Insights как first-party источник измерения цитирования в Bing/Copilot.
- Разделены роли `ClaudeBot`, `Claude-User` и `Claude-SearchBot`.
- Зафиксировано удаление Google FAQ rich result при сохранении валидности `FAQPage` в schema.org.
- `Google-Extended` отделён от training-only crawlers: он также управляет grounding в Gemini Apps и Vertex AI.
- Версия скилла обновлена с `0.1.6` до `0.1.7`.

## Зачем

Методика должна различать обучение моделей, user-triggered fetch, поисковую индексацию и grounding, чтобы аудит не давал неверные рекомендации по `robots.txt` и корректно измерял AI-видимость.

## Проверка

- Утверждения сверены с официальными источниками Bing, Anthropic и Google.
- Выполнены структурная проверка скилла и Markdown lint.
- `git diff --check` не выявил ошибок.

## Обновлено

- [x] `SKILL.md`
- [x] `README.md`
- [x] `references/execution.md`
- [x] `references/methodology.md`
- [x] `references/sources.md`
- [x] `agent_docs/development-history/`

## Связанные решения

- ADR не нужен: архитектура и границы скилла не изменились.

## Следующие шаги

- Следующий refresh проводить только после новых официальных изменений источников или подтверждённых результатов запусков.
