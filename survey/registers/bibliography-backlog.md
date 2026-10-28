---
title: AI Scientist bibliography backlog
created: 2026-06-05
updated: 2026-06-05
authority: working
freshness: tentative
source_basis: user-provided bibliography, pending verification
---

# Bibliography backlog

This file stores candidate sources for the systematic review. Items here are not yet treated as confirmed evidence. They should be promoted into `registers/source-inventory.md` only after verification against primary papers, official lab pages, benchmark repos, or peer-reviewed / arXiv records.

## Inclusion rule

Core review sources require at least one of:

- peer-reviewed article
- arXiv / bioRxiv technical paper
- open benchmark or reproducible repository
- wet-lab / experimental validation with methods
- official lab page pointing to primary evidence

Market claims without one of these remain in `sources/appendix-labs-and-market-watch.md`.

## Core AI Scientist / autonomous discovery

| Topic / system | People / groups to track | Candidate source | Review role | Verification status |
|---|---|---|---|---|
| Sakana AI - The AI Scientist | Chris Lu, Cong Lu, Robert Tjarko Lange, Jakob Foerster, Jeff Clune, David Ha; Sakana AI, UBC, Vector, Oxford | "The AI Scientist: Towards Fully Automated Open-Ended Scientific Discovery"; Nature paper "Towards end-to-end automation of AI research" | Computational ML autonomous research: ideas, literature, code, experiments, figures, paper, simulated review | Pending |
| Sakana critique | Joeran Beel, Kan, Baumgart | "Evaluating Sakana's AI Scientist for Autonomous Research" | Critical counterweight: novelty assessment failures, coding failures, weak experiments, citation issues | Pending |
| FutureHouse / Edison Scientific - Kosmos | Sam Rodriques, Andrew D. White, Ludovico Mitchener, Michaela Hinks, Tom Rainforth, Kosmos team | "Kosmos: An AI Scientist for Autonomous Discovery" | Long-horizon research agents: literature, code, data analysis, world model, multi-agent trajectories | Pending |
| Stanford Virtual Lab | James Zou, Kyle Swanson, Wesley Wu, Nash Bulaong, John E. Pak | "The Virtual Lab of AI agents designs new SARS-CoV-2 nanobodies", Nature 2025 | Validated virtual-lab case: AI-agent lab leading to nanobody design and wet-lab validation | Pending |
| Google DeepMind Co-Scientist | Juraj Gottweis, Vivek Natarajan, Google Research / DeepMind | Nature 2026 "Accelerating scientific discovery with Co-Scientist"; Google Research / DeepMind blogs | Multi-agent hypothesis generation and ranking with biomedical validation | Partially verified in `synthesis/primary-paper-notes.md` |
| CMU Coscientist | Daniil A. Boiko, Robert MacKnight, Ben Kline, Gabe Gomes | "Autonomous chemical research with large language models", Nature 2023 | Early tool-using chemistry agent with lab automation | Pending |
| OpenAI / Retro Biosciences | OpenAI for Science, Retro Biosciences team | "Accelerating life sciences research with Retro Biosciences" | Frontier-lab deployment; GPT-4b micro and Yamanaka factor variants | Pending; not peer-reviewed by default |

## Biomedical AI agents and scientist tools

| Topic / system | People / groups to track | Candidate source | Review role | Verification status |
|---|---|---|---|---|
| ToolUniverse | Marinka Zitnik, Shanghua Gao, Richard Zhu, Pengwei Sui, Ayush Noori, Joaquin Polonuer, Lucas Vittor | "Democratizing AI scientists using ToolUniverse" | Scientific tool unification infrastructure for AI scientists | Pending |
| PROTON | Marinka Zitnik lab / HMS | "PROTON: Graph AI generates neurological hypotheses validated in molecular, organoid, and clinical systems" | AI-generated biomedical hypotheses with multi-level validation | Code located and pulled: `open-source/PROTON` |
| ARK | Marinka Zitnik lab / HMS | Agentic knowledge-graph retrieval source | Biomedical agent retrieval / KG infrastructure | Code located and pulled: `open-source/ark-agent-cli` |
| MEDEA | Marinka Zitnik lab / HMS | Omics AI agent for therapeutic discovery | Omics agent for therapeutic discovery | Code located and pulled: `open-source/Medea` |
| Biomni | Kexin Huang, Jure Leskovec, Stanford/SNAP biomedical AI ecosystem | "Biomni: A General-Purpose Biomedical AI Agent" | Biomedical agent OS: tools, databases, planning, code execution | Pending |
| Paper2Agent | Jiacheng Miao, Joe R. Davis, Jonathan K. Pritchard, James Zou | "Paper2Agent: Reimagining Research Papers As Interactive and Reliable AI Agents" | Paper-to-agent reproducibility / MCP-like interactive research artifacts | Pending |
| Anthropic life sciences | Anthropic life sciences team; Benchling, 10x Genomics, PubMed/Wiley connectors | "Claude for Life Sciences"; "Advancing Claude in healthcare and the life sciences" | Market / enterprise workflow layer for assistants and connectors | Pending; likely market/infrastructure, not core discovery evidence |

## Self-driving labs, chemistry, and materials

