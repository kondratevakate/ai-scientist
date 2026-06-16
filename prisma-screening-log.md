---
title: PRISMA screening log
created: 2026-06-05
updated: 2026-06-15
authority: working
freshness: tentative
version: v0.2
---

# PRISMA screening log

Screening date: 2026-06-05.

Reviewer: Codex + user-provided source seeds.

## Screening statuses

- `include-full-text`: move to full paper / code extraction.
- `include-code-audit`: move to repository reproducibility audit.
- `include-context`: keep for narrative/appendix only.
- `pending-search`: exact paper/repo/source still needs verification.
- `exclude-core`: not core evidence.

## Full-text / code extraction queue

| Priority | Record | Status | Include reason | Immediate extraction target |
|---:|---|---|---|---|
| 1 | Robin | include-full-text + include-code-audit | Central closed-loop lab-in-the-loop discovery system with Nature paper and repo. | supplementary materials, prompts, trajectories, eval rubrics, data-analysis scripts. |
| 2 | Co-Scientist | include-full-text | Central multi-agent hypothesis system with Nature paper. | Nature methods, arXiv predecessor, validation details, ablations. |
| 3 | ERA | include-full-text + include-code-audit | Public Google system for scientific code generation; Nature + repo. | notebooks, tree-search implementation, task datasets, reproducibility. |
| 4 | Stanford Virtual Lab | include-full-text + include-code-audit | Wet-lab validated virtual AI lab; repo exists. | Nature paper, repo examples, nanobody workflow. |
| 5 | Sakana AI Scientist | include-full-text + include-code-audit | Canonical autonomous ML research system with high adoption and critiques. | paper, repo entry points, generated papers, review loop. |
| 6 | Coscientist | include-full-text + include-code-audit | Early Nature chemistry/lab automation system. | supporting information, implementation, lab automation constraints. |
| 7 | AutoScientists | include-full-text + include-code-audit | New multi-agent self-organizing experimentation system. | arXiv:2605.28655, repo tasks, benchmark claims. |
| 8 | ToolUniverse | include-full-text + include-code-audit | Tool ecosystem for AI scientists; active repo. | paper, API/tool catalogue, examples. |
| 9 | Biomni | include-full-text + include-code-audit | Biomedical AI agent OS; local repo exists. | paper, tools/databases, reproducible examples. |
| 10 | Paper2Agent | include-full-text + include-code-audit | Paper-to-agent reproducibility concept; high adoption signal. | paper, MCP/server design, examples. |
| 11 | Medical AI Scientist | include-full-text | New medical-domain AI scientist framework surfaced by ToolUniverse and verified by arXiv page. | arXiv:2603.28589, project page, code/data availability, clinical evaluation protocol. |
| 12 | EvoScientist | include-full-text + include-code-audit | End-to-end evolving multi-agent AI scientist with persistent memory claims. | arXiv:2603.08127, repo candidate, baselines, judge prompts, trajectory/memory artifacts. |

## Benchmark extraction queue

| Priority | Record | Status | Include reason | Immediate extraction target |
|---:|---|---|---|---|
| 1 | ScienceAgentBench | include-full-text + include-code-audit | Direct benchmark for data-driven scientific discovery. | task design, contamination controls, metrics. |
| 2 | AstaBench | include-full-text + include-code-audit | Broad scientific research agent benchmark. | task taxonomy, baselines, scoring. |
| 3 | BixBench | include-full-text + include-code-audit | Computational biology benchmark. | task examples, messy data setup, agent failures. |
| 4 | MLE-Bench | include-full-text + include-code-audit | Agentic ML engineering baseline. | Kaggle adaptation, contamination risks. |
| 5 | PaperBench / frontier-evals | include-full-text + include-code-audit | AI research replication benchmark/eval harness. | exact PaperBench mapping inside repo. |
| 6 | DiscoveryBench | pending-search | Strong benchmark from awesome-agents4science; repo exists but not pulled. | pull repo, extract paper. |
| 7 | SciCode | pending-search | Scientist-curated research coding benchmark. | pull repo, extract paper. |
| 8 | BLADE | pending-search | Data-driven science report benchmark. | pull repo, extract paper. |
| 9 | RE-Bench | pending-search | Has human expert baseline and longer horizon. | pull repo, extract paper. |
| 10 | MLAgentBench | pending-search | ML experimentation agent benchmark. | pull repo, extract paper. |
| 11 | Omics AI scientist benchmark | include-full-text | Biomedical/omics-specific benchmark for AI scientist systems. | arXiv:2505.08341, task definitions, subject-matter validation, contamination controls. |
| 12 | SoundnessBench | include-full-text | Tests proposal-stage methodological soundness judgment, a missing first-gate capability for AI scientists. | arXiv:2605.30329, Hugging Face dataset, label audit, false-positive/false-negative tradeoff. |

## Integrity / risk extraction queue

