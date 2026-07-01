---
title: AI Scientist source inventory
created: 2026-06-05
updated: 2026-07-01
authority: working
freshness: tentative
---

# Source inventory

## Batch 2026-06-05

| Source | Type | Authority | Freshness | Role in review | Initial notes | Follow-up |
|---|---|---:|---:|---|---|---|
| https://www.potato.ai/ | Company/product page | noisy | tentative | Market map; product workflow claims | Positions "Tater" as AI co-scientist for life-science experiment design, literature synthesis, computational tools, protocols, robot-ready scripts, analysis, reports, and iteration. | Find technical docs, case studies, papers, benchmarks, privacy/terms. |
| https://github.com/k-dense-ai/scientific-agent-skills | Open-source repository | working | tentative | Tool/skill ecosystem | Scientific Agent Skills claims 140+ skills, 100+ databases, biology/chemistry/medicine/drug-discovery coverage, compatibility with Codex/Claude Code/Cursor/Antigravity. Strong artifact for "skills as reusable scientific capability layer." | Inspect repo structure, licenses, skill quality, tests, update cadence, reproducible examples. |
| https://github.com/mims-harvard/AutoScientists | Open-source repository + linked arXiv | working | tentative | Multi-agent architecture and benchmark evidence | AutoScientists presents decentralized, self-organizing agent teams for long-running computational scientific experimentation. README reports BioML-Bench, nanoGPT, and ProteinGym gains and cites arXiv:2605.28655. | Read paper, extract tasks, baselines, ablations, compute budget, failure modes. |
| https://arxiv.org/pdf/2605.18747 | ArXiv survey paper | working | tentative | Conceptual framework | "Code as Agent Harness" frames code as executable, verifiable, stateful substrate for agents; covers planning, memory, tool use, feedback, multi-agent coordination, scientific discovery, and human oversight. | Extract taxonomy relevant to review matrix; use as framework source, not performance evidence. |
| https://blog.google/innovation-and-ai/technology/research/gemini-for-science-io-2026/ | Company research/product blog | working | tentative | Frontier lab product direction and primary-paper pointers | Google describes Gemini for Science experiments: Hypothesis Generation, Computational Discovery, Literature Insights, and Science Skills in Antigravity; points to Nature papers for ERA and Co-Scientist. | Retrieve Nature papers and technical pages; verify claims against primary literature. |
| https://www.pheiron.com/predictions | Company prediction page | noisy | tentative | Prospective evaluation / biological alpha angle | Page was not directly extractable in browser, but Pheiron public materials describe prospective clinical-readout predictions and separation of biological support from trial success probability. | Revisit page manually or through rendered browser; capture prediction examples, dates, outcomes, and methodology. |
| https://med.stanford.edu/cancer/about/news/inside-the-virtual-lab--how-ai-scientists-are-accelerating-disco.html | University news article | working | tentative | Academic lab narrative; biomedical AI scientist use case | Stanford Cancer Institute article, dated 2026-03-10, describes James Zou's "Virtual Lab": multi-agent AI scientists with PI, specialist researcher agents, and scientific critic; agents read papers, brainstorm experiments, debate, cite literature, and use "Agent School" for self-directed learning. Claims human intervention was about 1% of operations. | Find the corresponding primary paper, technical repo, benchmarks, and exact Virtual Lab evaluation tasks. |
| https://arxiv.org/pdf/2604.25917 | ArXiv preprint | working | tentative | Multi-agent systems architecture | "Recursive Multi-Agent Systems" introduces RecursiveMAS, a framework for scaling agent collaboration through recursion and latent-state transfer. Evaluates 4 collaboration patterns across 9 benchmarks spanning mathematics, science, medicine, search, and code generation; reports average +8.3% accuracy, 1.2x-2.4x speedup, and 34.6%-75.6% token reduction. | Read full paper; extract benchmark names, science/medicine tasks, baselines, code/data availability, and whether results transfer to AI-scientist workflows. |
| https://deepmind.google/blog/co-scientist-a-multi-agent-ai-partner-to-accelerate-research/ | Official research blog | working | tentative | Demis Hassabis / Google DeepMind watchlist; Co-Scientist primary pointer | Google DeepMind announced Co-Scientist on 2026-05-19 as a Gemini-based multi-agent hypothesis-generation system with generation, proximity, reflection, ranking, evolution, meta-review, and supervisor agents. It points to a Nature paper and frames the system as a research partner for life sciences and beyond. | Retrieve Nature paper DOI 10.1038/s41586-026-10644-y; extract architecture, validation tasks, lab-confirmed examples, limitations, and availability. |
| https://doi.org/10.1038/s41586-026-10644-y | Nature primary research article | authoritative | tentative | Central primary source; Google DeepMind Co-Scientist | "Accelerating scientific discovery with Co-Scientist", published 2026-05-19, presents Co-Scientist as a Gemini-based multi-agent system for structured scientific thinking and hypothesis generation. Nature abstract reports test-time compute scaling benefits and biomedical validation across drug repurposing, novel target discovery, and AMR mechanism explanation, including in vitro AML validation. | Extract full methods/supplementary materials; compare with arXiv:2502.18864. |
| https://doi.org/10.1038/s41586-026-10658-6 | Nature primary research article | authoritative | tentative | Central primary source; Google ERA / Computational Discovery | "An AI system to help scientists write expert-level empirical software", published 2026-05-19, presents Empirical Research Assistance (ERA), an LLM + tree-search system that writes scientific software to maximize quality metrics. Abstract reports results across single-cell analysis, epidemiological forecasting, geospatial analysis, neural activity prediction, numerical integration, and time-series forecasting. | Pull ERA code/experiments; compare with Computational Discovery product framing and AlphaEvolve. |
| https://research.google/blog/empirical-research-assistance-era-from-nature-publication-to-catalyzing-computational-discovery/ | Official research blog | working | tentative | Google / DeepMind science platform watch; ERA productization | Google describes ERA as an AI tool for expert-level scientific coding and says it helps build Computational Discovery, an experimental Gemini for Science tool. Blog points to Nature paper and ERA code/experiments. | Pull ERA code/experiments from linked GitHub; extract repo and manuscripts. |
| https://deepmind.google/blog/alphaevolve-impact/ | Official research blog | working | tentative | Google DeepMind AlphaEvolve watch | AlphaEvolve is framed as a Gemini-powered coding agent for designing algorithms across math, computing, genomics, grid optimization, earth science, and infrastructure. It is part of the Computational Discovery stack with ERA. | Add AlphaEvolve paper/source links; distinguish algorithm discovery from biomedical hypothesis discovery. |
| https://www.futurehouse.org/research-announcements/launching-futurehouse-platform-ai-agents | Official research/product announcement | working | tentative | FutureHouse watchlist; AI scientist platform | FutureHouse launched a public platform on 2025-05-01 with Crow, Falcon, Owl, and Phoenix. Claims benchmarked literature search/synthesis performance and science-specific agents with access to open-access papers, databases, source-quality evaluation, transparent reasoning, web UI, and API. | Pull linked benchmark papers, platform docs, and agent evals; separate literature-agent capability from closed-loop discovery claims. |
| https://www.futurehouse.org/research-announcements/aviary | Official research announcement | working | tentative | FutureHouse training/evaluation stack | FutureHouse Aviary describes environments and code for training language agents on multi-step biology tasks, linked to LAB-Bench, arXiv:2412.21154, and GitHub repos Future-House/aviary and Future-House/ldp. | Add LAB-Bench, Aviary paper, and repos to primary source queue. Extract tasks, human baselines, model baselines, and training recipe. |
| https://cen.acs.org/pharmaceuticals/drug-discovery/ai-companies-introduce-agent-based-research-tools/104/web/2026/05 | Trade/science news article | working | tentative | Cross-source pointer for FutureHouse Robin and Google tools | C&EN reports that Google DeepMind and FutureHouse published Nature 2026 studies on Co-Scientist and Robin, and that DeepMind also published Empirical Research Assistance. The article highlights Robin for hypothesis generation, experiment proposal, and results analysis for drug repurposing, while noting limits around open-access datasets and uncertainty about genuinely novel discoveries. | Retrieve Nature papers: Robin DOI 10.1038/s41586-026-10652-y and ERA DOI 10.1038/s41586-026-10658-6. |
| https://doi.org/10.1038/s41586-026-10652-y | Nature primary research article | authoritative | tentative | Central primary source; FutureHouse Robin | "A multi-agent system for automating scientific discovery", published 2026-05-19, presents Robin as a multi-agent lab-in-the-loop system for hypothesis generation, experiment proposal, data analysis, and updated hypotheses. Nature abstract reports dAMD drug-repurposing discovery with ripasudil and KL001 in vitro efficacy and ABCA1 follow-up mechanism from RNA-seq. | Extract supplementary materials, code, trajectories, ablations, rubrics, and novelty validation. |
| https://arxiv.org/pdf/2510.11390 | ICLR 2026 conference paper / arXiv | authoritative | tentative | Medical safety, interpretability, and trustworthiness context | "Medical Interpretability and Knowledge Maps of Large Language Models" studies how five open-source LLMs represent and process medical knowledge using UMAP activations, weight saliency, layer lesioning, and activation patching. It maps knowledge about patient age, symptoms, diseases, drugs, and dosages; reports that Llama3.3-70B processes much medical knowledge in earlier layers and identifies non-linear age/disease representations. Code is linked at TheLumos/medical-interpretability-llms. | Add to safety/evaluation section. Inspect code, model list, prompt set, medical-professional verification, and limitations for use in AI scientist review. |
| https://github.com/mims-harvard/Medea | GitHub repository | working | confirmed | Biomedical agent code; therapeutic discovery | Official Medea code for omics AI agent therapeutic discovery. PubMed/PMC page states code and benchmarks are available at this repository. | Audit install, tools, benchmark data, and reproducibility. |
| https://github.com/mims-harvard/PROTON | GitHub repository | working | confirmed | Graph AI / neurological hypothesis generation | Official PROTON code for graph AI hypotheses validated in molecular, organoid, and clinical systems. | Audit data/model download requirements: NeuroKG Dataverse and Hugging Face weights. |
| https://github.com/mims-harvard/ark-agent-cli | GitHub repository | working | confirmed | Knowledge-graph retrieval agent | ARK terminal-based agent CLI for autonomous knowledge graph exploration with adaptive breadth-depth retrieval. | Audit CLI, required graph/index assets, and mapping to arXiv:2601.13969. |
| https://github.com/gomesgroup/coscientist | GitHub repository | working | confirmed | Chemistry autonomous research / lab automation artifact | Supporting information and simple implementation for "Autonomous chemical research with large language models." License is Apache 2.0 with Commons Clause, restricting commercial use. | Audit simple implementation and data directories. |
| https://github.com/aspuru-guzik-group/atlas | GitHub repository | working | confirmed | Self-driving lab experiment planner | Atlas is a Bayesian optimization package intended as a brain / experiment planner for self-driving laboratories. | Audit relevance to AI-scientist systems vs classic self-driving lab optimization. |
| https://agents4science.stanford.edu/submissions.html | Conference dataset / web artifacts | working | tentative | Scientific integrity / AI-authored papers | Agents4Science provides submissions, reviews, AI reviewer scores, autonomy scores, and code audit results for 2025 conference papers. | Determine if data can be downloaded in bulk; do not treat `awesome-agents4science` as the conference dataset. |
| https://github.com/google-research/era | GitHub repository | working | confirmed | Big-company executable science infrastructure; Google ERA | Code associated with "An AI system to help scientists write expert-level empirical software." ERA combines an LLM with Flat UCB Tree Search to generate, execute, and score candidate scientific programs. | Audit notebooks, implementation, application tasks, and whether full experiments can be reproduced locally. |
| https://github.com/microsoft/mattergen | GitHub repository | working | confirmed | Big-company executable science infrastructure; materials generation | Official MatterGen implementation for property-guided inorganic materials design; repository links to Nature DOI 10.1038/s41586-025-08628-5. | Audit model/data download, examples, DFT/MatterSim dependency, license, and compute requirements. |
| https://github.com/microsoft/mattersim | GitHub repository | working | confirmed | Big-company executable science infrastructure; materials simulation | MatterSim is a deep learning atomistic model across elements, temperatures, and pressures; used as a simulation/evaluator layer in materials workflows. | Audit installation, checkpoint handling, limitations, and whether it is evaluator infrastructure rather than an autonomous scientist. |
| https://github.com/microsoft/bioemu | GitHub repository | working | confirmed | Big-company executable science infrastructure; protein ensemble emulator | BioEmu provides inference code and weights for scalable emulation of protein equilibrium ensembles; linked to Science DOI 10.1126/science.adv9817. | Audit Linux-only constraints, model weights, examples, and use as scientific evaluator/infrastructure. |
| https://github.com/NVIDIA/bionemo-framework | GitHub repository | working | confirmed | Big-company executable science infrastructure; drug-discovery model framework | BioNeMo Framework is a modular high-performance library for adapting AI models in drug discovery at scale; arXiv:2411.10548. | Audit install constraints, license, supported model families, examples, and relevance to autonomous agent workflows. |

