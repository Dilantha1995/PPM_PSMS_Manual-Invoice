# PPM / PSMS Manual Quotation & Invoice Tool

Single-file HTML tool for creating quotations and invoices on Propharma Maldives / Pro Synergy Medical Systems letterhead, with product code search pulled from the QuickBooks product/service export.

## Files in this repo (replace everything with these three)

- `index.html` — the entire tool (this is the only file that matters; everything is self-contained: styles, product data, and logo are embedded in it)
- `vercel.json` — explicitly tells Vercel to serve this as a static site with the correct `text/html` content type (added to rule out any content-type/download issue)
- `README.md` — this file

## How to deploy on Vercel

1. In your GitHub repo, delete any other files so only these three remain at the **root** (not in a subfolder).
2. In Vercel → your project → **Settings → General → Build & Development Settings**:
   - Framework Preset: **Other**
   - Root Directory: blank (repo root)
   - Build Command / Output Directory / Install Command: leave empty
3. Push these files to the `main` branch (or upload via GitHub's web UI, commit directly to `main`).
4. Vercel will auto-deploy. Open the deployment in the **Deployments** tab and confirm it says "Ready".
5. Visit your project's root URL (e.g. `https://your-project.vercel.app/`) in an **incognito window** to avoid any cached download from earlier attempts.

## If it still downloads instead of opening

That means the issue is specific to the Vercel project's dashboard settings (most likely the production domain is still aliased to an old/broken deployment). In that case:
- Open the deployment's own unique preview URL (shown on the deployment page, looks like `your-project-abc123.vercel.app`) instead of the main domain.
- If the preview URL works but the main domain doesn't, go to **Settings → Domains** and re-promote/reassign the domain to the latest deployment.

## Using the tool

- Toggle **Quotation / Invoice** at the top.
- Click any text on the document to edit it directly (company info, bill-to, terms, etc.).
- In the CODE column of a line item, start typing a product code or name — a dropdown will show matches; selecting one fills in the description and rate automatically.
- **Convert to Invoice** turns a finished quotation into an invoice with one click, keeping all line items.
- **Print / Save as PDF** produces a clean printable copy (toolbar is hidden automatically).
- **Change logo** lets you swap the letterhead logo (e.g. for PSMS instead of PPM).

Nothing is saved automatically — this is a static, offline-capable tool with no backend or database. Use Print / Save as PDF as your save step once a document is finalized.
