# 5. APIs & endpoints

**Priority:** Ship-blocker · **Theme:** Security · **Checks:** 12

Every endpoint is public the moment it's deployed, whether or not your UI links to it.

- [ ] **Rate limit every endpoint**: especially auth, signup, AI, email and anything expensive.
- [ ] **Limit request size**: body size, JSON depth and file size, so one request can't eat your server.
- [ ] **Trim API responses**: return only the fields the UI needs; never the whole user row with password hash.
- [ ] **Secure server logic**: pricing, permissions, limits live on the server, not in the bundle.
- [ ] **Lock CORS to your own domain**: no `*` with credentials.
- [ ] **Harden GraphQL**: limit query depth and complexity, disable introspection in prod, cap batching and aliases.
- [ ] **Set timeouts on every outbound call and DB query**: missing timeouts mean hung workers.
- [ ] **Inventory every endpoint**: anything forgotten (`/api/debug`, `/api/seed`) gets removed or locked.
- [ ] **Cap page sizes**: `?limit=1000000` shouldn't dump your database.
- [ ] **Protect cron and internal endpoints**: they're public URLs, so require a secret header or platform auth.
- [ ] **Disable debug mode in production**: `DEBUG=True`, `APP_DEBUG`, dev overlays and verbose ORM logging leak internals.
- [ ] **Use idempotency keys**: anything that creates money, orders or emails must survive a retry without doubling up.

---

Previous: [4. Input handling & injection](04-input-handling-and-injection.md) · [All sections](../../README.md#contents) · Next: [6. Payments & webhooks](06-payments-and-webhooks.md)
