---
title: PRISMA deduplication log
created: 2026-06-05
updated: 2026-06-15
authority: working
freshness: tentative
version: v0.2
---

# PRISMA deduplication log

Purpose:

Avoid counting the same system multiple times when it appears as a paper, arXiv preprint, blog post, repo, product page, and benchmark artifact.

## Deduplication rule

Primary unit of analysis:

- system/paper/repo bundle, not individual URL.

Keep separate records only when:

- the benchmark is independent from the system,
- a follow-up version changes architecture/evidence substantially,
- the source belongs to integrity/safety rather than system performance.

## Merged bundles

| Canonical record | Merged sources | Decision |
|---|---|---|
| Co-Scientist | DeepMind blog; Gemini for Science blog; Nature DOI 10.1038/s41586-026-10644-y; arXiv:2502.18864 | Treat Nature paper as primary; blogs as context; arXiv predecessor for method deltas only. |
| Robin | Nature DOI 10.1038/s41586-026-10652-y; FutureHouse announcement; `Future-House/robin`; C&EN coverage | Treat Nature + repo as primary; C&EN as secondary pointer only. |
| ERA | Nature DOI 10.1038/s41586-026-10658-6; Google Research blog; `google-research/era`; Gemini for Science blog | Treat Nature + repo as primary; product blog as context. |
| FutureHouse platform | FutureHouse platform page; Crow/Falcon/Owl/Phoenix claims; Aviary/LDP/BixBench repos | Do not merge into Robin. Platform agents are context; Aviary/LDP/BixBench are separate eval/infrastructure records. |
| Stanford Virtual Lab | Stanford Medicine article; Nature paper; `zou-group/virtual-lab` | Treat Nature + repo as primary; Stanford article as explainer. |
| Sakana AI Scientist | arXiv paper; Nature automation paper candidate; `SakanaAI/AI-Scientist`; critique paper | Keep system and critique as separate records: one performance/architecture, one quality/risk. |
| Coscientist | Nature paper; `gomesgroup/coscientist`; repeated backlog entries | One canonical core system record. |
| ToolUniverse | backlog item; `mims-harvard/ToolUniverse`; source inventory row | One infrastructure record; paper still needs extraction. |
| Biomni | backlog item; `snap-stanford/Biomni`; source inventory/code repo | One infrastructure record; paper still needs extraction. |
| Paper2Agent | backlog item; `jmiao24/Paper2Agent`; source inventory/code repo | One infrastructure record; paper still needs extraction. |
| Medea | backlog item; `mims-harvard/Medea`; source inventory row | One infrastructure record. |
| PROTON | backlog item; `mims-harvard/PROTON`; source inventory row | One infrastructure record. |
| ARK | backlog item; `mims-harvard/ark-agent-cli`; source inventory row | One infrastructure record. |
| AstaBench | backlog item; `allenai/asta-bench`; `allenai/agent-baselines` | Keep benchmark and baselines as linked but separate repo rows; one benchmark concept. |
| PaperBench | backlog item; `openai/frontier-evals`; OpenAI paper candidate | One benchmark concept; repo may include multiple evals. |
| BixBench | backlog item; `Future-House/BixBench`; FutureHouse references | One benchmark record. |
| Scientific Agent Skills | old academia repo; `open-source/scientific-agent-skills`; source inventory row | Duplicate local copy removed; canonical path is `open-source/scientific-agent-skills`. |

## Promoted records, 2026-06-15

| Canonical record | Source basis | Decision |
|---|---|---|
| Medical AI Scientist | ToolUniverse candidate TU003; arXiv:2603.28589 | New core-system record R060; not merged with generic medical LLM or Biomni records because it claims an autonomous clinical research workflow. |
| EvoScientist | ToolUniverse candidate TU012; arXiv:2603.08127 | New core-system record R061; not merged with AI Scientist/AutoScientists because its claimed novelty is persistent ideation and experimentation memory. |
| Omics AI scientist benchmark | ToolUniverse candidate TU048; arXiv:2505.08341 | New benchmark record R062; not merged with Biomni/Medea/ToolUniverse because it evaluates AI scientist performance rather than being a tool layer. |
| SoundnessBench | Targeted web verification; arXiv:2605.30329 | New benchmark record R063; not merged with PaperBench/MLE-Bench because it evaluates proposal-stage methodological soundness rather than execution/replication. |
| AI Scientists Fail Without Strong Implementation Capability | ToolUniverse candidate TU054; arXiv:2506.01372 | New integrity/critique record R064; not merged with Sakana critique because it evaluates broader implementation and verification bottlenecks. |
| Hidden Pitfalls of AI Scientist Systems | Targeted web verification; arXiv:2509.08713 | New integrity/critique record R065; companion repo still needs audit. |
| Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery | ToolUniverse candidate TU024; arXiv:2605.08956 | New integrity/critique record R066; kept separate because it is a conceptual design critique rather than empirical benchmark evidence. |

## Not merged

| Pair | Reason |
|---|---|
| Co-Scientist vs ERA | Different Google systems: hypothesis generation vs empirical scientific software generation. |
| Co-Scientist vs Gemini for Science | Gemini for Science is product umbrella; Co-Scientist is primary system. |
| Robin vs FutureHouse platform agents | Robin is a specific closed-loop discovery system; platform agents are broader product/tool context. |
| AI Scientist vs AutoScientists | Different institutions and architectures. |
| MatterGen vs MatterSim | MatterSim can serve as evaluator/simulator; MatterGen is generative materials model. |
| ToolUniverse vs Scientific Agent Skills | Both are tool/skill layers, but different ecosystems and evidence basis. |
| Agents4Science conference artifacts vs awesome-agents4science | Conference artifacts are evidence; `awesome-agents4science` is a curated bibliography. |

## Duplicates removed from active source counting

| Duplicate | Canonical record |
|---|---|
| Old `D:\projects\02_academia\scientific-agent-skills` folder | `D:\projects\02_academia\ai-scientist\open-source\scientific-agent-skills` |
| C&EN article as primary evidence for Robin/Co-Scientist | Robin and Co-Scientist Nature papers |
| Google Gemini for Science blog as primary evidence | Co-Scientist and ERA primary records |
| Company/product pages without technical methods | Appendix/context records |

## Open dedup questions

- Whether AI Scientist v2 should be a separate record or version update to AI Scientist after paper extraction.
- Whether FutureHouse platform agents should be decomposed into Crow/Falcon/Owl/Phoenix records.
- Whether PaperQA2 belongs under FutureHouse platform or standalone literature agent.
- Whether OpenAI frontier-evals contains PaperBench, FrontierScience, or multiple separable records.
