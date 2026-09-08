# asteriaplatform.com

Pagina singola di attesa per ASTERIA. Countdown al **1 gennaio 2027, 00:00 Europe/Zurich**.

## Struttura

| File | Ruolo |
| --- | --- |
| `index.html` | La pagina. Statica, zero dipendenze, i18n in 8 lingue via JS. |
| `og.png` | Anteprima link, 1200×1200: il monogramma, nient'altro. |
| `favicon.ico`, `favicon-*.png`, `apple-touch-icon.png` | Monogramma A. |
| `robots.txt`, `sitemap.xml` | SEO di base. |
| `CNAME` | Dominio custom per GitHub Pages. |

## Sviluppo

Apri `index.html` nel browser. Non serve build.

## Rigenerare icone e anteprima

Dal logo sorgente (quadrato, sfondo nero incluso):

```sh
sips -s format png -z 1200 1200 logo.jpg --out og.png
sips -c 900 900 logo.jpg --out /tmp/mark.png -s format png   # toglie il padding
for s in 32 180 192; do sips -z $s $s /tmp/mark.png --out /tmp/icon-$s.png; done
```

Poi `favicon-32.png`, `favicon-192.png`, `apple-touch-icon.png` (180) e il
`favicon.ico` multi-size (16/32/48).

Se cambi `og.png`, aggiorna `og:image:width` / `height` in `index.html`.

## Modificare il countdown

La data target è in `index.html`, in `TARGET`. È espressa in UTC: il 1 gennaio 2027 Zurigo è CET (UTC+1), quindi `Date.UTC(2026, 11, 31, 23, 0, 0)`.

## Lingue

`it` (default) · `en` · `fr` · `de` · `es` · `pt` · `ja` · `zh` — rilevate dal browser, sovrascrivibili dal selettore e memorizzate in `localStorage`.