## Batch 2026-06-15

| Source | Type | Authority | Freshness | Role in review | Initial notes | Follow-up |
|---|---|---:|---:|---|---|---|
| https://arxiv.org/abs/2603.28589 | ArXiv preprint + project page candidate | working | tentative | Core medical-domain AI scientist system | "Towards a Medical AI Scientist" presents a clinical autonomous research framework with paper-based reproduction, literature-inspired innovation, and task-driven exploration modes. Abstract reports evaluations across 171 cases, 19 clinical tasks, and 6 data modalities. | Extract clinical grounding mechanism, human evaluation protocol, code/data availability, ethics constraints, and executable-experiment evidence. |
| https://arxiv.org/abs/2603.08127 | ArXiv preprint + repo candidate | working | tentative | Core evolving multi-agent AI scientist system | "EvoScientist" proposes Researcher, Engineer, and Evolution Manager agents with persistent ideation and experimentation memory, claiming improved idea quality and code execution success. | Pull/inspect official repo candidate, extract memory artifacts, baselines, judge prompts, human-evaluation design, and leakage controls. |
| https://arxiv.org/abs/2505.08341 | ArXiv preprint | working | tentative | Biomedical/omics benchmark source | "Benchmarking AI scientists for omics data driven biological discovery" is a likely benchmark/evaluation source for biomedical AI scientist systems. | Extract task definitions, scoring, gold answers, false-negative risk, subject-matter validation, and public/hidden test status. |
| https://arxiv.org/html/2605.30329v1 | ArXiv preprint + dataset page | working | tentative | Proposal-soundness benchmark / first-gate evaluation | "SoundnessBench" tests whether models can judge methodological viability of research proposals and reports optimism bias under standard prompting. | Verify dataset, labels, contamination controls, human audit quality, and relevance to AI-scientist triage. |
| https://arxiv.org/abs/2506.01372 | ArXiv position paper | working | tentative | Critical evidence on implementation gap | "AI Scientists Fail Without Strong Implementation Capability" argues current systems are bottlenecked by implementation and verification, supported by benchmark evidence and generated-paper evaluation. | Extract systems evaluated, scoring method, benchmark evidence, and limits of generalization. |
| https://arxiv.org/abs/2509.08713 | ArXiv paper + companion repo candidate | working | tentative | Critical failure-mode audit | "The More You Automate, the Less You See" identifies benchmark selection, data leakage, metric misuse, and post-hoc selection bias in AI scientist workflows; emphasizes trace logs and code. | Pull/inspect companion repo, extract controlled experiments, systems assessed, and trace-log requirements. |
| https://arxiv.org/abs/2605.08956 | ArXiv position paper | working | tentative | Conceptual critique of autonomy claims | "Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery" argues current systems function as co-scientists and need simulation verifiers, persistent world models, and preregistration. | Use in discussion/risk section; separate conceptual claims from empirical performance evidence. |

