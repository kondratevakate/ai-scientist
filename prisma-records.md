---
title: PRISMA records register
created: 2026-06-05
updated: 2026-06-15
authority: working
freshness: tentative
version: v0.2
---

# PRISMA records register

This is the unified seed register for the systematic review. It merges records from:

- `source-inventory.md`
- `bibliography-backlog.md`
- `awesome-agents4science-triage.md`
- `company-article-code-blog-leads.md`
- `code-repos.md`
- `tooluniverse-candidates.md`
- targeted web verification on 2026-06-15

Status key:

- `include-core`: central AI scientist / autonomous discovery system.
- `include-benchmark`: benchmark or evaluation source.
- `include-infrastructure`: tool/model/repo infrastructure relevant to AI scientist systems.
- `include-integrity`: scientific integrity, safety, or reproducibility source.
- `appendix`: market, policy, product, or broad ecosystem context only.
- `pending`: potentially important; needs source verification.
- `exclude-core`: not eligible for core evidence, but may remain as context.

## Included core systems

| ID | Record | Source type | Current evidence | Code | Status | Reason |
|---|---|---|---|---|---|---|
| R001 | Co-Scientist | Nature paper + official blog + arXiv predecessor | Nature DOI 10.1038/s41586-026-10644-y | Not public / unclear | include-core | Central multi-agent hypothesis-generation system with biomedical validation claims. |
| R002 | Robin | Nature paper + FutureHouse repo | Nature DOI 10.1038/s41586-026-10652-y | `open-source/robin` | include-core | Strong lab-in-the-loop multi-agent discovery demonstration. |
| R003 | Stanford Virtual Lab | Nature paper + repo + Stanford article | Nature 2025, repo pulled | `open-source/virtual-lab` | include-core | Validated AI-agent lab case with SARS-CoV-2 nanobody design. |
| R004 | Sakana AI Scientist | arXiv/Nature + repo | arXiv:2408.06292 and Nature-linked source pending | `open-source/AI-Scientist` | include-core | Canonical autonomous ML research agent; high adoption and critique trail. |
| R005 | Sakana AI Scientist v2 | arXiv + repo | arXiv:2504.08066 | `open-source/AI-Scientist-v2` | include-core | Successor system using agentic tree search, VLM feedback, and parallel experiment execution; needs full reproducibility and safety audit. |
| R006 | AutoScientists | arXiv-linked repo | arXiv:2605.28655 pending full extraction | `open-source/AutoScientists` | include-core | Self-organizing agent teams for long-running scientific experimentation. |
| R007 | CMU Coscientist | Nature paper + repo | Nature DOI 10.1038/s41586-023-06792-0 | `open-source/coscientist` | include-core | Early autonomous chemical research / lab automation proof of concept. |
| R008 | Kosmos | paper/report candidate | Needs official source verification | Not found | pending | Potentially central long-horizon AI scientist; official system repo not verified. |
| R009 | BioDiscoveryAgent | arXiv + repo candidate | arXiv:2405.17631 | Not yet pulled | pending | Genetic perturbation experiment-design agent; likely core if verified. |
| R010 | AgentLaboratory | repo candidate | Needs paper/source verification | Not yet pulled | pending | End-to-end research workflow agent; not from original core list but relevant. |
| R060 | Medical AI Scientist | arXiv + project page candidate | arXiv:2603.28589 | Not yet checked | include-core | Medical-domain AI scientist framework with clinician-engineer co-reasoning, three autonomy modes, human/LLM evaluation, and executable-experiment claims. |
| R061 | EvoScientist | arXiv + repo candidate | arXiv:2603.08127 | `EvoScientist/EvoScientist` candidate, not yet pulled | include-core | Evolving multi-agent AI scientist with persistent ideation and experimentation memory; needs code, benchmark, and judge-audit extraction. |

## Included biomedical/tool systems

| ID | Record | Source type | Current evidence | Code | Status | Reason |
|---|---|---|---|---|---|---|
| R011 | ToolUniverse | paper candidate + repo | Source pending; repo active | `open-source/ToolUniverse` | include-infrastructure | Scientific tool layer for AI scientists; central biomedical infrastructure. |
| R012 | Biomni | paper candidate + repo | Source pending; repo pulled | `open-source/Biomni` | include-infrastructure | General-purpose biomedical AI agent / OS layer. |
| R013 | Paper2Agent | paper candidate + repo | Source pending; repo pulled | `open-source/Paper2Agent` | include-infrastructure | Paper-to-agent reproducibility infrastructure, high adoption signal. |
| R014 | Scientific Agent Skills | repo | Repo pulled, high adoption signal | `open-source/scientific-agent-skills` | include-infrastructure | Skill/tool library for scientific agents, not a discovery system by itself. |
| R015 | Medea | paper/repo | Repo pulled | `open-source/Medea` | include-infrastructure | Omics AI agent for therapeutic discovery; needs paper/eval audit. |
| R016 | PROTON | paper/repo | Repo pulled | `open-source/PROTON` | include-infrastructure | Graph AI neurological hypotheses with validation claims; needs full paper extraction. |
| R017 | ARK | paper/repo | Repo pulled | `open-source/ark-agent-cli` | include-infrastructure | Knowledge-graph retrieval agent; likely component infrastructure. |
| R018 | PaperQA2 | arXiv + repo candidate | arXiv:2409.13740 | Not yet pulled | pending | Strong scientific literature synthesis agent; likely benchmark/tool section. |

