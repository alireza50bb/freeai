# ZERO INDEX

A one-page, live field guide to AI models you can run as a coding agent for $0 on your own computer: local weights, free hosted agents, and free API tiers. Every route includes the exact setup commands, the published limits, and the privacy catch.

## Run it

```bash
node serve.mjs
# → http://127.0.0.1:4173
```

No dependencies, no build step. The server is a zero-dependency static file server; `index.html` also works when opened directly, though the live feed is happier over HTTP.

## How it is built

- `index.html` — page shell and static copy
- `assets/css/styles.css` — the whole visual system (no framework)
- `assets/js/data.js` — 24 curated routes, limits, recipes, playbook, base URLs, and the offline snapshot
- `assets/js/app.js` — filtering, recipe drawer, live feed, match finder, copy interactions
- `serve.mjs` — local static server on port 4173

## The live layer

The “Live wire” panel fetches `https://openrouter.ai/api/v1/models` in the browser, filters for text models priced at $0 input and output, and refreshes every 60 seconds. The endpoint sends `Access-Control-Allow-Origin: *`, so no backend is required. If the request fails or times out, the panel falls back to the curated snapshot in `data.js` and says so.

The rest of the atlas is deliberately curated rather than scraped: provider limits live in consoles and change without stable APIs. Each card links to the provider page it was verified against.

## Accuracy

Limits were read from provider documentation on **7 November 2026**. Free tiers rotate quickly — four OpenRouter free variants were removed in the week before that date, and Google flagged third-party Antigravity models in the Free column for removal on 18 November 2026. Always follow the source link on a card before depending on a route.
