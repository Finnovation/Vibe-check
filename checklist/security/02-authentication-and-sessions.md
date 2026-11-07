# 2. Authentication & sessions

**Priority:** Ship-blocker · **Theme:** Security · **Checks:** 22

Who is this user, and how sure are you? Everything here is enforced on the server.

- [ ] **Check login on the server**: hiding a button on the client is not auth. Every protected route verifies the session server-side.
- [ ] **Block unauthenticated routes by default**: deny-by-default middleware, then explicitly open public routes.
- [ ] **Hash every password**: bcrypt / argon2 / scrypt. Never plain, never MD5/SHA1.
- [ ] **Enforce password rules**: sensible minimum length, check against breached-password lists.
- [ ] **Keep tokens in `httpOnly` cookies**: not `localStorage`. JavaScript (and XSS) can't read them.
- [ ] **Secure auth sessions**: short-lived tokens, refresh rotation, server-side invalidation on logout.
- [ ] **Reset all sessions on password change**: otherwise an attacker who's already in stays in.
- [ ] **Expire password-reset links**: valid for minutes, usable once.
- [ ] **Rate limit logins and password resets**: stops brute force and email bombing.
- [ ] **Lock or throttle accounts after repeated failed logins**: slows credential stuffing to a crawl.
- [ ] **Prevent account enumeration**: "If that email exists, we've sent a link." Same response and timing for valid and invalid accounts.
- [ ] **Verify emails before granting full access**: stops fake signups and squatting on someone else's address.
- [ ] **Offer MFA, and require it for admins**: a stolen password alone shouldn't be enough.
- [ ] **Configure OAuth correctly**: exact redirect URI allow-list, `state` param, PKCE, verify the `id_token`.
- [ ] **Test password reset end to end in production**: it's the flow that breaks silently when email config changes.
- [ ] **Verify JWTs properly**: check signature, `exp`, `iss`, `aud`; reject `alg: none`; never trust a decoded-but-unverified token.
- [ ] **No sensitive data in JWT payloads**: they're base64, not encrypted.
- [ ] **Regenerate the session ID on login**: prevents session fixation.
- [ ] **Make magic links, invite links and OTPs single-use and short-lived**: a forwarded email shouldn't be a permanent key.
- [ ] **Add bot protection to signup and login**: CAPTCHA or Turnstile, and block disposable emails if abuse matters.
- [ ] **Re-authenticate for sensitive actions**: changing email, password, payout details, deleting the account.
- [ ] **Hash MFA backup codes**: single-use, and the user can regenerate them.

---

Previous: [1. Secrets & keys](01-secrets-and-keys.md) · [All sections](../../README.md#contents) · Next: [3. Authorization & data access](03-authorization-and-data-access.md)
