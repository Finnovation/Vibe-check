# Contributing to Vibe Check

Thanks for helping. The aim is a checklist that's complete but still quick to read, so every item follows the same few rules.

## Writing an item

Every item is one line in this format:

```markdown
- [ ] **Do this thing**: why it matters, or how to do it.
```

- Start the bold part with a verb: Add, Block, Check, Use, Remove.
- Keep the reason to one sentence. Name the tools or examples that make it concrete.
- Section 0 (Classic fumbles) uses its own format: `- [ ] **The mistake** → The fix.`

## Before you add one

1. Search the repo first. Merging into an existing item beats adding a near-duplicate.
2. Put it in the section where someone would look for it, ordered roughly by importance.

## Making the change

1. Edit only the section files in `checklist/`.
2. Run `python3 scripts/build.py`. It rebuilds `CHECKLIST.md`, the issue template and the contents table in `README.md`.
3. Run `python3 scripts/build.py --check` to confirm nothing is out of date, then open a pull request.

Never edit `CHECKLIST.md` or `.github/ISSUE_TEMPLATE/launch-audit.md` by hand. They are overwritten on every build.

## Adding a new section

Create `checklist/<folder>/NN-short-name.md` with this header, then renumber the files after it:

```markdown
# NN. Section title

**Priority:** High

One sentence on why this section matters.

- [ ] **First item**: why.
```

The build script adds the theme, check count and navigation links for you.

## Licensing your contribution

By submitting a contribution, you agree that it's licensed under [CC BY 4.0](LICENSE) like the rest of the repo.
