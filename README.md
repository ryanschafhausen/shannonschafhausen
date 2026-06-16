# Shannon Schafhausen, LMHC — website

A fast, static, single-page site for a Licensed Mental Health Counselor in Florida,
hosted on **GitHub Pages**. No build step, no framework — just `index.html` + `styles.css`,
so it loads instantly and is fully crawlable by search engines.

> Replaces the previous Angular app. The original Angular source is still in `src/`
> and the git history if it's ever needed.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire page (semantic HTML, SEO meta, JSON-LD, contact form). |
| `styles.css` | All styling. Palette/variables are at the top of the file. |
| `profile.png` | Portrait photo. |
| `favicon.ico` | Browser tab icon. |
| `robots.txt`, `sitemap.xml` | Search-engine discovery. |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll). |

All asset paths are **relative**, so the site works both at the current
`…github.io/shannonschafhausen/` URL **and** at the root of a custom domain.

## Deploying on GitHub Pages

In the repo: **Settings → Pages → Build and deployment**

- **Source:** *Deploy from a branch*
- **Branch:** the branch holding these files (e.g. `master`) and folder **`/ (root)`**

GitHub publishes within a minute or two. (The old setup deployed a built Angular
app to the `gh-pages` branch — once this is live you can delete that branch.)

## Before you go live — checklist

Search the project for these placeholders and replace them:

- [ ] **Contact email** — `CHANGE_ME@example.com` in `index.html`
- [ ] **Phone** — `tel:+10000000000` and the `[add phone]` text
- [ ] **Hours**, **Location**, **Fees**, **Insurance** — the `[add …]` notes
- [ ] **Contact form key** — get a free access key at <https://web3forms.com>
      and paste it into the `access_key` hidden field. Submissions are then
      emailed to you. (Formspree works the same way if preferred.)
- [ ] Confirm the **bio** wording (e.g. "over a decade" of experience).

> **Privacy note:** the contact form is intentionally limited to non-sensitive
> fields and is **not** HIPAA-compliant. Keep detailed health intake on a secure,
> BAA-covered platform (most scheduling tools offer this).

## Adding a custom domain later

1. Buy a domain from any registrar.
2. In **Settings → Pages → Custom domain**, enter it (this creates a `CNAME` file).
3. At your registrar's DNS:
   - Apex (`example.com`): four `A` records → `185.199.108.153`, `185.199.109.153`,
     `185.199.110.153`, `185.199.111.153`.
   - `www`: a `CNAME` record → `ryanschafhausen.github.io`.
4. Enable **Enforce HTTPS** once DNS verifies (GitHub issues a free certificate).
5. Update the absolute URLs (canonical, Open Graph, sitemap, robots, JSON-LD)
   in `index.html`, `sitemap.xml`, and `robots.txt` to the new domain.
