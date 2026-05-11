# Russian-Market SEO/GEO Layer

Apply this file for projects aimed at Russia/CIS users, especially Russian-language education, AI, SaaS, expert, event, and content sites.

## Search / Analytics Stack

- Yandex Webmaster sitemap and indexing checks: https://yandex.com/support/webmaster/en/indexing-options/sitemap
- Yandex Webmaster indexing recommendations: https://yandex.ru/support/webmaster/en/recommendations/indexing
- Yandex Schema.org docs and validator: https://yandex.ru/support/webmaster/en/schema-org/what-is-schema-org
- Yandex Search with Yandex AI: https://yandex.com/support/webmaster/en/yandex-ai
- Yandex Search with Alice: https://yandex.ru/support/webmaster/en/alice
- Yandex robot verification and `YandexAdditionalBot`: https://yandex.ru/support/webmaster/en/robot-workings/check-yandex-robots
- Yandex Metrica docs: https://www.yandex.com/support/metrica/en/
- Yandex Metrica recommended goals: https://yandex.com/support/metrica/en/general/recommend-goals
- Yandex Direct search-query reports and goals should be considered for commercial pages receiving paid traffic.

## Russian Conversion Signals

For Russian AI/education/SaaS projects, verify visible answers to:

- Works in Russia without VPN, if true.
- Russian cards/ruble payments, if true.
- Telegram contact/channel/community.
- Russian-language support and examples.
- Data hosting / privacy / 152-FZ statements where relevant.
- Legal entity, offer, privacy policy, consent pages.
- Clear trial/subscription terms and cancellation.
- Compatibility with Russian workflows: Yandex, VK, Telegram, Excel/Google Sheets alternatives, corporate network restrictions.

Do not invent compliance or security claims. If a fact is unknown, create a task to confirm it with the owner.

## Russian Off-Site GEO Sources

Priority surfaces:

- Habr: technical credibility, developer and AI-tool audience.
- vc.ru: business, SaaS, marketing, founder stories.
- Telegram channels: main distribution and community proof.
- YouTube/Rutube/VK Video: explainers, webinar recordings, descriptions with canonical links.
- Dzen and VK: additional Russian-indexable surfaces when content already exists.
- University/conference pages, Innopolis-related pages, partner pages.
- 2GIS/Yandex Business for local or event-related surfaces.

## Yandex-Specific Checks

- `robots.txt` must not accidentally block `Yandex`.
- `Sitemap:` directive should be present and reachable.
- Important content should be server-rendered or visible in HTML.
- Check canonical and redirect behavior for `www`/apex and HTTP/HTTPS.
- Yandex may process sitemap updates slowly; record the verification date.
- For paid traffic pages, connect Metrica goals to actual lead/signup/payment events, not only button clicks.

## Yandex AI / Search with Alice Checks

- Check whether generated-answer participation is desired for Russian priority pages.
- If participation is desired, do not block `YandexAdditionalBot` / `YandexAdditional` for those pages.
- If participation is not desired, document explicit `robots.txt` restrictions for `YandexAdditionalBot` / `YandexAdditional` and record the verification date.
- Treat `YandexAdditionalBot` separately from `YandexBot`: Yandex docs describe it as a generated-answer / Alice surface for pages already indexed by the primary crawler, not as an indexing crawler.
- When auditing server logs, classify `YandexAdditionalBot` / `YandexAdditional` traffic separately from primary indexing, screenshots, Metrica, Ads, Images, and other Yandex robots.
- For Search with Alice readiness, prefer well-structured and informative pages with clear source-worthy facts, offers, prices, dates, and entity details.

## Common Russian-Project Risks

- Good Google SEO but missing Yandex Webmaster/Metrica verification.
- Robots rules accidentally block Yandex AI/Alice answer use while leaving ordinary Yandex indexing open, or vice versa.
- Landing promises "без VPN", "данные в РФ", "152-ФЗ" without verified facts.
- Telegram-only conversion without fallback or analytics event.
- Legal pages copied from old sites and mismatched to current product/payment model.
- Off-site mentions spread across Telegram but not repeated in indexable web pages.
