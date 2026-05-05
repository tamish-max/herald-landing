# herald-landing

Static landing page for **herald** (closed beta).

This repo contains nothing but the marketing site — a single `index.html`
with inline CSS and a tiny inline JS sprinkle. No build step, no
framework, no dependencies.

The actual product (a Go MCP server) lives elsewhere:

- **Source (private, invite-only):** `tamish-max/herald`
- **Signed binaries (public, key-gated):** [`tamish-max/herald-releases`](https://github.com/tamish-max/herald-releases)

## Local preview

```bash
# any static server works
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy on Vercel

1. Go to https://vercel.com/new
2. Import this repo (`tamish-max/herald-landing`)
3. Framework preset: **Other** (no build needed)
4. Build command: *(leave blank)*
5. Output directory: *(leave blank — root)*
6. Click **Deploy**

That's it. Vercel will serve `index.html` at the project root and
honour the headers in `vercel.json` (security headers + don't cache
the HTML so you can ship copy changes by pushing to `main`).

### Custom domain

Settings → Domains → Add. Point your DNS at Vercel per their docs.

## Editing copy

Everything is in `index.html`. Search for the section markers
(`<!-- ── … ─ -->`) to find the bit you want to change.

Things you'll likely want to update:

- `https://tally.so/r/jaGYNa` — the early-access form (live)
- The `STEP 01 … STEP 05` quickstart block — keep in sync with the
  install instructions in `tamish-max/herald-releases`
- The version pill in the hero ("v0.2.0 · closed beta")

## Why a separate repo?

So the landing page can iterate independently of the binary release
cadence and ship to Vercel on every push without touching the release
repo.