## Included benchmarks and evals

| ID | Record | Source type | Current evidence | Code | Status | Reason |
|---|---|---|---|---|---|---|
| R019 | ScienceAgentBench | arXiv + repo | arXiv:2410.05080 | `open-source/ScienceAgentBench` | include-benchmark | Direct scientific data-driven discovery benchmark. |
| R020 | AstaBench | paper/repo | Source pending; repo pulled | `open-source/asta-bench` | include-benchmark | Broad scientific research agent benchmark suite. |
| R021 | Asta agent baselines | repo | Repo pulled | `open-source/agent-baselines` | include-benchmark | Baseline companion for AstaBench. |
| R022 | BixBench | paper/repo | Source pending; repo pulled | `open-source/BixBench` | include-benchmark | Computational biology benchmark for LLM agents. |
| R023 | MLE-Bench | arXiv + repo | arXiv:2410.07095 | `open-source/mle-bench` | include-benchmark | ML engineering benchmark; adjacent but important. |
| R024 | PaperBench / Frontier Evals | paper/repo | Source pending; repo pulled | `open-source/frontier-evals` | include-benchmark | AI research replication/eval infrastructure. |
| R025 | Aviary | paper/repo | arXiv:2412.21154 pending | `open-source/aviary` | include-benchmark | FutureHouse environment/training stack for science agents. |
| R026 | LDP | repo | Repo pulled | `open-source/ldp` | include-benchmark | Language agent development framework; supports FutureHouse stack. |
| R027 | DiscoveryBench | arXiv + repo candidate | arXiv:2407.01725 | Not yet pulled | pending | High-priority benchmark for data-driven discovery workflows. |
| R028 | SciCode | arXiv + repo candidate | arXiv:2407.13168 | Not yet pulled | pending | Scientist-curated research coding benchmark, low contamination risk. |
| R029 | BLADE | arXiv + repo candidate | arXiv:2408.09667 | Not yet pulled | pending | Data-driven science benchmark with expert validation. |
| R030 | RE-Bench | arXiv + repo candidate | arXiv:2411.15114 | Not yet pulled | pending | Frontier AI R&D benchmark with human expert baseline. |
| R031 | MLAgentBench | arXiv + repo candidate | arXiv:2310.03302 | Not yet pulled | pending | ML experimentation agent benchmark. |
| R032 | CHIME | ACL/arXiv | arXiv:2407.16148 | Repo not found yet | pending | Biomedical literature-review organization benchmark. |
| R033 | AAAR-1.0 | arXiv | arXiv:2410.22394 | Repo not checked | pending | R&D workflow benchmark; likely relevant for review/equation/experiment tasks. |
| R062 | Omics AI scientist benchmark | arXiv | arXiv:2505.08341 | Not yet checked | include-benchmark | Benchmarking AI scientists for omics data-driven biological discovery; likely central for biomedical discovery-agent evaluation. |
| R063 | SoundnessBench | arXiv + dataset page | arXiv:2605.30329; Hugging Face dataset reported by paper | Not yet checked | include-benchmark | Benchmarks whether models can judge proposal-stage methodological soundness before execution; important for triage and false-positive risk. |

## Big-company executable science infrastructure

| ID | Record | Source type | Current evidence | Code | Status | Reason |
|---|---|---|---|---|---|---|
| R034 | Google ERA | Nature + blog + repo | Nature DOI 10.1038/s41586-026-10658-6 | `open-source/era` | include-core | Closest big-company public artifact for agentic scientific coding / computational discovery. |
| R035 | AlphaEvolve | blog + technical report | Source pending | Code partial/unclear | pending | Algorithm discovery branch; relevant but code availability unclear. |
| R036 | MatterGen | Nature + blog + repo | Nature DOI 10.1038/s41586-025-08628-5 | `open-source/mattergen` | include-infrastructure | Materials generation infrastructure, not autonomous scientist by itself. |
| R037 | MatterSim | arXiv + repo | arXiv:2405.04967 | `open-source/mattersim` | include-infrastructure | Atomistic evaluator/simulator layer for materials workflows. |
| R038 | BioEmu | Science + repo | Science DOI 10.1126/science.adv9817 | `open-source/bioemu` | include-infrastructure | Protein ensemble emulator; scientific evaluator infrastructure. |
| R039 | BioNeMo Framework | arXiv + repo + NVIDIA blog | arXiv:2411.10548 | `open-source/bionemo-framework` | include-infrastructure | Drug-discovery model framework; platform layer. |
| R040 | Meta ESM / ESMFold | papers + repo | Science/PNAS papers | Not yet pulled | pending | Protein foundation model baseline; appendix/infrastructure unless used in agents. |
| R041 | Meta OMol25 / UMA | blog + arXiv/data | Exact repo/model path pending | Not yet pulled | pending | Materials/molecular model infrastructure; not agentic by itself. |

