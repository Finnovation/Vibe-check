# 3. Authorization & data access

**Priority:** Ship-blocker · **Theme:** Security · **Checks:** 17

Logged in is not the same as allowed. Every request has to prove it can touch the data it asks for.

- [ ] **Write real row-level security (RLS) rules**: "enabled" with a `true` policy is not security. Each table: who can read, insert, update, delete.
- [ ] **Check who's admin on the server**: never from a client flag or a profile field the user can edit.
- [ ] **Put a login on the admin panel and lock admin routes**: a secret URL is not protection.
- [ ] **Remove default admin routes**: `/admin`, `/wp-admin`, framework defaults and seeded admin users are the first things bots try.
- [ ] **Don't expose internal dashboards**: DB studios, queue UIs, Grafana and Supabase/Firebase consoles stay off the public internet.
- [ ] **Test IDOR attacks**: change `/invoice/123` to `/invoice/124`. Can user A see user B's stuff?
- [ ] **Test user isolation and record access**: log in as two users and try to read or edit each other's data via the API, not just the UI.
- [ ] **Enforce tenant isolation**: in multi-tenant apps, every query is scoped to the tenant.
- [ ] **Use random IDs (UUID/ULID), not 1, 2, 3**: sequential IDs make enumeration trivial.
- [ ] **Enforce business logic server-side**: coupon reuse, negative quantities, skipping steps, free-trial farming.
- [ ] **Handle race conditions**: double-spend, double-redeem, double-submit. Use transactions, unique constraints, idempotency keys.
- [ ] **Fail closed**: if the auth/permission check errors, deny. Never `catch { allow }`.
- [ ] **Check ownership on update and delete**: not just on read. It's the classic half-done IDOR fix.
- [ ] **Lock storage rules separately**: Firebase and Supabase storage buckets have their own rules, apart from your tables.
- [ ] **Watch for RLS bypasses**: `SECURITY DEFINER` functions, views, and service-role server code all skip RLS.
- [ ] **Test vertical privilege escalation**: can a normal user hit admin-only API routes directly?
- [ ] **Take the user ID from the session**: never from the request body or query string.

---

Previous: [2. Authentication & sessions](02-authentication-and-sessions.md) · [All sections](../../README.md#contents) · Next: [4. Input handling & injection](04-input-handling-and-injection.md)
