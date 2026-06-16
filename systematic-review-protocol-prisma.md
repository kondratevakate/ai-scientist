---
title: PRISMA systematic review protocol
created: 2026-06-05
updated: 2026-06-15
authority: working
freshness: tentative
---

# PRISMA systematic review protocol

Working title:

AI Scientist Systems and Autonomous Scientific Discovery Agents: A Systematic Review of Architectures, Evidence, Benchmarks, and Reproducibility.

Quality requirements:

This protocol is governed by `systematic-review-requirements-2026.md`, which defines the 2026 standards layer for PRISMA/PRISMA-ScR reporting, source authority, risk-of-bias logic, reproducibility grading, and AI-assisted workflow disclosure.

## Review type

Systematic scoping review with PRISMA-ScR structure, plus systematic evidence extraction for systems with code or experimental validation.

Rationale:

The field is fast-moving and heterogeneous: peer-reviewed papers, arXiv preprints, benchmark repos, official lab blogs, product pages, and code snapshots. A classic clinical-intervention meta-analysis is not appropriate yet; a PRISMA-ScR style review with strict evidence grading is.

## Core research questions

1. Which AI scientist systems attempt to automate scientific research workflows?
2. Which scientific tasks are automated: literature search, hypothesis generation, experimental design, code generation, data analysis, wet-lab planning, lab execution, paper writing, peer review, or closed-loop discovery?
3. What agent architectures are used: single-agent, multi-agent, debate/tournament, recursive multi-agent, tool-library, code harness, knowledge graph, self-driving lab optimizer, or foundation-model infrastructure?
4. What evidence supports each system: benchmark scores, expert evaluation, reproducible code, prospective validation, wet-lab validation, or company claims?
5. How reproducible are the systems: code availability, data availability, installation clarity, trajectories, prompts, evaluation scripts, and license?
6. What failure modes and risks are reported: hallucinated citations, weak novelty assessment, contamination, benchmark leakage, unsafe tool use, irreproducible experiments, overclaiming autonomy, and literature pollution?

## Eligibility criteria

### Include

Sources are eligible if they satisfy at least one:

- describes an AI agent or multi-agent system for scientific research
- evaluates agents on scientific research tasks
- provides benchmark/eval infrastructure for scientific agents
- provides code/tool infrastructure explicitly intended for AI scientists
- presents validated AI-generated scientific hypotheses or experimental workflows
- analyzes risks/integrity/reproducibility of scientific agents

Evidence-bearing sources require at least one:

- peer-reviewed paper
- arXiv/bioRxiv/medRxiv technical paper
- public code repository
- official benchmark/data release
- wet-lab or prospective validation
- official lab/company technical blog pointing to primary evidence

### Exclude from core evidence

- generic LLM-for-science commentary without system/eval detail
- company product pages without methods, code, benchmark, or validation
- funding/news articles unless used only for appendix/context
- general scientific foundation models unless used inside agentic workflows or evaluation loops
- clinical decision support agents without discovery/research workflow component

### Appendix only

- market watch labs/startups
- policy/national programs
- enterprise platform pages
- foundation model infrastructure without agentic workflow

## Information sources

Databases / search surfaces:

- arXiv
- PubMed / PMC
- Semantic Scholar
- Google Scholar
- Nature / Science / Cell / PNAS / Springer / ACM / IEEE / ACL Anthology
- GitHub
- official lab/company research blogs
- benchmark leaderboards and dataset pages
- ToolUniverse literature search tools after Python 3.10+ runtime is available.

Seed repositories / bibliographies:

- `awesome-agents4science`
- `source-inventory.md`
- `bibliography-backlog.md`
- `company-article-code-blog-leads.md`
- references from Co-Scientist, Robin, Virtual Lab, AI Scientist, ScienceAgentBench, AstaBench, BixBench, MLE-Bench, PaperBench.

## Search strings

Initial search strings:

```text
("AI scientist" OR "autonomous scientist" OR "autonomous scientific discovery")
AND ("agent" OR "multi-agent" OR "language agent")
AND ("benchmark" OR "code" OR "wet-lab" OR "experimental validation")
```

```text
("LLM agent" OR "language agent")
AND ("scientific discovery" OR "hypothesis generation" OR "experiment design")
AND ("GitHub" OR "benchmark" OR "Nature" OR "arXiv")
```

```text
("self-driving lab" OR "closed-loop discovery")
AND ("large language model" OR "AI agent" OR "autonomous")
```

```text
("biomedical AI agent" OR "AI scientist")
AND ("tool" OR "database" OR "knowledge graph" OR "omics" OR "drug repurposing")
```

```text
("science agent benchmark" OR "scientific agent benchmark" OR "AI research agent benchmark")
```

Company-specific:

