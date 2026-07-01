---
title: AI Scientist systematic review
status: working
created: 2026-06-05
updated: 2026-06-15
authority: working
freshness: tentative
---

# AI Scientist systematic review

## What this repository is

This repository is a public-domain working compilation for a systematic
scoping review of AI Scientist systems: agents, benchmarks, tool ecosystems,
and reproducibility evidence for automated or AI-assisted scientific research.

It is not a software package and it is not an implementation of an AI
scientist. Use it as a structured evidence map: what systems exist, what they
claim, what evidence supports them, what code or benchmarks are available, and
where the claims are weak.

## How to use it

Start here:

1. `prisma-records.md` - canonical record register.
2. `review-matrix.md` - compact comparison of core systems and critique papers.
3. `synthesis-taxonomy.md` - how the field is grouped.
4. `extraction-forms.md` - fields to use when extracting a paper/repository.
5. `search-execution-log.md` - what searches were run and what is still missing.
6. `code-repos.md` - third-party repositories that were inspected locally, with
   provenance notes.

Suggested workflow:

1. Pick a record from `prisma-screening-log.md`.
2. Read the primary paper/repository.
3. Fill the relevant fields from `extraction-forms.md`.
4. Update `review-matrix.md` only after source verification.
5. Keep AI-assisted steps in `ai-assistance-log.md`.

Do not treat tentative rows as final evidence. Many records are still pending
full-text or code audit.

## Purpose

Build a systematic review of AI systems for automated research / AI scientist workflows, with emphasis on:

- scientific task coverage
- agent architecture and orchestration
- evidence generation and verification
- tool / skill ecosystems
- evaluation methodology
- safety, leakage, and human oversight

Success for the current phase: turn incoming resources into a clean source inventory and review matrix before distilling claims.

## Current state

The project folder is initialized. The first source batch has been logged in `source-inventory.md`. Primary notes for Co-Scientist and Robin are in `primary-paper-notes.md`; broader candidate sources are in `bibliography-backlog.md`; market/lab tracking is separated into `appendix-labs-and-market-watch.md`; cloned repositories are indexed in `code-repos.md`.

The 2026 quality and AI-assistance requirements layer is defined in `systematic-review-requirements-2026.md`. It constrains the protocol with PRISMA/PRISMA-ScR, Cochrane/JBI/Campbell, AMSTAR 2, ROBIS, GRADE-style evidence certainty, reproducibility grading, and AI-use disclosure requirements.

Update 2026-06-15: the PRISMA register is at v0.2 with 66 records. Seven high-priority sources were promoted from ToolUniverse/targeted verification into screening: Medical AI Scientist, EvoScientist, omics AI scientist benchmark, SoundnessBench, AI Scientists Fail Without Strong Implementation Capability, Hidden Pitfalls of AI Scientist Systems, and Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery. `ai-assistance-log.md` was added, and `extraction-forms.md` now includes benchmark false-negative risk, trajectory, cost, sandbox, tool-permission, and skill/tool governance fields.

## Public-domain compilation status

This folder is prepared as a CC0 public-domain compilation of original review
work. The CC0 dedication covers the project's original notes, tables,
taxonomies, screening decisions, extraction forms, and normalized metadata.

It does not cover third-party code, papers, abstracts, datasets, model weights,
logos, trademarks, raw database/API exports, or cloned repositories. For a clean
public release, publish the markdown compilation and metadata files only.
`open-source/` and `searches/` are excluded by default in `.gitignore`.

See:

- `LICENSE`
- `PUBLIC-DOMAIN-COMPILATION.md`
- `THIRD_PARTY_SOURCES.md`
- `CONTRIBUTING.md`

## Working world model

Stakeholders:

- Researcher/user: wants a systematic view of autoresearch / AI scientist tools.
- Tool builders: Potato, Google, K-Dense, AutoScientists, Pheiron.
- Scientific users: life science researchers, computational biologists, bioinformaticians, drug development teams.
- Review audience: someone deciding what AI scientist systems can actually do, how they are evaluated, and where the evidence is weak.

Initial decision axes:

- Product vs open-source system vs academic paper vs company claim.
- Literature synthesis vs hypothesis generation vs computational experimentation vs wet-lab / clinical translation.
- Centralized planner vs multi-agent self-organization vs skill-library augmentation.
- Retrospective benchmarks vs prospective validation.

Initial blockers / open loops:

- Define inclusion and exclusion criteria.
- Decide whether the review focuses only on biomedical/life-science autoresearch or broader AI-for-science agents.
- Extract peer-reviewed papers behind company announcements where possible.
- Separate vendor claims from independently validated evidence.
- Verify bibliography backlog items before promoting them into the core evidence base.
- Audit pulled code repositories for license, install path, entry points, datasets, trajectories, and reproducibility.

## Uncertainty map

- Potato and Pheiron are company/product sources: useful for market map, not enough as confirmed efficacy evidence.
- GitHub repositories are implementation artifacts: useful for architecture and reproducibility, but claims need paper/benchmark confirmation.
- Google blog is a high-signal pointer to Nature papers and product direction, but blog claims need primary-paper extraction.
- ArXiv survey is broad infrastructure context, not specific evidence for AI scientist performance.

## Next action

Promote backlog items into `source-inventory.md` only after source verification, starting with Sakana AI Scientist, Stanford Virtual Lab Nature paper, FutureHouse Kosmos, ToolUniverse/Biomni/Paper2Agent, and benchmark papers.
