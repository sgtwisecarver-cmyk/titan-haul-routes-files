# titan-haul-routes-files
Route-map PDFs (`pdfs/`) and the site safety video (`videos/`) for https://titanenergytech.com, served by this
repo's own GitHub Pages site so the main site deploys fast (the main repo was ~620 MB to publish; now ~20 MB).

- The main site still links PDFs as `pdfs/<path>` (same-site). Its service worker fetches them from here and keeps
  each one on the phone once opened, so they work with no signal. Visitors without the service worker are sent here
  by the main site's 404 page. Pad pages and the safety video link here directly.
- Adding a route map: put it in `pdfs/<customer>/`, commit and push here; point the card's `url` / `docs[].url` at
  `pdfs/<customer>/<file>.pdf` in the main repo's `data/pads/<customer>.json`.
- Base URL (one constant in the main repo, `FILES` in sw.js / index.html / tools): https://sgtwisecarver-cmyk.github.io/titan-haul-routes-files/
