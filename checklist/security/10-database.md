# 10. Database

**Priority:** High · **Theme:** Security · **Checks:** 9

Your data is the product. Lock down who can reach it and make sure you can get it back.

- [ ] **Restrict database permissions**: the app user can't `DROP`; separate read/write roles where possible.
- [ ] **Use connection pooling**: PgBouncer, Supabase pooler or Prisma Accelerate, or serverless will exhaust your connections.
- [ ] **Back up and test restores**: a backup you've never restored is a hope, not a backup.
- [ ] **Wipe test data before launch**: fake users and orders pollute analytics and sometimes hold real emails.
- [ ] **Keep the database off the public internet**: no `0.0.0.0/0` on Postgres, Mongo, Redis or Elasticsearch. Use an IP allow-list or private network.
- [ ] **Change default credentials**: on every database, admin panel and service.
- [ ] **Encrypt backups**: and store them somewhere a compromised app can't delete them.
- [ ] **Review AI-written migrations before running them**: especially anything with `DROP`, `TRUNCATE` or `DELETE` without `WHERE`.
- [ ] **Turn on point-in-time recovery**: so you can rewind to the minute before it went wrong.

---

Previous: [9. Transport, headers & cookies](09-transport-headers-and-cookies.md) · [All sections](../../README.md#contents) · Next: [11. Dependencies & supply chain](11-dependencies-and-supply-chain.md)