## Integrity, safety, and interpretability

| ID | Record | Source type | Current evidence | Code | Status | Reason |
|---|---|---|---|---|---|---|
| R042 | Medical Interpretability and Knowledge Maps of LLMs | ICLR/arXiv + repo | arXiv:2510.11390 | `open-source/medical-interpretability-llms` | include-integrity | Medical trustworthiness and interpretability framework. |
| R043 | Agents4Science | conference artifacts + paper candidate | Website artifacts; Nature Biotechnology source pending | `open-source/awesome-agents4science` is only bibliography | include-integrity | Scientific communication, AI authors/reviewers, audit artifacts. |
| R044 | Sakana AI Scientist critique | paper candidate | Needs source verification | Not applicable | pending | Anti-hype quality audit for autonomous paper-writing agents. |
| R045 | Tang et al. safeguarding | arXiv | arXiv:2402.04247 | Not checked | include-integrity | Direct risk framework for LLM agents in science. |
| R046 | Messeri & Crockett illusions | Nature paper | DOI 10.1038/s41586-024-07146-0 | Not applicable | include-integrity | Important critique of AI-driven scientific monocultures / overconfidence. |
| R047 | AgentReview | EMNLP/arXiv | arXiv:2406.12708 | Not checked | pending | Peer-review dynamics simulation; useful for integrity subsection. |
| R048 | ReviewCritique | EMNLP/arXiv | arXiv:2406.16253 | Not checked | pending | AI-assisted reviewing/meta-review benchmark. |
| R064 | AI Scientists Fail Without Strong Implementation Capability | arXiv position paper | arXiv:2506.01372 | Not applicable | include-integrity | Direct critique arguing the bottleneck is implementation and verification capability, based on benchmark evidence and generated-paper evaluation. |
| R065 | Hidden Pitfalls of AI Scientist Systems | arXiv + repo candidate | arXiv:2509.08713; `niharshah/AIScientistPitfalls` candidate | Not yet pulled | include-integrity | Identifies benchmark selection, data leakage, metric misuse, and post-hoc selection bias; argues trace logs/code are needed beyond final papers. |
| R066 | Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery | arXiv position paper | arXiv:2605.08956 | Not applicable | include-integrity | Argues current agentic AI scientists are better viewed as co-scientists; emphasizes tacit lab knowledge, benchmark limits, world models, and preregistration. |

## Appendix and context

| ID | Record | Source type | Current evidence | Code | Status | Reason |
|---|---|---|---|---|---|---|
| R049 | Potato / Tater | product page | Company page | Not checked | appendix | Market/product context only until technical evidence appears. |
| R050 | Pheiron Predictions | company page | Product/claims page | Not checked | appendix | Prospective prediction market signal; needs rendered extraction and outcome validation. |
| R051 | Gemini for Science | company blog/product umbrella | Official Google blog | Not public as one repo | appendix | Product framing; primary evidence captured via Co-Scientist/ERA. |
| R052 | Anthropic Life Sciences | company/product pages | Official pages | Not checked | appendix | Enterprise assistant/connectors layer, not autonomous discovery evidence. |
| R053 | OpenAI / Retro Biosciences | company post | Official post | Not expected | appendix | Important deployment signal but not peer-reviewed core evidence yet. |
| R054 | OpenAI FrontierScience | blog/paper candidate | Source pending | Code unclear | pending | Science reasoning benchmark; include if dataset/code available. |
| R055 | Lila Sciences | market/company | Company/funding context | Not checked | appendix | Market watch only. |
| R056 | Periodic Labs | market/company | Company/funding context | Not checked | appendix | Market watch only. |
| R057 | Unreasonable Labs | market/company | Company/funding context | Not checked | appendix | Market watch only. |
| R058 | U.S. Genesis Mission | policy | EO/DOE pages pending | Not applicable | appendix | Policy/infrastructure context, not system evidence. |
| R059 | UK AI for Science Strategy | policy | UK gov/DeepMind pages pending | Not applicable | appendix | Policy context, not system evidence. |

## Exclude from core for now

| ID | Record | Source type | Current evidence | Status | Reason |
|---|---|---|---|---|---|
| X001 | Generic AI-for-science foundation model pages without agent workflow | mixed | varies | exclude-core | Keep only if linked to agent/eval loop or appendix. |
| X002 | Funding/news articles without primary technical source | news | varies | exclude-core | Use only for market/context appendix. |
| X003 | Unofficial Kosmos third-party repos | GitHub | unofficial | exclude-core | Do not treat as primary evidence. |

## v0.2 counts

| Bucket | Count |
|---|---:|
| Included core | 10 |
| Included benchmark | 10 |
| Included infrastructure | 13 |
| Included integrity | 7 |
| Appendix/context | 8 |
| Pending verification | 18 |
| Exclude-core rules | 3 |
