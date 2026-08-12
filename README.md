# Inswid public resources

Публичные материалы мобильного приложения Inswid:

- `public/index.html` — политика конфиденциальности;
- `public/catalog/partner-offers.v1.json` — удалённый каталог ценовых ориентиров и ссылок страховщиков;
- `public/_headers` — заголовки безопасности и правила кэширования Cloudflare Pages.

## Cloudflare Pages

- Framework preset: `None`
- Build command: оставить пустым
- Build output directory: `public`

После публикации:

- политика: `https://<project>.pages.dev/`
- каталог: `https://<project>.pages.dev/catalog/partner-offers.v1.json`

## Обновление каталога

1. Изменить `priceLabel` и/или `externalUrl`.
2. Увеличить `catalogVersion`.
3. Обновить `updatedAt` в формате ISO 8601.
4. Проверить файл в основном проекте командой `npm run catalog:validate`.
5. Скопировать проверенный файл сюда и отправить изменения в GitHub.