## Batch 2026-07-01

| Source | Type | Authority | Freshness | Role in review | Initial notes | Follow-up |
|---|---|---:|---:|---|---|---|
| https://www.anthropic.com/news/claude-science-ai-workbench | Official company product announcement | working | confirmed | Anthropic scientific workbench / infrastructure context | Claude Science is described as a customizable scientific workbench that integrates research tools, compute, rich artifacts, figures, manuscripts, and reproducible outputs. It is product/infrastructure evidence, not by itself peer-reviewed evidence of autonomous scientific discovery. | Extract product architecture, availability, connectors/tools, artifact/reproducibility model, and any linked evaluation or case studies. |
| https://www.anthropic.com/news/claude-for-life-sciences | Official company product announcement | working | confirmed | Anthropic life-sciences assistant/connectors context | Claude for Life Sciences adds scientific connectors, Agent Skills, prompt-library support, and life-sciences workflows. It remains context until tied to independent benchmark, code, or primary scientific validation. | Keep linked to R052/R067; separate product claims from independently validated evidence. |

## Authority key

- authoritative: peer-reviewed article, official dataset/spec, primary benchmark with sufficient methods.
- working: implementation repo, preprint, official technical blog, reproducible artifact.
- noisy: marketing page, company claim, social post, non-methodological announcement.

