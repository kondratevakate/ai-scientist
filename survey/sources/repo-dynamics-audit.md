---
title: Repository dynamics audit
created: 2026-06-05
updated: 2026-06-05
authority: working
freshness: tentative
source_basis: GitHub API first pass, local snapshots
---

# Repository dynamics audit

Snapshot date: 2026-06-05.

Local source root:

`D:\projects\02_academia\ai-scientist\open-source`

Notes:

- GitHub `open_issues_count` includes issues and pull requests.
- Stars/forks are weak signals, but useful for adoption / attention.
- `pushed_at` is the best quick signal for whether the repository is alive.
- Four repositories hit GitHub API `403` during the first pass; local snapshots still exist and should be re-queried later or checked manually.

## High-signal active repositories

| Repo | Created | Last push | Stars | Forks | Open issues/PRs | License | Maintainer signal | Interpretation |
|---|---:|---:|---:|---:|---:|---|---|---|
| `K-Dense-AI/scientific-agent-skills` | 2025-10-19 | 2026-06-04 | 27343 | 2821 | 26 | MIT | Multiple contributors; very high public attention | Major ecosystem artifact; adoption claim needs independent validation, but usage signal is huge. |
| `SakanaAI/AI-Scientist` | 2024-08-12 | 2025-12-19 | 13894 | 1972 | 116 | NOASSERTION | Sakana authors + community contributors | Core historical system; high usage/attention, issue load large. |
| `jmiao24/Paper2Agent` | 2025-09-09 | 2026-02-10 | 2232 | 340 | 0 | MIT | Small author-led repo | Very strong attention for paper-to-agent reproducibility idea; low open issue count could mean tidy or low issue usage. |
| `microsoft/mattergen` | 2024-11-27 | 2026-02-27 | 1719 | 329 | 12 | MIT | Microsoft Research contributors | Strong big-company executable science artifact; infrastructure, not autonomous scientist. |
| `openai/mle-bench` | 2024-10-08 | 2026-04-24 | 1566 | 251 | 9 | NOASSERTION | OpenAI evals contributors | Core ML-agent benchmark; high adoption signal. |
| `mims-harvard/ToolUniverse` | 2025-03-03 | 2026-06-05 | 1423 | 218 | 15 | Apache-2.0 | Active MIMS/Harvard contributors | Very relevant biomedical tool infrastructure; alive. |
| `openai/frontier-evals` | 2025-03-28 | 2026-04-21 | 1212 | 160 | 12 | MIT | OpenAI evals contributors | Important eval harness; PaperBench/FrontierScience mapping still needs exact extraction. |
| `microsoft/bioemu` | 2024-12-17 | 2026-05-28 | 822 | 141 | 0 | MIT | Microsoft contributors | Strong model artifact; evaluator/simulation infrastructure. |
| `NVIDIA-BioNeMo/bionemo-framework` | 2023-10-16 | 2026-06-05 | 760 | 155 | 190 | blank | NVIDIA BioNeMo team | Very active platform repo; issue load high, likely mature/large framework with support burden. |
| `mims-harvard/AutoScientists` | 2026-05-21 | 2026-05-28 | 539 | 83 | 2 | blank | Single visible top contributor in first pass | New, hot, relevant; needs methods/code audit before trusting claims. |
| `Future-House/robin` | 2025-05-19 | 2026-04-21 | 497 | 79 | 5 | Apache-2.0 | FutureHouse authors | Central closed-loop discovery artifact; strong candidate for deep reproducibility audit. |

## Active benchmark / eval infrastructure

| Repo | Created | Last push | Stars | Forks | Open issues/PRs | License | Interpretation |
|---|---:|---:|---:|---:|---:|---|---|
| `Future-House/aviary` | 2024-08-27 | 2026-06-04 | 270 | 34 | 10 | Apache-2.0 | Alive; core FutureHouse environment/training stack. |
| `google-research/era` | 2025-09-09 | 2026-05-27 | 223 | 34 | 1 | Apache-2.0 | Strong Google executable-science artifact; high priority audit. |
| `OSU-NLP-Group/ScienceAgentBench` | 2024-10-02 | 2026-04-29 | 139 | 19 | 6 | MIT | Active enough; central benchmark for data-driven scientific discovery. |
| `Future-House/ldp` | 2024-09-02 | 2026-06-05 | 136 | 18 | 19 | Apache-2.0 | Active framework layer; likely used internally by FutureHouse stack. |
| `allenai/agent-baselines` | 2025-03-21 | 2026-05-22 | 142 | 16 | 1 | Apache-2.0 | Asta baseline companion; useful for reproducible evals. |
| `allenai/asta-bench` | 2025-03-21 | 2026-05-11 | 108 | 21 | 14 | Apache-2.0 | Important scientific research suite; active but still young. |
| `Future-House/BixBench` | 2025-02-19 | 2025-10-06 | 112 | 24 | 2 | Apache-2.0 | Computational biology benchmark; adoption moderate, still important. |

