# RadioHabbo

Sitio web de radio en vivo construido con Next.js (Pages Router). Incluye un banner con gradiente, reproductor embebido, hora y fecha de Venezuela (America/Caracas) desde un endpoint propio, avatar de Habbo ("keko") y preparación para Google AdSense.

## Características
- Banner con gradiente y foto/título alineados a la izquierda
- Reproductor de radio (widget de Caster.fm) listo para reemplazar por un player propio
- Hora y fecha de Caracas desde `/api/hora` usando Luxon
- Avatar Habbo dinámico con parámetro anti-cache
- Estilos responsivos y tema oscuro
- Integración de AdSense (script en `_app.js` y `public/ads.txt`)

## Tech Stack
- Next.js, React, Luxon
- CSS plano en `styles/styles.css`
- Despliegue recomendado: Vercel

## Estructura del proyecto
```
package.json
pages/
  _app.js
  index.js
  api/
    hora.js
public/
  ads.txt
  imagenes/
styles/
  styles.css
```

## Scripts
- `pwsh> npm run dev` — servidor de desarrollo
- `pwsh> npm run build` — build de producción
- `pwsh> npm start` — iniciar build en producción

## Desarrollo local
1. Instalar dependencias: `npm install`
2. Ejecutar en dev: `npm run dev`
3. Abrir `http://localhost:3000`

## Despliegue (Vercel)
- Conecta el repo en Vercel
- Framework: Next.js; Node 18+ recomendado
- La API `/api/hora` se despliega como ruta serverless automáticamente

## Configuración
- AdSense: Meta + script en `pages/_app.js` y `public/ads.txt` (reemplaza el `client` si aplica)
- Avatar Habbo: Edita el usuario en `pages/index.js` (parámetro `user=`)

## Hora de Caracas (API)
- Endpoint: `pages/api/hora.js`
- Respuesta ejemplo: `{ "hora": "12:34 PM", "fecha": "01 de enero de 2025" }`

## Streaming de audio
- Actualmente usa el widget de Caster.fm. Para un player propio necesitarás un servidor de streaming (Icecast/Shoutcast) y emitir con un encoder (p. ej., BUTT). En Vercel no es viable alojar Icecast; considera VPS.

## Licencia
ISC
