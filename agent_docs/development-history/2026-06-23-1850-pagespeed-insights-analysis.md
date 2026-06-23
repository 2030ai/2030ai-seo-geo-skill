# [2026-06-23 18:50] PageSpeed Insights analysis

Файл: `agent_docs/development-history/2026-06-23-1850-pagespeed-insights-analysis.md`

## Что сделано

- Версия skill обновлена до `0.1.6`.
- PageSpeed Insights / Lighthouse / Core Web Vitals добавлены в trigger metadata и baseline workflow.
- В методологию добавлен отдельный PSI-раздел: mobile/desktop, категории Lighthouse, lab vs field data, CrUX fallback, приоритизация findings.
- В execution workflow добавлены поля, которые нужно сохранять при PSI-аудите и verify-pass.
- В sources добавлены официальные страницы PSI API и CrUX API/History API.

## Зачем

Чтобы SEO/GEO-аудит явно включал официальный Google PageSpeed Insights analysis, но не смешивал Lighthouse lab scores, CrUX field data и SEO/GEO outcomes.

## Обновлено

- [ ] agent_docs/architecture.md (не применимо)
- [ ] agent_docs/adr/YYYY-MM-DD-HHMM-title.md (новое архитектурное решение не принималось)
- [x] Тесты (ручная проверка diff и metadata)
- [x] Документация

## Связанные решения

- Нет.

## Следующие шаги

- При следующем monitor refresh проверить статус прекращения CrUX field data в PSI API и при необходимости усилить CrUX API guidance.