## Freshness key

- confirmed: validated against primary source and date.
- tentative: initial capture; not yet fully verified.
- stale: likely outdated or superseded.
- archived: kept for history, not used for current claims.

## Early clustering

Product / applied platforms:

- Potato
- Google Gemini for Science
- Pheiron
- Stanford Virtual Lab
- Google DeepMind Co-Scientist
- Google ERA / Computational Discovery
- Google DeepMind AlphaEvolve
- FutureHouse Platform
- FutureHouse Robin
- Anthropic Claude Science / Claude for Life Sciences

Open implementation artifacts:

- Scientific Agent Skills
- AutoScientists
- FutureHouse Aviary / LDP

Conceptual / framework literature:

- Code as Agent Harness
- Recursive Multi-Agent Systems
- Medical Interpretability and Knowledge Maps of LLMs

Safety / interpretability / trustworthiness:

- Medical Interpretability and Knowledge Maps of LLMs

## Candidate review questions

1. What scientific workflows are being automated: literature review, hypothesis generation, code experimentation, wet-lab protocol generation, lab automation, clinical prediction, or peer review?
2. What architecture is used: single agent, central planner, self-organizing multi-agent system, skill library, code harness, or domain-specific predictive model?
3. What evidence supports performance claims: retrospective benchmark, prospective prediction, peer-reviewed validation, ablation, user study, case study, or vendor statement?
4. How is correctness verified: citations, executable code, tests, simulation, external databases, human review, experimental outcome, or clinical readout?
5. What are the main risks: data leakage, memorization, irreproducibility, weak benchmarks, unsafe lab actions, hallucinated citations, or overclaiming product capability?
