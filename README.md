# UWAAN Alpha — Demographic Intelligence

Independent static demo for **https://alfa.uwaan.com/**. The main UWAAN website remains unchanged.

## Initial setup

1. Upload the original **`uwaan-alpha-ionos.zip`** archive to the repository root on `main`, **without extracting it**. Use GitHub **Add file → Upload files**.
2. Go to **Settings → Pages** and choose **GitHub Actions** as the deployment source.
3. In IONOS DNS, point the `alfa` CNAME to **`cboransoy40.github.io`** (no `https://`).
4. Under GitHub **Settings → Pages → Custom domain**, enter **`alfa.uwaan.com`** and save. Enable **Enforce HTTPS** when available.

The workflow at `.github/workflows/deploy-pages.yml` automatically extracts `public/` from the ZIP, copies the contents to the published root, creates `CNAME`, and deploys on every push to `main`.

If GitHub reports the deployment failed before the ZIP is uploaded, that is expected: the workflow requires the archive.

## Updating the demo

Replace `uwaan-alpha-ionos.zip` in the repository with the updated archive and commit. GitHub Actions redeploys the site.

The JSON/GeoJSON files inside the archive will be publicly downloadable; no PostgreSQL database connection is required for this static demo.
