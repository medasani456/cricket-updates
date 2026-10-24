# cricket-updates 2026

Static website for the TuS Komet Arsten cricket section, live at https://kometcricket.xyz.

## Structure

- `index.html` â€“ home (score ticker, hero story, news, standings, video, photos)
- `tpl2026results.html` â€“ TPL 2026 results, points table, gallery
- `2026_indoor.html` â€“ Indoor tournament match centre
- `2026_auction.html` â€“ Auction recap and squads
- `styles.css`, `main.js` â€“ shared styling and mobile menu
- `images/` â€“ logo and event photos

## Deployment (GitHub Pages)

Every push to `main` publishes the site to GitHub Pages via `.github/workflows/static.yml`:
https://medasani456.github.io/cricket-updates/

To use a custom domain later: repo **Settings → Pages → Custom domain**, then point the domain's DNS at GitHub Pages.

## Optional: Namecheap hosting

`.github/workflows/deploy-namecheap.yml` uploads the site to Namecheap over FTP. It currently runs only when started manually from the **Actions** tab.

One-time setup:

1. In Namecheap cPanel â†’ **FTP Accounts**, note the FTP server and username (or create an FTP account whose directory is `public_html`).
2. In GitHub â†’ repo **Settings â†’ Secrets and variables â†’ Actions**, add:
   - `FTP_SERVER` â€“ e.g. `ftp.kometcricket.xyz` (or the server hostname shown in cPanel)
   - `FTP_USERNAME` â€“ the cPanel/FTP username
   - `FTP_PASSWORD` â€“ its password
3. Push to `main`, or run the workflow manually from the **Actions** tab.

If you created a dedicated FTP account whose home is already `public_html`, change `server-dir` in the workflow to `./`.

Manual alternative: cPanel â†’ **File Manager** â†’ `public_html` â†’ upload all files and the `images` folder (keep the same folder structure).