| Topic / system | People / groups to track | Candidate source | Review role | Verification status |
|---|---|---|---|---|
| Acceleration Consortium / self-driving lab | Alan Aspuru-Guzik, Hyun Suk Park, Mahdi Mazaheri | "Discovery of tunable and soluble organic emitters for solid-state lasers with a self-driving laboratory", Nature Communications 2026 | Real closed-loop materials discovery | Pending |
| CMU Coscientist | Gabe Gomes, Daniil Boiko, Robert MacKnight, Ben Kline | "Autonomous chemical research with large language models", Nature 2023 | Chemical automation proof of concept | Code located and pulled: `open-source/coscientist` |
| Liverpool robotic chemist / AIchemy Hub | Andrew Cooper, Liverpool Materials Innovation Factory | Cooper-specific robotic chemist / autonomous materials discovery paper trail | Self-driving lab lineage | Pending dedicated search; no central code repo verified yet |
| MIT Coley Group | Connor Coley | Closed-loop molecular design, reaction planning, lab automation, formulation workflows | Chemistry / engineering backbone for AI-scientist workflows | Pending dedicated search |
| Microsoft Research AI for Science | Microsoft Research AI for Science; MatterGen / BioEmu teams | Microsoft Discovery platform, BioEmu, MatterGen sources | Scientific foundation models / enterprise R&D platform | Pending; likely adjacent rather than autonomous-scientist core |

## Benchmarks and evals

| Benchmark | People / groups to track | Candidate source | Review role | Verification status |
|---|---|---|---|---|
| AstaBench | Jonathan Bragg, Mike D'Arcy, Nishant Balepur, Peter Clark, Doug Downey, Yoav Goldberg, Daniel Weld; Ai2/Asta | "AstaBench: Rigorous Benchmarking of AI Agents with a Scientific Research Suite" | Broad scientific research assistant benchmark | Pending |
| MLE-Bench | Jun Shern Chan, Neil Chowdhury, Oliver Jaffe, Dane Sherburn, Tejal Patwardhan, Lilian Weng, Aleksander Madry; OpenAI | "MLE-bench: Evaluating Machine Learning Agents on Machine Learning Engineering" | Agentic ML engineering benchmark; contamination concerns | Pending |
| PaperBench | Giulio Starace, Oliver Jaffe, Dane Sherburn, James Aung, Tejal Patwardhan; OpenAI | "PaperBench: Evaluating AI's Ability to Replicate AI Research" | Replication benchmark for AI research papers | Pending |
| ScienceAgentBench | Ziru Chen, Shijie Chen, Yuting Ning, Xia Ning, Yu Su, Huan Sun | "ScienceAgentBench: Toward Rigorous Assessment of Language Agents for Data-Driven Scientific Discovery" | Executable scientific workflow benchmark | Pending |
| BixBench | Ludovico Mitchener, Jon Laurent, Benjamin Tenmann, Andrew White, Samuel Rodriques; FutureHouse / ScienceMachine | "BixBench: a Comprehensive Benchmark for LLM-based Agents in Computational Biology" | Computational biology agent benchmark; messy real-world analysis | Pending |
| Agents4Science | Federico Bianchi, Owen Queen, Nitya Thakkar, Eric Sun, James Zou | Agents4Science site; Nature Biotechnology paper on AI authors/reviewers | Scientific communication experiment: AI authors and reviewers | Pending |

## Infrastructure and reproducibility

Priority sources:

- ToolUniverse
- Paper2Agent
- Biomni
- AstaBench tooling
- MLE-Bench repository
- PaperBench repository
- ScienceAgentBench repository

Working frame:

Science becomes executable: papers -> tools -> workflows -> agents -> benchmarks -> validation.

Security note:

Tool-use and MCP security should become a separate section. In AI-for-science, prompt injection and tool impersonation become high-risk once agents access lab automation, datasets, clinical records, file systems, cloud compute, or robotic APIs.

## Scientific integrity and literature pollution

| Topic | Candidate source | Review role | Verification status |
|---|---|---|---|
| Sakana AI Scientist critique | Beel et al. evaluation paper | Anti-hype quality control for autonomous papers | Pending |
| AI-authored / AI-reviewed papers | Agents4Science / Nature Biotechnology | Controlled experiment in scientific communication | Pending |
| AI-generated peer review | "Detecting AI-generated content in peer reviews" | Literature pollution / trust section | Pending |
| AI slop secondary coverage | FT / Nature-style reporting | Narrative only, not primary evidence | Pending |

## People watchlist

AI Scientist / autonomous discovery:

- David Ha
- Jeff Clune
- Chris Lu
- Cong Lu
- Sam Rodriques
- Andrew White
- James Zou
- Kyle Swanson
- Juraj Gottweis
- Vivek Natarajan
- Gabe Gomes

Biomedical agents:

- Marinka Zitnik
- Kexin Huang
- Jure Leskovec
- James Zou
- John Pak
- Ayush Noori
- Joaquin Polonuer
- Pengwei Sui

Self-driving labs / chemistry / materials:

- Alan Aspuru-Guzik
- Gabe Gomes
- Andrew Cooper
- Connor Coley
- Markus Buehler
- Ekin Dogus Cubuk
- Rafael Gomez-Bombarelli
- John Gregoire

Benchmarks / evals:

- Jonathan Bragg
- Peter Clark
- Doug Downey
- Daniel Weld
- Jun Shern Chan
- Tejal Patwardhan
- Lilian Weng
- Giulio Starace
- Ziru Chen
- Yu Su
- Huan Sun
- Ludovico Mitchener
