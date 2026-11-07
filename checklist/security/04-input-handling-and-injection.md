# 4. Input handling & injection

**Priority:** Ship-blocker · **Theme:** Security · **Checks:** 15

Treat every input as hostile: form fields, URLs, headers, files and AI output.

- [ ] **Validate all inputs on the server**: type, length, format and range, with Zod, Pydantic or Joi.
- [ ] **Use parameterized SQL or an ORM**: never string-concatenate queries, and test for SQL injection.
- [ ] **Sanitize user HTML**: run it through DOMPurify (or equivalent) before storing and again on render.
- [ ] **Only save the fields you expect**: block mass assignment and field tampering (`role: "admin"` in a profile update).
- [ ] **Block command injection**: never pass user input to `exec`/shell; use arg arrays.
- [ ] **Avoid insecure deserialization**: no `pickle`, `eval`, or unsafe YAML on untrusted data.
- [ ] **No open redirects**: validate `?next=` / `?redirect=` against an allow-list.
- [ ] **Protect against CSRF**: CSRF tokens, or SameSite cookies plus origin checks, on every state-changing request.
- [ ] **Block SSRF**: if the server fetches user-supplied URLs (link previews, webhooks, imports), block private IPs and `169.254.169.254` cloud metadata.
- [ ] **Block path traversal**: never build file paths from user input (`../../etc/passwd`); watch zip-slip on archive extraction.
- [ ] **Block NoSQL injection**: don't pass raw request objects into Mongo queries (`{ "$ne": null }` logs you in as anyone).
- [ ] **Block `javascript:` URLs**: in user-supplied links and rendered markdown they run code on click.
- [ ] **Avoid ReDoS**: no user input into complex regexes; set length limits first.
- [ ] **Block template injection and prototype pollution**: never render user input as a template, and don't deep-merge untrusted JSON into objects.
- [ ] **Use a crypto RNG for tokens**: `crypto.randomUUID` or `secrets`, never `Math.random()`.

---

Previous: [3. Authorization & data access](03-authorization-and-data-access.md) · [All sections](../../README.md#contents) · Next: [5. APIs & endpoints](05-apis-and-endpoints.md)
