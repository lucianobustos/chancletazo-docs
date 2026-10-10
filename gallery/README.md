# 📸 Galería de capturas

Capturas mobile (iPhone 13) generadas automáticamente por el tour de Playwright.

## Cómo se genera

```bash
# Una sola vez:
npm install
npx playwright install chromium

# Cada vez que querés actualizar la galería:
npm run dev          # API (NODE_ENV=development obligatorio para dev-login)
npm run frontend     # Next.js
npm run tour         # ejecuta Playwright + regenera index.html
```

`npm run tour` reutiliza los servers si ya están corriendo. Si no, los arranca él.

## Convenciones

- Archivo: `<role>__<slug>.png` — determinístico, una corrida sobreescribe la anterior.
- Roles: `admin`, `manager`, `user`, `guest`.
- Setup: el tour promociona `player3@test.com` a manager si no lo es (idempotente).
- La galería en sí es `index.html` — abrir directo en el browser, sin servidor.

## Modificar las rutas recorridas

Editar [`tests/e2e/routes.js`](../../tests/e2e/routes.js). Cada entrada:

```js
{ path: '/foo?bar=1', slug: 'foo-bar', label: 'Foo' }
```

## Solo regenerar la galería

```bash
npm run gallery
```
