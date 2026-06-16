---
title: Systematic review requirements 2026
created: 2026-06-06
updated: 2026-06-15
authority: working
freshness: tentative
---

# Systematic Review Requirements 2026

Purpose: define the quality bar for this AI Scientist systematic scoping review, including standard evidence-synthesis requirements and additional requirements for AI-assisted review work.

This document is a working requirements layer. It does not replace the project protocol; it constrains how the protocol, screening, extraction, synthesis, and reporting should be executed.

## Source Basis

Authoritative / primary standards:

| Source | Authority | Role in this project |
|---|---|---|
| PRISMA 2020 | authoritative | Baseline reporting standard for search, selection, methods, results, flow diagram, limitations, and transparency. |
| PRISMA-ScR | authoritative | Scoping-review reporting structure; relevant because the AI Scientist field is heterogeneous and fast-moving. |
| Cochrane Handbook / MECIR | authoritative | Methodological reference for rigorous conduct, bias handling, synthesis discipline, and reporting logic. |
| JBI Manual for Evidence Synthesis | authoritative | Evidence-synthesis methods for scoping, mixed-methods, qualitative, prevalence, diagnostic, and implementation questions. |
| Campbell Collaboration Standards | authoritative | Systematic-review standards for social science, education, policy, and complex-intervention style evidence. |
| AMSTAR 2 | authoritative | Critical appraisal of methodological quality in systematic reviews and overviews. |
| ROBIS | authoritative | Risk-of-bias assessment for systematic reviews. |
| GRADE / GRADE-CERQual where applicable | authoritative | Certainty/confidence in bodies of evidence; adapt cautiously because this review is not a clinical intervention meta-analysis. |
| CDC 2026 GenAI disclosure guidance and publisher AI policies | working | AI-use disclosure, human oversight, and accountability requirements. |
| Emerging AI-assisted SLR reporting proposals, e.g. PRISMA-trAIce / CANGARU-style disclosure | working | Additional transparency items for AI-assisted screening, extraction, and synthesis. |

## Review Type Decision

Current review type:

Systematic scoping review with PRISMA-ScR structure, plus structured evidence extraction and reproducibility grading for systems, benchmarks, and repositories.

Rationale:

- The field mixes peer-reviewed papers, arXiv preprints, repositories, benchmark suites, official lab blogs, company claims, and policy/market artifacts.
- A classic intervention meta-analysis is not appropriate because outcomes, tasks, systems, domains, and evidence types are too heterogeneous.
- The review still needs systematic search, transparent screening, explicit inclusion/exclusion rules, auditable extraction, and cautious evidence grading.

## Minimum Quality Requirements

The review is not considered defensible unless all items below are satisfied or explicitly marked as unresolved limitations.

| Area | Requirement |
|---|---|
| Question | Define the review question and scope before synthesis. Keep biomedical/life-science scope decisions explicit. |
| Protocol | Maintain a dated protocol and log deviations from the protocol. |
| Search | Use multiple search surfaces: scholarly databases, preprint servers, code repositories, benchmark pages, and official lab sources. |
| Search strings | Preserve database-specific queries, dates, raw exports, and failures/timeouts. |
| Source authority | Classify sources as authoritative, working, or noisy. Do not mix product claims with peer-reviewed evidence. |
| Freshness | Classify freshness as confirmed, tentative, stale, or archived. |
| Screening | Separate title/source screening, abstract/README screening, and full-text/code screening. |
| Exclusions | Record exclusion reasons using controlled labels. |
| Deduplication | Preserve deduplication decisions and merged record IDs. |
| Extraction | Use structured extraction forms for papers and repositories. |
| Bias / quality | Assess risk of bias, benchmark leakage, cherry-picked examples, unclear human involvement, missing failures, and missing baselines. |
| Reproducibility | Grade code/data/prompts/trajectories/eval scripts, not just paper claims. |
| Synthesis | Separate facts, author claims, reviewer inference, and recommendations. |
| Limitations | Report search limitations, inaccessible sources, rate limits, failed tools, and likely coverage gaps. |
| Reporting | Produce PRISMA-style flow counts and a final checklist. |

## AI-Assisted Review Requirements

AI assistance is allowed only when it is auditable and human-verified. AI cannot be the final authority for inclusion, exclusion, risk of bias, evidence strength, or final conclusions.

For every AI-assisted step, record:

| Field | Requirement |
|---|---|
| Tool | Tool/platform name. |
| Model | Model name/version where available. |
| Date | Date of use. |
| Task | Search, deduplication, screening, extraction, summarization, coding, translation, or editing. |
| Inputs | Search query, record IDs, PDF/text source, repository path, or extraction target. |
| Prompt/procedure | Prompt or deterministic procedure used. |
| Output | Raw or summarized output location. |
| Human check | Who/what verified the output and what was checked. |
| Error handling | False inclusions, false exclusions, hallucinated citations, unsupported claims, or extraction errors. |
| Final authority | Human decision or deterministic script, never opaque AI output alone. |

Mandatory AI-use constraints:

- Do not use AI-generated references unless every citation is verified against a primary source.
- Do not exclude records solely because an AI tool marked them irrelevant.
- Do not summarize a paper into the evidence table without checking the source text.
- Do not treat LLM confidence as evidence quality.
- Do not use AI-written synthesis unless source-to-claim traceability is preserved.
- Disclose AI use in the methods section of the final review.

## Tool And Parser Inventory

Preferred tool classes for this project:

| Stage | Tools / parsers | Project requirement |
|---|---|---|
| Scholarly search | PubMed / PMC, arXiv, Semantic Scholar, OpenAlex, Europe PMC, bioRxiv / medRxiv, Google Scholar manual checks | Preserve query, date, raw export, and count. |
| Tool-mediated search | ToolUniverse literature tools when Python 3.10+ or `uvx tooluniverse` is available | Mark blocked attempts; do not report unexecuted results. |
| Metadata APIs | PubMed E-utilities, Crossref, OpenAlex, Semantic Scholar, Europe PMC | Prefer structured metadata over ad hoc scraping. |
| Citation formats | BibTeX, RIS, CSL JSON; parsers such as `bibtexparser`, `rispy`, R `revtools`, `bibliometrix` | Normalize into a single record table before screening. |
| PDF parsing | GROBID, CERMINE, PyMuPDF, pdfplumber | Use for extraction support only; verify critical claims manually. |
| Repository audit | Git metadata, README/license inspection, package manager files, tests, examples, eval scripts | Record commit hashes and local paths. |
| Screening | Rayyan, Covidence, EPPI-Reviewer, DistillerSR, ASReview, or local CSV workflow | Must support audit trail and exclusion reasons. |
| Risk / quality | AMSTAR 2 logic, ROBIS logic, benchmark-leakage checklist, reproducibility rubric | Adapt to AI-system and benchmark papers. |
| Meta-analysis | Not planned by default; use only if outcomes become comparable | Do not force quantitative pooling across heterogeneous benchmarks. |
| Reporting | PRISMA flow diagram, PRISMA checklist, extraction tables, reproducibility matrix | Counts must match screening and deduplication logs. |

## AI Scientist-Specific Quality Criteria

For each included system, assess:

| Criterion | Good evidence | Weak evidence |
|---|---|---|
| Autonomy | Clear task boundaries and human role | Vague "autonomous" claim |
| Scientific workflow coverage | Explicit steps: literature, hypothesis, experiment, code, analysis, validation | Demo-only workflow |
| Validation | Prospective, wet-lab, benchmark, or reproducible computational validation | Cherry-picked examples or screenshots |
| Baselines | Human and model/tool baselines where appropriate | No baseline |
| Contamination control | Hidden sets, temporal separation, leakage analysis, or benchmark controls | Public benchmark with no leakage analysis |
| Reproducibility | Code/data/prompts/trajectories/eval scripts available | No code or missing key artifacts |
| Error reporting | Failures, negative results, ablations, limitations | Only success cases |
| Safety | Tool-use constraints, lab/clinical boundaries, approval model, sandboxing | Unsafe or unspecified tool access |
| Claims discipline | Claims match evidence level | Product/lab claims exceed validation |

## Evidence And Reproducibility Grades

Use the existing `extraction-forms.md` levels, with this interpretation:

Evidence:

- Level 1 high: peer-reviewed primary evidence plus public artifacts plus prospective/wet-lab or strong reproducible benchmark validation.
- Level 2 moderate: technical paper plus code/benchmark plus retrospective evaluation.
- Level 3 limited: partial code, partial data, opaque methods, or non-reproducible technical claims.
- Level 4 context: company, product, news, policy, or market source without primary technical evidence.

Reproducibility:

- A runnable: installable and runnable with documented data/models/keys.
- B inspectable: source and examples present, but full run blocked by data/API/model access.
- C partial: code exists but missing prompts, trajectories, data, eval scripts, or key configuration.
- D unavailable: no public reproduction path.

## Required Project Artifacts

Before final synthesis, the project should contain:

- `systematic-review-protocol-prisma.md`
- `systematic-review-requirements-2026.md`
- `database-search-strategy.md`
- `search-execution-log.md`
- raw search exports under `searches/YYYY-MM-DD/`
- `prisma-records.md`
- `prisma-deduplication-log.md`
- `prisma-screening-log.md`
- `inclusion-exclusion-criteria.md`
- `extraction-forms.md`
- `ai-assistance-log.md`
- filled extraction tables or per-source extraction notes
- `repo-dynamics-audit.md` or equivalent repository audit table
- final PRISMA flow counts
- final limitations and AI-use disclosure section

## Current Gaps To Close

- ToolUniverse search was executed under Python 3.12 via `uv`; remaining work is normalization, deduplication, and title/abstract screening for candidates not yet promoted.
- OpenAlex query syntax needs repair.
- arXiv and Semantic Scholar need reruns with rate limits/API keys or slower query execution.
- AI-use logging now exists as `ai-assistance-log.md`; keep it updated for every future AI-assisted screening, extraction, or synthesis step.
- Final PRISMA checklist is not yet present.
- Final source-to-claim traceability table is not yet present.
- Open-source benchmark/tooling critique is tracked in `requirements-critique.md`; its required fields have been folded into `extraction-forms.md`, but filled extractions still need to use them consistently.
