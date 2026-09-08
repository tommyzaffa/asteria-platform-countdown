# asteriaplatform.com

Pagina singola di attesa per ASTERIA. Countdown al **1 gennaio 2027, 00:00 Europe/Zurich**.

## Struttura

| File | Ruolo |
| --- | --- |
| `index.html` | La pagina. Statica, zero dipendenze, i18n in 8 lingue via JS. |
| `og.html` | Sorgente per l'immagine di anteprima link. |
| `og.png` | Immagine OG generata (1200×630). |
| `robots.txt`, `sitemap.xml` | SEO di base. |

## Sviluppo

Apri `index.html` nel browser. Non serve build.

## Rigenerare `og.png`

```sh
"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" \
  --headless --disable-gpu --hide-scrollbars \
  --screenshot=og.png --window-size=1200,630 --virtual-time-budget=6000 og.html
```

## Modificare il countdown

La data target è in `index.html`, in `TARGET`. È espressa in UTC: il 1 gennaio 2027 Zurigo è CET (UTC+1), quindi `Date.UTC(2026, 11, 31, 23, 0, 0)`.

## Lingue

`it` (default) · `en` · `fr` · `de` · `es` · `pt` · `ja` · `zh` — rilevate dal browser, sovrascrivibili dal selettore e memorizzate in `localStorage`.
