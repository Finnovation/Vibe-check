# 1. Secrets & keys

**Priority:** Ship-blocker · **Theme:** Security · **Checks:** 10

Keys leak through git history, browser bundles and copy-paste. Once a key is out, assume someone is using it.

- [ ] **Never commit `.env`**: add `.env*` to `.gitignore` *before* the first commit; ship a `.env.example` with dummy values.
- [ ] **Scan git history for secrets**: a key deleted in a later commit is still in history. Use `gitleaks` / `trufflehog`; rotate anything found.
- [ ] **Keep secret keys out of the browser**: anything in client JS (or prefixed `NEXT_PUBLIC_`, `VITE_`, `EXPO_PUBLIC_`) is public.
- [ ] **Hide API keys behind your server**: the frontend calls *your* endpoint, your server calls the third-party API.
- [ ] **Use live payment keys in production only**: test keys everywhere else, never mixed.
- [ ] **Rotate any key that's been exposed**: pasted into an AI chat, a screenshot, Discord or a public repo counts as leaked.
- [ ] **Separate keys per environment**: dev, preview and prod never share keys, DBs or OAuth apps.
- [ ] **Use a secrets manager**: Doppler, 1Password, Vault or your platform's env vars, not a shared `.env` in Slack.
- [ ] **Generate secrets properly**: 32+ random bytes from a crypto RNG. Never `secret`, `changeme` or the tutorial's example value.
- [ ] **Enable GitHub push protection**: secret scanning blocks a commit containing a key before it lands.

---

Previous: [0. Classic fumbles](../00-classic-fumbles.md) · [All sections](../../README.md#contents) · Next: [2. Authentication & sessions](02-authentication-and-sessions.md)
