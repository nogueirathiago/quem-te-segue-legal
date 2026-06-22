# Legal Site

Static pages ready to host before App Store submission:

- `index.html`: legal/support landing page.
- `privacy.html`: production privacy policy page.
- `terms.html`: production terms of use page.
- `support.html`: App Store support URL page.
- `styles.css`: self-contained styling, no external scripts, no analytics, no fonts loaded from third-party CDNs.

## Deployment Options

Any static host is enough:

- GitHub Pages;
- Netlify;
- Vercel;
- Cloudflare Pages;
- any existing website under a public HTTPS domain.

The repository includes `netlify.toml`, so Netlify can publish `docs/legal-site` with no build command. The folder also includes `_headers` for static hosts that support that file.

After publishing, add the hosted URLs to App Store Connect:

- Privacy Policy URL: `https://<domain>/privacy.html`
- Support URL: `https://<domain>/support.html`

If the hosted path uses a folder, use the final public path, for example:

```text
https://<domain>/quem-te-segue/privacy.html
https://<domain>/quem-te-segue/support.html
```

Before submission, open the hosted URLs from a private browser window and from an iPhone to confirm they are public, fast, and do not require login.

After hosting, run:

```sh
PRIVACY_POLICY_URL="https://<domain>/privacy.html" \
SUPPORT_URL="https://<domain>/support.html" \
TERMS_URL="https://<domain>/terms.html" \
scripts/public_legal_url_guard.sh
```

Use `../web-publication-package.md` for provider-specific deployment steps and App Store Connect URL acceptance checks.
