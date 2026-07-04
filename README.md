# Huarocondo 2026 · LUCHA

Sitio estático de una sola página (`index.html`, sin dependencias ni build) con el
planeamiento semestral de LUCHA: Resumen, Dinámicas, Domingo 05, Lunes 06, Martes 07
y Post Huarocondo.

## Estructura

```
huarocondo-2026-lucha/
├── index.html      ← todo el sitio (HTML + CSS + JS inline, logo embebido en base64)
├── vercel.json     ← config mínima para Vercel (cleanUrls)
├── .gitignore
└── README.md
```

No hay paso de build: es HTML plano. Cualquier hosting estático (Vercel, Netlify, GitHub Pages) lo sirve tal cual.

## 1. Subir a GitHub

Desde esta carpeta, en tu terminal:

```bash
cd huarocondo-2026-lucha
git init
git add .
git commit -m "Huarocondo 2026 - planeamiento semestral LUCHA"
```

Crea el repo en GitHub (puede ser privado, ya que tiene info interna de Lucha):

```bash
gh repo create lucha-huarocondo-2026 --private --source=. --remote=origin --push
```

Si no tienes `gh` (GitHub CLI) instalado, crea el repo manualmente en github.com y luego:

```bash
git remote add origin https://github.com/TU_USUARIO/lucha-huarocondo-2026.git
git branch -M main
git push -u origin main
```

## 2. Hostear en Vercel

**Opción A — Dashboard (más simple):**
1. Entra a [vercel.com/new](https://vercel.com/new)
2. Importa el repo `lucha-huarocondo-2026` que acabas de subir
3. Vercel detecta que es un sitio estático automáticamente (no hay que tocar ningún ajuste de build)
4. Deploy

**Opción B — CLI:**
```bash
npm i -g vercel
vercel login
vercel --prod
```

Cualquiera de las dos te da una URL tipo `https://lucha-huarocondo-2026.vercel.app` para proyectar directamente en el retiro.

## 3. Actualizar el sitio después

Cada vez que haya una nueva versión del artifact:

```bash
git add .
git commit -m "Actualiza agenda del martes"
git push
```

Vercel redeploya solo con cada push a `main`.

## Privacidad

Este contenido incluye información interna de Lucha (OKRs, restricciones de planilla, etc.).
Si el repo de GitHub es privado, considera además activar protección por contraseña del
deployment en Vercel (Project Settings → Deployment Protection) antes de compartir la URL
fuera del equipo.