## Biomedical / discovery systems with lower adoption but high relevance

| Repo | Created | Last push | Stars | Forks | Open issues/PRs | License | Interpretation |
|---|---:|---:|---:|---:|---:|---|---|
| `gomesgroup/coscientist` | 2023-09-30 | 2025-08-11 | 205 | 29 | 3 | NOASSERTION | Historically important chemistry agent; likely not heavily maintained as a platform. |
| `mims-harvard/Medea` | 2025-12-11 | 2026-03-26 | 108 | 20 | 8 | Apache-2.0 | Relevant but smaller user signal; needs benchmark/data audit. |
| `aspuru-guzik-group/atlas` | 2023-06-24 | 2025-05-21 | 51 | 13 | 1 | MIT | Self-driving-lab optimizer, not LLM scientist; good methods background. |
| `mims-harvard/PROTON` | 2025-12-09 | 2025-12-27 | 28 | 14 | 0 | MIT | Low adoption signal; scientific importance depends on paper/validation. |
| `mims-harvard/ark-agent-cli` | 2026-02-03 | 2026-03-12 | 13 | 6 | 1 | MIT | Very new; probably demo/CLI artifact rather than broad platform. |

## Bibliography / list artifacts

| Repo | Created | Last push | Stars | Forks | Open issues/PRs | License | Interpretation |
|---|---:|---:|---:|---:|---:|---|---|
| `OSU-NLP-Group/awesome-agents4science` | 2024-12-03 | 2024-12-11 | 91 | 3 | 3 | MIT | Useful curated list, not code/evidence. Best used as source-discovery map. |

## Needs manual re-query

| Repo | Local status | Why unresolved |
|---|---|---|
| `SakanaAI/AI-Scientist-v2` | Local snapshot exists | GitHub API returned `403` in first pass. |
| `snap-stanford/Biomni` | Local snapshot exists | GitHub API returned `403` in first pass. |
| `TheLumos/medical-interpretability-llms` | Local snapshot exists | GitHub API returned `403` in first pass. |
| `zou-group/virtual-lab` | Local snapshot exists | GitHub API returned `403` in first pass. |

## Repository tiers

Tier A - central to systematic review:

- `Future-House/robin`
- `SakanaAI/AI-Scientist`
- `SakanaAI/AI-Scientist-v2`
- `zou-group/virtual-lab`
- `google-research/era`
- `mims-harvard/AutoScientists`
- `gomesgroup/coscientist`
- `mims-harvard/ToolUniverse`
- `snap-stanford/Biomni`
- `jmiao24/Paper2Agent`

Tier B - benchmark / evaluation backbone:

- `OSU-NLP-Group/ScienceAgentBench`
- `openai/mle-bench`
- `openai/frontier-evals`
- `allenai/asta-bench`
- `allenai/agent-baselines`
- `Future-House/BixBench`
- `Future-House/aviary`
- `Future-House/ldp`

Tier C - infrastructure / evaluator models:

- `microsoft/mattergen`
- `microsoft/mattersim`
- `microsoft/bioemu`
- `NVIDIA-BioNeMo/bionemo-framework`
- `aspuru-guzik-group/atlas`
- `TheLumos/medical-interpretability-llms`

Tier D - early / low-adoption / source-discovery:

- `mims-harvard/Medea`
- `mims-harvard/PROTON`
- `mims-harvard/ark-agent-cli`
- `OSU-NLP-Group/awesome-agents4science`

## Missing but important

From `sources/awesome-agents4science-triage.md`, these should be pulled next if scope includes benchmarks broadly:

- `allenai/discoverybench`
- `scicode-bench/SciCode`
- `behavioral-data/BLADE`
- `METR/RE-Bench`
- `snap-stanford/MLAgentBench`
- `Future-House/paper-qa`
- `snap-stanford/BioDiscoveryAgent`
- `ur-whitelab/chemcrow-public`

Still unresolved:

- Kosmos official system repo.
- Agents4Science official dataset / artifact repo.
- Andrew Cooper / Liverpool robotic chemist code trail.
- Connor Coley / MIT closed-loop chemistry code trail.
- Exact repos for CHIME, AAAR-1.0, Chemist-X, MLR-Copilot, ProtAgents, AtomAgents, TAIS, DrugAgent, ChatMOF.

## Next audit fields

For each Tier A/B repo:

- paper DOI / arXiv mapping
- license exact text and restrictions
- install path
- runnable entry points
- model/API-key requirements
- dataset requirements
- example trajectories / outputs
- benchmark reproducibility
- issue health: stale issues, maintainer replies, recent merged PRs
- release tags / package publication
- whether repository is a research snapshot or maintained platform
