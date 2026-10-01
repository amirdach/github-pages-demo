# GitHub Pages Demo

A minimal static HTML demo page (no backend, no secrets) ready to publish with GitHub Pages.

## 1. Publish with GitHub Pages

1. Create a new GitHub repository (e.g. `my-demo-page`).
2. Add `index.html` (from this folder) to the repo root.
3. Push to the `main` branch.
4. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, select `main` / `root`, save.
5. Your page will be live at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

## 2. Restrict access to specific people (recommended)

GitHub Pages itself is public once published. To limit who can actually view it:

### Option A — Cloudflare Access (free up to 50 users)
1. Add a custom domain/subdomain you control (e.g. `demo.yourdomain.com`) and point it at GitHub Pages via CNAME.
2. In Cloudflare, enable **Zero Trust → Access → Applications**, create an app for that hostname.
3. Add a policy allowing only specific emails (or your Google Workspace/Entra ID group).
4. Visitors now must authenticate via Cloudflare before reaching the page.

### Option B — Keep the repo private + GitHub Pages access control (GitHub Enterprise only)
Private repo Pages visibility restriction requires GitHub Enterprise Cloud; not available on free/personal plans.

### Option C — Simple obscurity (not real security)
Use an unguessable repo/page name and share the link only with intended recipients. **Not recommended** if the content is sensitive — anyone with the link can view it and it may get indexed.

## Notes
- Keep everything client-side; never put API keys or secrets in this HTML/JS since it's publicly servable once deployed.
- Use Cloudflare Access (or Tailscale Funnel) if you need real access control rather than a hidden link.
