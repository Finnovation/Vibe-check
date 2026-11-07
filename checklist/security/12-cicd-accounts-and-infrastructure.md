# 12. CI/CD, accounts & infrastructure

**Priority:** High · **Theme:** Security · **Checks:** 11

Your app is only as secure as the accounts and pipelines that deploy it.

- [ ] **Lock down CI/CD secrets**: scoped per environment, with least-privilege tokens.
- [ ] **Don't run untrusted build actions**: pin GitHub Actions to a commit SHA; be wary of `pull_request_target`.
- [ ] **Pin build dependencies**: base images, actions and tool versions.
- [ ] **Review all code before production**: at least a second pass, human or a separate AI review, on every merge.
- [ ] **Put risky features behind flags**: so you can kill something without a redeploy.
- [ ] **Turn on 2FA everywhere**: GitHub, domain registrar, DNS, hosting, database, email, Stripe, AI providers.
- [ ] **Turn on registrar lock and auto-renew**: for every domain you own.
- [ ] **Kill dangling DNS**: CNAMEs pointing at deleted Vercel/Heroku/S3 apps get taken over.
- [ ] **Isolate preview deployments**: no prod data, no prod keys, and not publicly indexable.
- [ ] **Give the team least-privilege access**: and offboard people the day they leave.
- [ ] **Protect `main`**: required reviews and passing checks before merge.

---

Previous: [11. Dependencies & supply chain](11-dependencies-and-supply-chain.md) · [All sections](../../README.md#contents) · Next: [13. Logging, monitoring & recovery](13-logging-monitoring-and-recovery.md)