| Priority | Record | Status | Include reason | Immediate extraction target |
|---:|---|---|---|---|
| 1 | Sakana critique | pending-search | Direct quality critique of autonomous research outputs. | exact paper, findings, failure taxonomy. |
| 2 | Tang et al. safeguarding | include-full-text | Direct risk framework for science agents. | risk taxonomy and safeguards. |
| 3 | Messeri & Crockett | include-full-text | Nature critique on AI illusions of understanding. | conceptual risks for review discussion. |
| 4 | Medical interpretability maps | include-full-text + include-code-audit | Medical LLM trustworthiness and interpretability. | methods, code, limitations. |
| 5 | Agents4Science | include-full-text | AI-authored/reviewed scientific communication artifacts. | dataset/artifacts, audit data, paper. |
| 6 | AI Scientists Fail Without Strong Implementation Capability | include-full-text | Direct critique of implementation and verification bottlenecks in AI scientist systems. | arXiv:2506.01372, systems evaluated, generated-paper scoring protocol. |
| 7 | Hidden Pitfalls of AI Scientist Systems | include-full-text + include-code-audit | Controlled failure-mode audit of AI scientist workflows. | arXiv:2509.08713, companion repo, trace-log/code requirements. |
| 8 | Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery | include-full-text | Direct position paper on why current systems are co-scientists rather than autonomous scientists. | arXiv:2605.08956, design recommendations, preregistration/world-model claims. |

## Appendix/context only

| Record | Status | Reason |
|---|---|---|
| Potato / Tater | include-context | Product page; no primary evidence yet. |
| Pheiron Predictions | include-context | Prospective prediction claims need rendered extraction and outcome validation. |
| Gemini for Science | include-context | Product umbrella; primary sources are Co-Scientist and ERA. |
| Anthropic Life Sciences | include-context | Enterprise assistant/connectors, not autonomous discovery evidence. |
| Microsoft MatterGen/MatterSim/BioEmu | include-context + include-code-audit | Executable science infrastructure; relevant substrate, not autonomous scientist. |
| NVIDIA BioNeMo | include-context + include-code-audit | Platform infrastructure for drug discovery. |
| Lila / Periodic / Unreasonable / Edison funding news | include-context | Market watch only. |
| U.S. Genesis Mission / UK AI for Science Strategy | include-context | Policy context only. |

## Exclusion rules applied

| Exclusion reason | Example |
|---|---|
| No technical methods, code, benchmark, or validation | Pure product/marketing pages. |
| News/funding without primary source | Funding coverage for startups. |
| Foundation model only, no agentic workflow | Generic protein/materials models unless used as evaluator/tool in a system. |
| Unofficial repo for named system | Third-party Kosmos repo candidates. |


## ToolUniverse candidate batch, 2026-06-06

Source file: `tooluniverse-candidates.md`

Status: `pending-dedup` and `pending-title-abstract`.

Batch summary:

| Source | Raw records | Notes |
|---|---:|---|
| ToolUniverse/PubMed | 37 | Successful across five queries. |
| ToolUniverse/SemanticScholar | 5 | First query only; later queries hit API 429. |
| ToolUniverse/arXiv | 25 | Successful across five queries. |
| ToolUniverse/EuropePMC | 25 | Successful across five queries. |
| Deduplicated candidate keys | 84 | Title/DOI dedup only; formal PRISMA dedup still pending. |

High-priority candidates surfaced by the batch:

| Candidate | Why screen early |
|---|---|
| Towards a Medical AI Scientist | Possible core medical-domain AI scientist framework. |
| Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery | Critical position paper directly addressing autonomy claims. |
| AI Scientists Fail Without Strong Implementation Capability | Direct critique/evaluation of current AI Scientist systems. |
| Benchmarking AI scientists for omics data driven biological discovery | Likely benchmark/evaluation source for biomedical discovery agents. |
| EvoScientist | Possible end-to-end evolving multi-agent AI scientist system. |
| PiFlow | Possible multi-agent scientific discovery framework. |
| Building MCP-native hierarchical AI scientist ecosystems | Tool/protocol infrastructure and MCP framing. |
| TeLLAgent | Tool-enhanced LLM scientific discovery framework. |
| PantheonOS | Genomics discovery agent framework. |
| Autonomous Chemistry and Materials Innovation Driven by Scientific Agents | Domain discovery/system source for chemistry/materials. |
| Polymer-Agent | Domain agent source for polymer design. |

After the 2026-06-15 promotion pass, continue matching the remaining candidates against R001-R066.

## Promoted candidate decisions, 2026-06-15

These records were promoted from the ToolUniverse candidate layer and targeted web checks into the PRISMA register. They still require full-text/code extraction.

| Candidate | New record | Decision | Reason |
|---|---|---|---|
| Towards a Medical AI Scientist | R060 | include-core | Medical-domain AI scientist framework with technical paper and reported human/LLM evaluations. |
| EvoScientist | R061 | include-core | Evolving multi-agent AI scientist with persistent memory and experiment-execution claims. |
| Benchmarking AI scientists for omics data driven biological discovery | R062 | include-benchmark | Direct biomedical/omics benchmark candidate for AI scientist evaluation. |
| SoundnessBench | R063 | include-benchmark | Addresses proposal-stage methodological soundness, a major missing capability in current AI scientist evals. |
| AI Scientists Fail Without Strong Implementation Capability | R064 | include-integrity | Direct critique of implementation and verification bottlenecks. |
| Hidden Pitfalls of AI Scientist Systems | R065 | include-integrity | Direct failure-mode audit requiring trace logs and code for evaluation. |
| Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery | R066 | include-integrity | Conceptual critique and design recommendations for autonomy claims. |

Next screening action: continue matching the remaining ToolUniverse candidates against R001-R066, then assign include/exclude reasons using `inclusion-exclusion-criteria.md`.

## Include/exclude decision fields to complete

For each record after full-text screening:

- final decision
- reason
- source URL
- paper URL
- code URL
- evidence level
- reproducibility level
- reviewer note

