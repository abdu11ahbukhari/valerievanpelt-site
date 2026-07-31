# valerievanpelt.com

Static site. One HTML file plus an `assets/` folder of images. No build step, no dependencies.

```
index.html
assets/          12 images (logos, Valerie cutout)
```

## Deploy on GitHub Pages

1. Create a **public** repo (Pages needs a paid plan to serve from a private repo).
2. Upload `index.html` and the `assets` folder to the repo root. Drag and drop in the browser works; no git required. Keep `assets` as a folder, the paths are relative.
3. **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main`, folder: `/ (root)`. Save.
4. Wait for the first build, then open the `github.io` URL to confirm it renders.

## Custom domain

1. **Settings → Pages → Custom domain** → enter `valerievanpelt.com` → Save. This writes a `CNAME` file to the repo.
2. In **GoDaddy → DNS** for valerievanpelt.com, replace the existing records:
   - Four `A` records for `@` pointing at the four IPs GitHub lists on that Pages settings screen.
   - One `CNAME` for `www` pointing at `<username>.github.io`.
   - Remove the old records pointing at GoHighLevel, or the domain will keep serving the old funnel.
3. Wait for DNS to propagate, then tick **Enforce HTTPS** once the certificate provisions (can take up to an hour).

## Before launch

- **Contact form.** The page has no working form. In the contact section there's a `form-slot` div with a placeholder. Paste the GoHighLevel form iframe (or a Formspree form) there and delete the placeholder div. Leads then flow into whatever CRM you point it at.
- **Collective Moves link.** Nav pill, About paragraph, and the green band all link to `https://collectivemoves.com`. That domain currently resolves to an unrelated arts collective, so confirm the real URL before going live.
- **One hotlinked image.** The About section photo still loads from GoHighLevel's CDN (`assets.cdn.filesafe.space`). If that account changes or the funnel is deleted, the image breaks. Download it from the GHL media library, save it into `assets/`, and update that one `src` in the About section.
- **Compass compliance.** Check with Compass marketing on required disclaimers and logo usage for agent sites.

## Editing later

Everything is in `index.html`, including the CSS in a `<style>` block. Edit, commit, and Pages redeploys in about a minute.

## Content notes

- Testimonials are real reviews from Valerie's Google Business Profile (5.0, 61 reviews), lightly trimmed for length. Pull full text from Google if you'd rather quote verbatim.
- Phone `214-708-2115`, email `valerie.vanpelt@compass.com`, Instagram `valerievanpeltgroup`.
- Service area is written as Addison and Dallas throughout.
