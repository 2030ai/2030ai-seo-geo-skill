# Official SEO/GEO refresh

## Что изменилось

- Добавлена условная проверка Google Preferred Sources для подходящих publisher/content sites без штрафа за отсутствие.
- Уточнена региональная проверка Google site reputation abuse policy для EEA и остальных рынков.
- Разделены блокировка `OAI-SearchBot` и полное исключение URL через читаемый `noindex`.
- Канонические ссылки добавлены в `references/sources.md`; версия skill обновлена до `0.1.8`.

## Проверка

- Frontmatter разобран как YAML; `name` и версия `0.1.8` подтверждены. Общий `quick_validate.py` неприменим без адаптации: он отклоняет уже существующие Claude-compatible поля `user-invocable` и `argument-hint`.
- Markdown новых строк не добавляет lint-ошибок; в `references/sources.md` остаётся 61 ранее существовавший `MD034`. `git diff --check` проходит.
