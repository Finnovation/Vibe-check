# 11. Dependencies & supply chain

**Priority:** High · **Theme:** Security · **Checks:** 8

Most of your code was written by strangers. Know what you're installing.

- [ ] **Check a package exists before installing**: AI hallucinates package names and attackers register them ("slopsquatting").
- [ ] **Scan dependencies for vulnerabilities**: `npm audit`, Dependabot, Snyk or `pip-audit`.
- [ ] **Watch for malicious packages**: typosquats, brand-new packages, weird install scripts.
- [ ] **Pin dependencies and commit the lockfile**: prod installs exactly what you tested.
- [ ] **Audit third-party SDKs**: what data do your analytics/chat/ads scripts collect?
- [ ] **Review `postinstall` scripts**: on new dependencies, or install with `--ignore-scripts`.
- [ ] **Update dependencies on a schedule**: Renovate or Dependabot, not once a year.
- [ ] **Remove unused dependencies**: every package is attack surface.

---

Previous: [10. Database](10-database.md) · [All sections](../../README.md#contents) · Next: [12. CI/CD, accounts & infrastructure](12-cicd-accounts-and-infrastructure.md)
