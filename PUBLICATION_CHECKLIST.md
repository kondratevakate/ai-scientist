---
title: Public release checklist
created: 2026-06-15
updated: 2026-06-15
authority: working
freshness: tentative
---

# Public Release Checklist

Use this checklist before publishing the compilation.

## Scope

- [ ] Confirm the release is a CC0 compilation of original review work.
- [ ] Confirm `open-source/` is excluded from the public release.
- [ ] Confirm `searches/` is excluded unless raw exports have been separately
      reviewed for redistribution rights.
- [ ] Confirm no PDFs, screenshots, model weights, datasets, or copied paper
      text are included.
- [ ] Confirm substantial third-party text is summarized and linked, not copied.

## Files To Include

- [ ] `README.md`
- [ ] `LICENSE`
- [ ] `PUBLIC-DOMAIN-COMPILATION.md`
- [ ] `THIRD_PARTY_SOURCES.md`
- [ ] `CONTRIBUTING.md`
- [ ] `.gitignore`
- [ ] project markdown registers, logs, protocols, matrices, and taxonomies

## Metadata Checks

- [ ] Every promoted source has a URL or identifier.
- [ ] Tentative claims are marked tentative.
- [ ] Vendor/product claims are separated from primary evidence.
- [ ] AI-assisted steps are logged in `ai-assistance-log.md`.
- [ ] Third-party repositories are represented by URL/commit metadata rather
      than included snapshots.

## Suggested Local Commands

```powershell
git init
git status --short
git add .
git status --short
```

Before committing, verify that `open-source/` and `searches/` do not appear in
the staged file list.
