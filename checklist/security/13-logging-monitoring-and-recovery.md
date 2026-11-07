# 13. Logging, monitoring & recovery

**Priority:** High · **Theme:** Security · **Checks:** 12

You can't fix what you can't see, and you can't recover from what you never planned for.

- [ ] **Hide stack traces in production**: generic error to the user, detail to your logs.
- [ ] **Strip `console.log`s from production**: anyone can open dev tools and read users, tokens and API responses.
- [ ] **Remove sensitive logs**: no passwords, tokens, full card numbers or PII in logs.
- [ ] **Log security events**: logins, failed logins, password changes, permission changes.
- [ ] **Keep audit logs**: for admin and data-changing actions, so you can answer "who did this?"
- [ ] **Set up error monitoring**: Sentry or similar, so you hear about bugs before users post about them.
- [ ] **Alert on suspicious activity**: login spikes, mass data access, new admin accounts.
- [ ] **Add uptime alerts**: know your site is down before your customers do.
- [ ] **Create a status page**: one place to tell users what's broken and when it's fixed.
- [ ] **Write an incident response plan**: who gets called, how you rotate every key, how you take the app offline.
- [ ] **Know your breach-notification duties**: GDPR gives you 72 hours, and Australia's Notifiable Data Breaches scheme and US state laws have their own rules.
- [ ] **Alert on cost spikes**: cloud, AI and email bills are often the first sign of abuse.

---

Previous: [12. CI/CD, accounts & infrastructure](12-cicd-accounts-and-infrastructure.md) · [All sections](../../README.md#contents) · Next: [14. Attack your own app](14-attack-your-own-app.md)
