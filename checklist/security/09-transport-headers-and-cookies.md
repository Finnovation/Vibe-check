# 9. Transport, headers & cookies

**Priority:** High · **Theme:** Security · **Checks:** 10

Browsers enforce a lot of security for free, but only if you send the right headers and flags.

- [ ] **Enforce HTTPS everywhere**: redirect every HTTP request to HTTPS.
- [ ] **Add HSTS**: tells browsers to only ever reach your domain over HTTPS.
- [ ] **Add security headers**: CSP, `X-Content-Type-Options`, `Referrer-Policy`, `frame-ancestors`/`X-Frame-Options`, `Permissions-Policy`.
- [ ] **Set secure cookie flags**: `Secure`, `HttpOnly`, `SameSite=Lax/Strict`.
- [ ] **Keep sensitive data out of browser storage**: `localStorage`, `sessionStorage` and IndexedDB are readable by any script on the page.
- [ ] **Encrypt data in transit and at rest**: plus field-level encryption for the really sensitive stuff.
- [ ] **Use Subresource Integrity (SRI)**: on third-party scripts from CDNs, so a compromised CDN can't inject code.
- [ ] **Allow TLS 1.2+ only**: with valid certificates that auto-renew.
- [ ] **Block dotfiles on your web server**: `/.git/config`, `/.env`, `/.DS_Store` must 404.
- [ ] **Don't ship public source maps**: upload them privately to your error tracker instead.

---

Previous: [8. File uploads & storage](08-file-uploads-and-storage.md) · [All sections](../../README.md#contents) · Next: [10. Database](10-database.md)
