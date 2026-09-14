# Gabriel Dantas — portfolio

Static portfolio site plus the CV source and the project docs.

```
site/            the website (index.html, assets/, img/, cv.pdf)  ← what gets deployed
cv-en.html       CV source; regenerate the PDF with Chrome headless (see docs/current-state.md)
docs/            content source (timeline.md), specs, LinkedIn/GitHub profile texts
package.json     `npm start` serves site/ with `serve` — the command Railway runs
railway.json     Railway deploy settings (start command, healthcheck on /)
```

## Run locally

```bash
npm install
npm run dev        # http://localhost:4173
```

## Deploy on Railway

1. Push this repository to GitHub.
2. Railway → New Project → Deploy from GitHub repo → pick it.
3. Nothing else to configure: Railway detects `package.json`, runs `npm install`, then
   `npm start`, which serves `site/` on the `PORT` Railway injects. `index.html` is the root.
4. Generate a public domain in Settings → Networking, then put it on the CV and profiles.

The `-s` flag on `serve` is the SPA fallback: any unknown path returns `index.html`.
