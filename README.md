# subastados.es

Landing estática de venta de **Subastas Scraper + Pujable** (producto de InversionNPL).

- `index.html` — página única, self-contained (CSS/JS inline, fuente Outfit de Google Fonts).
- Checkout: `POST https://inversionnpl.com/api/public/subastados/checkout` (módulo `OrenesBackend/src/subastados.ts` del repo Orenes.Fund). El acceso se concede por webhook de Stripe: cuenta existente → acceso inmediato; sin cuenta → email para registrarse y un sweep lo activa al registrarse.
- Subastas en vivo: `GET /api/subastas/preview` (público, CORS habilitado para este dominio).
- Servida por nginx en el VPS de Orenes (`/etc/nginx/sites-available/subastados.es`), repo clonado en `~/subastados.es` del server. Deploy: `git pull` en el server (no hay build).
