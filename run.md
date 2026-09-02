# Run Commands

Gemini Watermark Remover is a **static, fully client-side site** — plain HTML/CSS/vanilla JS.
There is no build step, no `package.json`, and no backend. You just need any static file server.

> Opening `index.html` directly with `file://` is **not** reliable: `main.js` dynamically imports
> MediaBunny as an ES module (`await import('https://cdn.jsdelivr.net/npm/mediabunny@1.52.3/+esm')`),
> which browsers block over `file://`. Always serve over HTTP.

---

## Start the app

### Option A — Python 3 (no install needed on macOS)

```bash
cd /Users/manassingh/Documents/GitHub/gemini-watermark-remover
python3 -m http.server 8000
```

### Option B — Node.js

```bash
cd /Users/manassingh/Documents/GitHub/gemini-watermark-remover
npx serve .          # serves on http://localhost:3000
# or
npx http-server -p 8000
```

### Option C — VS Code

Install the **Live Server** extension, then right-click `index.html` → *Open with Live Server*.

---

## Open in the browser

```bash
open http://localhost:8000
```

---

## Run in the background (keeps the terminal free)

```bash
cd /Users/manassingh/Documents/GitHub/gemini-watermark-remover
nohup python3 -m http.server 8000 > /tmp/gwr-server.log 2>&1 &
echo $!                       # note the PID
tail -f /tmp/gwr-server.log   # watch requests
```

---

## Verify it's serving correctly

```bash
curl -s -o /dev/null -w "index.html -> %{http_code}\n" http://localhost:8000/
curl -s -o /dev/null -w "main.js    -> %{http_code}\n" http://localhost:8000/main.js
curl -s -o /dev/null -w "style.css  -> %{http_code}\n" http://localhost:8000/style.css
```

All three should print `200`.

---

## Stop the server

```bash
# Foreground: Ctrl+C
# Background / port already in use:
lsof -ti:8000 | xargs kill
```

Check whether the port is already taken before starting:

```bash
lsof -ti:8000 || echo "port 8000 is free"
```

---

## Notes

- **Requirements:** only a browser + a static server. Verified with Python 3.14.4 and Node v24.15.0.
- **Watermark masks are inlined** as base64 (`BG_48_BASE64` / `BG_96_BASE64` in `main.js`), so no
  mask files need to be fetched at runtime.
- **Internet connection is needed** for the CDN dependencies: Google Fonts, Iconify, and MediaBunny (loaded lazily, only when you process a **video**). Image watermark
  removal works fully offline.
- **Video export requires WebCodecs** — use Chrome/Edge (or a recent Safari). Firefox support is limited.
- **Deployment:** GitHub Pages serves the repo root as-is. Pushing to `main` is the deploy.
