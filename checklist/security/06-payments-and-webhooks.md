# 6. Payments & webhooks

**Priority:** Ship-blocker · **Theme:** Security · **Checks:** 9

Money flows are where business logic bugs turn into real losses.

- [ ] **Set prices server-side**: never trust an amount sent from the client.
- [ ] **Verify webhook signatures**: Stripe, GitHub and friends sign every event, so reject anything unsigned.
- [ ] **Prevent webhook replay**: check timestamps, store processed event IDs, make handlers idempotent.
- [ ] **Test the signup to paid flow**: end to end, with a real card in live mode, then refund it.
- [ ] **Show the full price up front**: no hidden fees at checkout.
- [ ] **Grant access from the webhook, not the success-page redirect**: anyone can visit `/success`.
- [ ] **Never touch raw card data**: use Stripe Checkout/Elements to stay out of PCI scope.
- [ ] **Handle the full subscription lifecycle**: failed payments, cancellations, refunds and disputes revoke access.
- [ ] **Check currency and amount on the webhook**: confirm they match what you expected before fulfilling.

---

Previous: [5. APIs & endpoints](05-apis-and-endpoints.md) · [All sections](../../README.md#contents) · Next: [7. AI & LLM features](07-ai-and-llm-features.md)
