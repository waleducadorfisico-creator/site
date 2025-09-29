# Wal-Ribeiro - docs static site

This repository contains a static site under the `docs/` folder used as the web UI and exporter for workout routines.

## Test locally

Serve the `docs/` folder with a local HTTP server and open the page in your browser:

PowerShell examples:

```powershell
# Using npx http-server
npx http-server .\docs -p 8080

# Or using Python
python -m http.server 8080 --directory docs
```

Open http://localhost:8080/src/pages/home.html and test the UI (categories, add gifs to day, export preview).

If categories do not appear, click the debug bar at the bottom-right and press "Recarregar categorias" to see errors.

## Deploy to GitHub Pages

This repo includes a GitHub Actions workflow at `.github/workflows/gh-pages.yml` that publishes the `docs/` folder to GitHub Pages on every push to `main`.

- The action uses `peaceiris/actions-gh-pages` and the automatically provided `GITHUB_TOKEN`. No additional secrets are required.
- After a successful run, your site will be available at `https://<your-username>.github.io/<repository>/` (enable Pages on `gh-pages` branch if necessary in repo settings).

## Notes

- The exporter creates a single self-contained HTML file with embedded images and the timer/player logic.
- `docs/public/categories.json` is included to improve compatibility when loading categories on static hosts.

If you want, I can remove the debug bar or generate a sample exported HTML file and commit it under `docs/exports/`.