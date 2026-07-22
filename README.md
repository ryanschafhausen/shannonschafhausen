# Shannon Schafhausen, LPC — website

A fast, static, single-page site for a Licensed Professional Counselor in Colorado,
hosted on **GitHub Pages**. No build step, no framework — just `index.html` + `styles.css`,
so it loads instantly and is fully crawlable by search engines.

**Live at:** <https://shannonschafhausencounseling.com>

> Replaces the previous Angular app. That source has been removed from the working
> tree but remains in the git history if it's ever needed.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire page (semantic HTML, SEO meta, JSON-LD, contact form). |
| `styles.css` | All styling. Palette/variables are at the top of the file. |
| `profile.png` | Portrait photo. |
| `favicon.ico` | Browser tab icon. |
| `robots.txt`, `sitemap.xml` | Search-engine discovery. |
| `.nojekyll` | Tells GitHub Pages to serve files as-is (skip Jekyll). |

All asset paths are **relative**, so the site works both at the
`…github.io/shannonschafhausen/` URL **and** at the root of the custom domain.

## Deploying on GitHub Pages

In the repo: **Settings → Pages → Build and deployment**

- **Source:** *Deploy from a branch*
- **Branch:** `main`, folder **`/ (root)`** — the branch serving the site.

GitHub publishes within a minute or two of each push to `main`. (The old Angular
`gh-pages` branch and the temporary `static-rebuild` branch have been removed — `main`
is now the single source of truth: push to `main` and the live site updates.)

## Site content (configured)

Content and contact details are filled in and live:

- **Practitioner:** Shannon Schafhausen, LPC — Licensed Professional Counselor, Colorado.
- **Contact email:** `shannonschafhausencounseling@gmail.com`
- **Phone:** `719-387-8677`
- **Hours:** Wednesdays & Thursdays, 8 AM – 3 PM
- **Location:** Telehealth only.
- **Fees:** $120 per 60-minute session.
- **Insurance:** Not accepted.
- **Contact form:** [Web3Forms](https://web3forms.com) — the `access_key` hidden field
  in `index.html` delivers submissions to the email above. Spam protection is the
  built-in hCaptcha (`data-captcha="true"`), which uses Web3Forms' shared site key,
  so no signup or key configuration is needed. (Formspree works the same way if
  ever preferred.)

> **Privacy note:** the contact form is intentionally limited to non-sensitive
> fields and is **not** HIPAA-compliant. Keep detailed health intake on a secure,
> BAA-covered platform (most scheduling tools offer this).

## Custom domain (configured)

The site serves from **`shannonschafhausencounseling.com`** (registered via Squarespace),
with `www` redirecting to the bare domain and HTTPS enforced.

Current configuration, for reference:

- **`CNAME`** file in the repo root holds `shannonschafhausencounseling.com`.
- **GitHub:** Settings → Pages → Custom domain shows the domain, "DNS check successful",
  and **Enforce HTTPS** enabled (GitHub issues the certificate automatically).
- **Squarespace DNS:**
  - Apex (`@`): four `A` records → `185.199.108.153`, `185.199.109.153`,
    `185.199.110.153`, `185.199.111.153` (plus matching `AAAA` records for IPv6).
  - `www`: a `CNAME` record → `ryanschafhausen.github.io`.
- The absolute URLs (canonical, Open Graph, JSON-LD, `sitemap.xml`, `robots.txt`)
  all point at `https://shannonschafhausencounseling.com/`.

> **New-domain note:** brand-new domains are often blocked by corporate web filters
> for ~30 days (Newly Registered Domain rules) and may show as "uncategorized."
> This resolves on its own, or sooner by requesting categorization with the relevant
> filter vendor (Zscaler, Cisco Umbrella, Palo Alto, etc.).
