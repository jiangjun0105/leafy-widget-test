# Leafy Widget Test

A tiny static site to test loading the Leafy widget under a strict Content Security Policy (CSP).

## Files
- `index.html`: Test page with a CSP **meta** tag (works on GitHub Pages and Vercel).
- `vercel.json`: Adds the same CSP as a **response header** when deployed on Vercel (more realistic).

## Quick start – GitHub Pages
1. Create a new repo (e.g. `leafy-widget-test`) and push these files.
2. In **Settings → Pages**, choose **Deploy from a branch**, Branch=`main`, Folder=`/ (root)`.
3. Open `https://<your-user>.github.io/leafy-widget-test/` and check that the widget renders.

## Quick start – Vercel
1. Import the GitHub repo into Vercel **or** run `vercel` in this folder (CLI).
2. Vercel will serve `index.html` and apply the CSP headers from `vercel.json`.
3. Visit the deployment URL and check that the widget renders.

## What to verify in DevTools (Network)
- `gina.js` loads with **Status 200**, **type=module**, **Content-Type: text/javascript**.
- Requests to `*.leafy.studio` succeed (including any **preflight OPTIONS**).
- No **CSP** or **CORS** errors in the Console.
