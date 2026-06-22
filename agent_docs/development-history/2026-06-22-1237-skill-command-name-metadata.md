# [2026-06-22 12:37] Skill command-name metadata

Файл: `agent_docs/development-history/2026-06-22-1237-skill-command-name-metadata.md`

## Что сделано

- Root skill metadata сохранена в формате `/2030ai-seo-geo-skill`.
- `agents/openai.yaml` дополнен machine-readable полями `name`, `description`, `short_description`, `default_prompt`.

## Зачем

Чтобы root skill repo показывал в UI ровно slash-команду, которую вызывает пользователь.

## Обновлено

- [ ] agent_docs/architecture.md (не применимо)
- [ ] agent_docs/adr/YYYY-MM-DD-HHMM-title.md (не применимо)
- [ ] Тесты (не применимо, metadata-only)
- [x] Документация

## Связанные решения

- Не применимо.

## Следующие шаги

- При изменении skill metadata сохранять соответствие `/2030ai-seo-geo-skill`.
