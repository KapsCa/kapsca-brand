# Brand guide — KapsCa (v1)

Reglas de aplicabilidad del kit. Medidas sobre los tokens de `tokens.json` (contraste WCAG y ΔE), no criterios de gusto.

## 1. Dónde vive cada versión

| Contexto | Asset | Motivo |
|---|---|---|
| README en GitHub (dark) | `kapsca-logo-principal-transparente.png` | SIN fondo horneado: el tile `#0D0E12` del PNG dark resalta feo contra el canvas de GitHub |
| README en GitHub (light) | `kapsca-logo-monocromo-negro.svg` | tinta única `#0D0E12`, escalable |
| Favicon web | `favicon.ico` + `<link rel="icon" type="image/svg+xml" href="kapsca-isotipo.svg">` | multi-size + vector moderno |
| Banner de repo | `kapsca-repo-banner-1280x640.png` | resolución exacta del preview de GitHub |
| Banner de perfil | `kapsca-profile-banner-1500x500.png` | resolución exacta del profile |
| Avatar / app icon | isotipo (`favicon512.png`, `kapsca-isotipo-dark-avatar.png`) | íconos circulares de UI |
| Print / grande | SVGs | escala infinita |

*Nota vector: los SVG son un trazado fiel en geometría con degradados aproximados (coreΔ medio ~11 RGB). Para reproducir el degradado exacto del generador, usar los PNG.*

## 2. Tamaño y espacio

- Tamaño mínimo del isotipo en pantalla: **32 px** (por debajo, uso `favicon.ico` que tiene set propio).
- Área de respeto alrededor: el **25% del ancho** del isotipo en cada lado.
- NO rotar, NO recolorear, NO agregar sombras o contornos propios.  
- La tinta monocroma válida es una sola: `#ECE9F2` (dark) o `#0D0E12` (light). El logo no se tinta de otros colores.

## 3. Reglas de color (ambas prohibiciones han sido medidas)

1. `#CE97EB` (brand) sobre blanco = **2.26:1**. En modo claro, el violeta de marca NO sirve como texto: usar `#7A2E9E`.
2. `#E5384F` (accent) sobre `#CE97EB` = **1.85:1**. NO poner rojo sobre violeta claro: se lee como mancha, no como acento.
3. Dark por defecto; light solo vía `data-theme` explícito, nunca `prefers-color-scheme` (una app dark-only cambió su paleta con el SO).

## 4. Consumo vendido

Cada repo lleva `assets/brand/` con:

- `banner.png` — banner de repo (1280×640)
- `kapsca-512.png` — isotipo transparente 512
- `kapsca-mono-white.svg` — monocromo blanco vector
- `kapsca-favicon.ico` — favicon multi-size

Ese set pesa ~370 KB y NO depende de este repo (copia). Los archivos completos/regenerados provienen del release del SOT.

## 5. Pipeline para repos nuevos

`repo-bootstrap` (installer `install-repo-standards.sh`, paso brand) copia el set desde la copia vendida en `dev-skills/repo-bootstrap/assets/kapsca-brand/`, el cual se actualiza desde el release del SOT.

> **Regla de fondo horneado**: el PNG `-dark` (fondo `#0D0E12` horneado) sólo para contextos que ya son de ese color (avatares, social preview, fondos propios). En READMEs de GitHub usar SIEMPRE el `-transparente` (dark) o el monocromo SVG (light).
