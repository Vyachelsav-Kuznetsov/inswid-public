# Inswid public resources

Публичные материалы мобильного приложения Inswid:

- `public/index.html` — политика конфиденциальности;
- `public/catalog/partner-offers.v1.json` — удалённый каталог ценовых ориентиров и ссылок страховщиков;
- `public/_headers` — заголовки безопасности и правила кэширования Cloudflare Workers Static Assets;
- `wrangler.jsonc` — конфигурация публикации статических файлов Cloudflare.

## Cloudflare Workers

Репозиторий подключается к Cloudflare Workers Builds через GitHub.

- Production branch: `main`
- Build command: оставить пустым
- Deploy command: `npx wrangler deploy`
- Root directory: оставить пустым
- Builds for non-production branches: выключить

После публикации:

- политика: `https://inswid-public.<subdomain>.workers.dev/`
- каталог: `https://inswid-public.<subdomain>.workers.dev/catalog/partner-offers.v1.json`

## Обновление каталога

1. Изменить `priceLabel` и/или `externalUrl`.
2. Увеличить `catalogVersion`.
3. Обновить `updatedAt` в формате ISO 8601.
4. Проверить файл в основном проекте командой `npm run catalog:validate`.
5. Скопировать проверенный файл сюда и отправить изменения в GitHub.