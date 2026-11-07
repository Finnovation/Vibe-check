# 20. Mobile & real-world edge cases

**Priority:** Quality · **Theme:** Quality · **Checks:** 6

Real users on real phones do things your test run never did.

- [ ] **Handle double-tapped submit**: disable the button while submitting, and make the server idempotent.
- [ ] **Hide raw error text**: replace `TypeError: undefined is not…` with a human message.
- [ ] **Stop the keyboard covering input fields**: test on real iOS and Android devices.
- [ ] **Test both dark and light mode**: hard-coded colours break one of them.
- [ ] **Don't let the back button wipe forms**: persist drafts so user entry survives.
- [ ] **Test mobile breakpoints**: at real device widths, not just a shrunk desktop window.

---

Previous: [19. UX states & polish](19-ux-states-and-polish.md) · [All sections](../../README.md#contents) · Next: [21. Accessibility](21-accessibility.md)