```text
(Google OR DeepMind OR Microsoft OR OpenAI OR Meta OR NVIDIA OR Amazon)
AND ("AI for science" OR "scientific discovery" OR "AI scientist")
AND ("GitHub" OR "Nature" OR "arXiv" OR "code")
```

## Screening process

Stage 1 - title/source screening:

- Include if the title/source clearly matches AI scientist, scientific agents, scientific benchmarks, or executable science infrastructure.
- Exclude obvious market-only pages unless they point to primary evidence.

Stage 2 - abstract/README screening:

- Extract task, domain, architecture, evidence type, and code/data availability.
- Decide core / benchmark / infrastructure / appendix.

Stage 3 - full-text/code screening:

- Read full paper or technical report.
- Inspect repository README, license, examples, datasets, and entry points.
- Record reproducibility status.

Stage 4 - quality/evidence assessment:

- Grade evidence strength and limitations.
- Separate facts, author claims, and reviewer inference.

## Data extraction fields

Bibliographic:

- title
- authors
- year
- venue
- DOI/arXiv
- source URL

System:

- system name
- institution/company/lab
- domain
- task coverage
- autonomy level
- human role
- architecture
- tools/databases
- memory/state
- code execution
- lab automation / wet-lab involvement

Evidence:

- evaluation type
- benchmark/data
- number of tasks/examples
- human baseline
- contamination controls
- prospective vs retrospective
- wet-lab validation
- reported failures
- ablations

Reproducibility:

- code URL
- license
- install status
- API keys/models
- datasets
- prompts/trajectories
- eval scripts
- compute requirements
- last repo push
- stars/forks/issues
- maintainer activity

Review judgment:

- evidence level
- reproducibility level
- autonomy level
- generality
- risk/limitations
- core vs appendix classification

## Evidence grading

Level 1 - high:

- peer-reviewed primary paper
- public code/data
- clear methods
- prospective or wet-lab validation
- reproducible examples/evals

Level 2 - moderate:

- peer-reviewed or arXiv technical paper
- code or benchmark available
- retrospective evaluations
- some methods limitations

Level 3 - limited:

- arXiv/company technical report
- partial code or partial data
- benchmark claims without full reproducibility

Level 4 - context only:

- company/product blog
- market page
- funding/news article
- opinion/prospective without technical system

## Risk of bias / quality criteria

For system papers:

- benchmark leakage / contamination risk
- cherry-picked case studies
- unclear human involvement
- no negative results
- no ablations
- no external baseline
- no code or prompts
- opaque proprietary model
- unclear novelty assessment

For benchmarks:

- ecological validity
- contamination risk
- human baseline
- task horizon
- scoring reliability
- inter-rater agreement
- dataset availability
- hidden test set availability

For repos:

- last push
- issue response health
- license restrictions
- install rot
- missing data/models
- hardcoded proprietary dependencies
- absent examples

## PRISMA flow log

Current seed state:

| Stage | Count | Notes |
|---|---:|---|
| Seed source rows in source inventory | 36 | Includes papers, blogs, repos, datasets, and 2026-06-15 additions; some rows are infrastructure/context. |
| Local source snapshots | 29 | Stored under `open-source`. |
| Unified records v0.2 | 66 | See `prisma-records.md`; includes verified, pending, appendix, and exclusion-rule records. |
| Records after initial deduplication | 63 | Three exclusion-rule rows are not counted as eligible records. See `prisma-deduplication-log.md`; newly promoted records still need formal full-text/code extraction. |
| Records excluded from core evidence | 3 rules + appendix items | Product/news/foundation-model-only sources remain context unless linked to primary evidence. |
| Records included for full-text/code review | 30 | Queue in `prisma-screening-log.md`: Tier A systems, benchmark/eval backbone, integrity sources, and 2026-06-15 promoted candidates. |
| Core systems included | 10 | Co-Scientist, Robin, Virtual Lab, AI Scientist, AI Scientist v2, AutoScientists, Coscientist, ERA, Medical AI Scientist, EvoScientist. |
| Benchmark/eval sources included | 10 | ScienceAgentBench, AstaBench, BixBench, MLE-Bench, PaperBench/frontier-evals, Aviary, LDP, Asta baselines, omics AI scientist benchmark, SoundnessBench. |
| Appendix/context sources | 8+ | Product, market, policy, and non-agentic infrastructure context. |

## Immediate next steps

1. Normalize remaining ToolUniverse candidates into PRISMA screening records and controlled include/exclude reasons.
2. Re-run arXiv, Semantic Scholar, OpenAlex, and Europe PMC with database-specific query syntax.
3. Pull missing high-priority benchmark repos from `awesome-agents4science-triage.md`.
4. Run Tier A repo audits first.
5. Fill expanded extraction forms for Robin, Co-Scientist, ERA, Virtual Lab, AI Scientist, Coscientist, Medical AI Scientist, EvoScientist, SoundnessBench, and the key critique papers.
