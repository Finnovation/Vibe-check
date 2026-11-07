# 0. Classic fumbles

**Priority:** Start here · **Theme:** Triage · **Checks:** 35

The mistakes that show up in vibe-coded apps again and again, each paired with its fix. If you only have ten minutes, start here.

- [ ] **Supabase `service_role` key shipped in the frontend** → Frontend uses the anon key only; service role lives server-side. Rotate it now.
- [ ] **RLS "enabled" with a `using (true)` policy** → Write per-table, per-action policies scoped to `auth.uid()`.
- [ ] **Firebase left in test mode (`allow read, write: if true`)** → Write real rules before launch. Test mode is wide open, then expires and breaks.
- [ ] **`.env` committed, then "deleted" in the next commit** → It's still in history. Rotate every key, then purge with `git filter-repo`.
- [ ] **API key in a `NEXT_PUBLIC_` / `VITE_` variable** → Move the call to a server route; rotate the key.
- [ ] **Paywall checked in the UI only (`if (user.isPro)`)** → Check the plan on the server for every paid action and API call.
- [ ] **Paid access granted on the Stripe success URL** → Grant access from the verified `checkout.session.completed` webhook.
- [ ] **Price or amount sent from the browser** → Server looks up price IDs; the client sends only the product.
- [ ] **`userId` read from the request body** → Use the user from the verified session.
- [ ] **Admin check is `email.endsWith('@mycompany.com')` on an unverified email** → Verified email + a server-side roles table.
- [ ] **Seed admin `admin / admin123` still exists** → Delete it, and the seed script's access to prod.
- [ ] **`/api/seed`, `/api/reset`, `/api/test`, `/api/debug` shipped to prod** → Delete them or gate behind env + admin auth.
- [ ] **CORS set to `*` because it "fixed the error"** → Allow-list your actual origins.
- [ ] **`dangerouslySetInnerHTML` / `v-html` / `innerHTML` on user or AI content** → Sanitize with DOMPurify, or render as text.
- [ ] **JWT secret is `secret` or copied from the tutorial** → Generate 32+ random bytes and rotate it. It logs everyone out, which is fine.
- [ ] **Rate limiter stored in memory on serverless** → Each instance has its own counter, so it does nothing. Use Redis/Upstash or your platform's limiter.
- [ ] **Open AI endpoint with no auth and no cap** → Auth + per-user quota + provider spending cap, or wake up to a $10k bill.
- [ ] **Dev and prod share one database** → Separate databases. The AI agent never gets prod credentials.
- [ ] **AI agent ran a migration / `DROP` against prod** → Backups with tested restore, PITR on, and agents only touch dev.
- [ ] **AI "fixed" failing tests by deleting or skipping them** → Review every diff to tests; CI fails on `.skip` / `.only`.
- [ ] **AI silenced errors to make the build pass (`@ts-ignore`, `eslint-disable`, `any`, empty `catch`)** → Grep for them before every release.
- [ ] **AI excluded routes from auth middleware to stop a redirect loop** → Check the middleware `matcher` and make sure protected routes are still covered.
- [ ] **AI installed a package that didn't exist yesterday** → Check age, downloads and repo before installing anything new.
- [ ] **Login says "user not found" vs "wrong password"** → One generic message, same timing.
- [ ] **`emailVerified` / `role` field writable by the user's own profile update** → Allow-list updatable fields server-side.
- [ ] **Public S3 / storage bucket "just for testing"** → Private bucket + signed URLs. Check it's actually private.
- [ ] **Uploaded SVG pops an alert box** → Sanitize SVGs or serve uploads as attachments from another domain.
- [ ] **Server fetches any URL a user pastes** → SSRF: block internal IPs and cloud metadata endpoints.
- [ ] **Password reset token in the URL leaks via `Referer` and analytics** → `Referrer-Policy: no-referrer` on reset pages; single-use, short-lived tokens.
- [ ] **Logging full request bodies, so passwords end up in logs** → Redact sensitive fields at the logger.
- [ ] **`/.git` or `/.env` reachable on the live site** → Block dotfiles at the server/CDN; make sure they're not in the deploy output.
- [ ] **Public source maps hand out your whole frontend source** → Disable in prod or upload privately to Sentry.
- [ ] **Preview deploy wired to prod DB and indexed by Google** → Preview env vars + `noindex` + password protection.
- [ ] **Domain expired / registrar account had no 2FA** → Auto-renew, registrar lock and 2FA. Lose the domain and you lose everything.
- [ ] **No backups until the day you needed one** → Automated backups and a restore you've actually tested.

---

Previous: none · [All sections](../README.md#contents) · Next: [1. Secrets & keys](security/01-secrets-and-keys.md)
