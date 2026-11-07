# 8. File uploads & storage

**Priority:** High · **Theme:** Security · **Checks:** 7

A file upload is a stranger handing your server a package. Check what's inside and where it ends up.

- [ ] **Allow-list upload types**: check magic bytes, not just the extension.
- [ ] **Restrict file uploads**: size limits, rename files, store outside the web root, strip EXIF, scan if possible.
- [ ] **Lock storage buckets**: private by default, signed URLs for access, no public listing.
- [ ] **Disable directory listing**: nobody should be able to browse your upload folders.
- [ ] **Treat SVG and HTML uploads as code**: they can carry JavaScript, so sanitize them or serve with `Content-Disposition: attachment`.
- [ ] **Serve user uploads from a separate domain**: a CDN or bucket domain, so uploaded content can't read your cookies.
- [ ] **Keep signed URLs short-lived**: minutes not days, with content-type and size limits on uploads.

---

Previous: [7. AI & LLM features](07-ai-and-llm-features.md) · [All sections](../../README.md#contents) · Next: [9. Transport, headers & cookies](09-transport-headers-and-cookies.md)
