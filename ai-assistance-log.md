---
title: AI assistance and tool-use log
created: 2026-06-15
updated: 2026-06-15
authority: working
freshness: tentative
---

# AI Assistance And Tool-Use Log

Purpose:

Record AI-assisted screening, extraction, synthesis, repository review, and search-support steps so the review remains auditable. This log does not make AI output the final authority for inclusion, exclusion, evidence grading, or claims.

## Logging rule

Every AI-assisted step should preserve:

- date
- tool / model when known
- task
- input records or source files
- prompt or deterministic procedure
- output location
- human or deterministic check
- error handling / limitations
- final authority

## Entries

| Date | Tool / model | Task | Inputs | Procedure | Output | Human / deterministic check | Limitations | Final authority |
|---|---|---|---|---|---|---|---|---|
| 2026-06-05 | Codex, model not recorded in original seed pass | Initial project structuring and source triage | User-provided source seeds, repository snapshots, search exports | Structured notes into inventory, PRISMA records, screening log, deduplication log, and requirements layer | `source-inventory.md`, `prisma-records.md`, `prisma-screening-log.md`, `prisma-deduplication-log.md`, `systematic-review-requirements-2026.md` | Requires later source-by-source verification against primary papers/repos | Original model/version and prompts were not captured; treat early decisions as provisional | Human reviewer / future deterministic extraction |
| 2026-06-06 | Codex + local ToolUniverse run under Python 3.12 via `uv` | ToolUniverse literature search support and candidate normalization | `searches/2026-06-05/tooluniverse/*`, five ToolUniverse queries | Ran ToolUniverse search tools, normalized candidate titles/DOIs into a candidate register | `tooluniverse-candidates.md`, `search-execution-log.md` | Raw exports preserved; candidate rows still need deduplication and title/abstract screening | Semantic Scholar rate-limited after first query; preliminary tags are heuristic only | PRISMA screening decisions after human/source verification |
| 2026-06-15 | Codex | Repository/document review and methodological patching | Local markdown artifacts; web checks for selected new arXiv records | Reviewed internal consistency, added missing AI-use log, expanded extraction fields, promoted selected high-priority candidates into records/screening/matrix | `ai-assistance-log.md`, `extraction-forms.md`, `prisma-records.md`, `prisma-screening-log.md`, `review-matrix.md`, related protocol/source files | New entries are still marked tentative until full-text/code extraction is completed | Web checks were targeted, not a full rerun of all databases | Human reviewer plus full-text/code audit |

## Open checks

- Capture exact model names/versions for future AI-assisted steps whenever available.
- Store prompts or deterministic procedures for any future batch screening or extraction.
- Do not downgrade or exclude records solely from AI-generated summaries.
- Before final synthesis, verify every citation and claim against the primary source text.
