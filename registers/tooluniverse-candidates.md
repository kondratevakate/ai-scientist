---
title: ToolUniverse candidate register
created: 2026-06-06
updated: 2026-06-15
authority: working
freshness: tentative
version: v0.2
---

# ToolUniverse candidate register

Purpose: normalized candidate layer from ToolUniverse raw exports before formal PRISMA deduplication and title/abstract screening.

Raw source folder: `searches/2026-06-05/tooluniverse/`

Unique candidate titles/DOI keys before formal deduplication: 86.

Status semantics:

- `pending-dedup`: candidate must be matched against existing R001-R066 records.
- `pending-title-abstract`: candidate must receive include/exclude reason after screening.
- `preliminary_tag` is heuristic only and is not the final PRISMA decision.

| ID | Year | Title | Preliminary tag | Sources | Queries | DOI / URL | Status |
|---|---:|---|---|---|---|---|---|
| TU001 | 2026 | What are the limits to biomedical research acceleration through general-purpose AI? | infrastructure-or-domain-agent | europepmc | tu5_self_driving_lab_agent | 10.1038/s41598-025-32583-w | pending-dedup; pending-title-abstract |
| TU002 | 2026 | Towards end-to-end automation of AI research. | core-system-or-framework | europepmc, pubmed | tu1_ai_scientist | 10.1038/s41586-026-10265-5 | pending-dedup; pending-title-abstract |
| TU003 | 2026 | Towards a Medical AI Scientist | benchmark/eval-or-critique | arxiv | tu1_ai_scientist | https://arxiv.org/abs/2603.28589v1 | promoted-to-R060; pending-full-text |
| TU004 | 2026 | TeLLAgent: a dual-agent framework for reliable scientific discovery with tool-enhanced LLMs. | benchmark/eval-or-critique | europepmc, pubmed | tu2_llm_science_agent | 10.1039/d5sc09883a | pending-dedup; pending-title-abstract |
| TU005 | 2026 | Simulon: An AI-Assisted, PyTorch-Native Framework of Molecular Dynamics and Modeling. | infrastructure-or-domain-agent | europepmc, pubmed | tu2_llm_science_agent | 10.1002/jcc.70364 | pending-dedup; pending-title-abstract |
| TU006 | 2026 | Rethinking the AI Scientist: Interactive Multi-Agent Workflows for Scientific Discovery | benchmark/eval-or-critique | semantic_scholar | tu1_ai_scientist | 10.48550/arXiv.2601.12542 | pending-dedup; pending-title-abstract |
| TU007 | 2026 | Polymer-Agent: Large Language Model Agent for Polymer Design. | infrastructure-or-domain-agent | pubmed | tu2_llm_science_agent | 10.1021/acs.jcim.6c00343 | pending-dedup; pending-title-abstract |
| TU008 | 2026 | PantheonOS: An Evolvable Multi-Agent Framework for Automatic Genomics Discovery | infrastructure-or-domain-agent | europepmc | tu2_llm_science_agent | 10.64898/2026.02.26.707870 | pending-dedup; pending-title-abstract |
| TU009 | 2026 | On-Chip modeling of drug-gut interactions in Oral drug delivery. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.1016/j.addr.2026.115864 | pending-dedup; pending-title-abstract |
| TU010 | 2026 | Multi-omics feature engineering driven by biomedical foundation models improves drug response prediction for inflammatory bowel disease patients. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.1038/s41598-026-44366-y | pending-dedup; pending-title-abstract |
| TU011 | 2026 | MetaMuse: A Multi-Agent AI System for Biomedical Metadata Curation and Harmonization | infrastructure-or-domain-agent | europepmc | tu2_llm_science_agent, tu4_science_agent_benchmark | 10.64898/2026.04.12.718044 | pending-dedup; pending-title-abstract |
| TU012 | 2026 | EvoScientist: Towards Multi-Agent Evolving AI Scientists for End-to-End Scientific Discovery | benchmark/eval-or-critique | arxiv | tu2_llm_science_agent | https://arxiv.org/abs/2603.08127v1 | promoted-to-R061; pending-full-text-code-audit |
| TU013 | 2026 | Evaluating Memory Condensation Strategies for Coding Agents in Data-Driven Scientific Discovery | benchmark/eval-or-critique | arxiv | tu4_science_agent_benchmark | https://arxiv.org/abs/2605.18854v1 | pending-dedup; pending-title-abstract |
| TU014 | 2026 | Building MCP-native hierarchical AI scientist ecosystems: a perspective on scaling multi-agent scientific discovery. | core-system-or-framework | europepmc | tu1_ai_scientist | 10.3389/frai.2026.1820375 | pending-dedup; pending-title-abstract |
| TU015 | 2026 | Bridging data and discovery: a survey on knowledge graphs in AI for science. | core-system-or-framework | europepmc | tu1_ai_scientist, tu3_biomedical_ai_agent | 10.1093/nsr/nwag140 | pending-dedup; pending-title-abstract |
| TU016 | 2026 | Beyond replacement anxiety: a psychological framework for understanding AI in natural science research. | infrastructure-or-domain-agent | europepmc | tu5_self_driving_lab_agent | 10.3389/fpsyg.2026.1824256 | pending-dedup; pending-title-abstract |
| TU017 | 2026 | Autonomous Chemistry and Materials Innovation Driven by Scientific Agents. | benchmark/eval-or-critique | pubmed | tu2_llm_science_agent | 10.1021/jacsau.6c00213 | pending-dedup; pending-title-abstract |
| TU018 | 2026 | An LLM-Based Intelligent Agent and Its Application in Making the Lanolin Saponification Process Greener | needs-manual-triage | europepmc | tu5_self_driving_lab_agent | https://europepmc.org/article/PMC/PMC12943705 | pending-dedup; pending-title-abstract |
| TU019 | 2026 | An agentic framework for autonomous scientific discovery in cancer pathology. | core-system-or-framework | europepmc | tu1_ai_scientist | 10.1038/s41591-026-04357-y | pending-dedup; pending-title-abstract |
| TU020 | 2026 | Aligned explanations in neural networks | needs-manual-triage | arxiv | tu4_science_agent_benchmark | https://arxiv.org/abs/2601.04378v3 | pending-dedup; pending-title-abstract |
| TU021 | 2026 | AI-driven CRISPR screening: optimizing gene editing through automation and intelligent decision support. | infrastructure-or-domain-agent | europepmc | tu5_self_driving_lab_agent | 10.1186/s12967-026-07849-0 | pending-dedup; pending-title-abstract |
| TU022 | 2026 | AI for scientific discovery is a social problem. | benchmark/eval-or-critique | pubmed | tu1_ai_scientist | 10.1016/j.patter.2026.101497 | pending-dedup; pending-title-abstract |
| TU023 | 2026 | AI for Scientific Discovery in Omics Data-Driven Precision Medicine. | infrastructure-or-domain-agent | europepmc | tu4_science_agent_benchmark | https://europepmc.org/article/MED/41742924 | pending-dedup; pending-title-abstract |
| TU024 | 2026 | Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery | benchmark/eval-or-critique | arxiv | tu1_ai_scientist, tu2_llm_science_agent | https://arxiv.org/abs/2605.08956v1 | promoted-to-R066; pending-full-text |
| TU025 | 2025 | Transduction is All You Need for Structured Data Workflows | needs-manual-triage | arxiv | tu4_science_agent_benchmark | https://arxiv.org/abs/2508.15610v3 | pending-dedup; pending-title-abstract |
| TU026 | 2025 | The AI Scientist-v2: Workshop-Level Automated Scientific Discovery via Agentic Tree Search | core-system-or-framework | semantic_scholar | tu1_ai_scientist | 10.48550/arXiv.2504.08066 | pending-dedup; pending-title-abstract |
| TU027 | 2025 | Spike sorting AI agent. | benchmark/eval-or-critique | pubmed | tu4_science_agent_benchmark | 10.1101/2025.02.11.637754 | pending-dedup; pending-title-abstract |
| TU028 | 2025 | Small Extracellular Vesicles Orchestrate Cisplatin-Induced Ototoxicity: Potential Biomarker and Targets Discovery. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.1002/advs.202502627 | pending-dedup; pending-title-abstract |
| TU029 | 2025 | scMOBA: A conversational single-cell Multi-Omics Brain Agent across species | infrastructure-or-domain-agent | europepmc | tu2_llm_science_agent | 10.64898/2025.12.01.691565 | pending-dedup; pending-title-abstract |
| TU030 | 2025 | SciToolAgent: a knowledge-graph-driven scientific agent for multitool integration. | benchmark/eval-or-critique | pubmed | tu4_science_agent_benchmark | 10.1038/s43588-025-00849-y | pending-dedup; pending-title-abstract |
| TU031 | 2025 | SciAgents: Automating Scientific Discovery Through Bioinspired Multi-Agent Intelligent Graph Reasoning. | infrastructure-or-domain-agent | pubmed | tu2_llm_science_agent | 10.1002/adma.202413523 | pending-dedup; pending-title-abstract |
| TU032 | 2025 | Revised model for cell cycle regulation by iron: differential roles between transferrin and ferritin. | needs-manual-triage | pubmed | tu3_biomedical_ai_agent | 10.1016/j.redox.2025.103727 | pending-dedup; pending-title-abstract |
| TU033 | 2025 | RAG-Enhanced Collaborative LLM Agents for Drug Discovery | integrity/context | arxiv | tu3_biomedical_ai_agent | https://arxiv.org/abs/2502.17506v3 | pending-dedup; pending-title-abstract |
| TU034 | 2025 | PiFlow: Principle-Aware Scientific Discovery with Multi-Agent Collaboration | benchmark/eval-or-critique | arxiv | tu2_llm_science_agent | https://arxiv.org/abs/2505.15047v4 | pending-dedup; pending-title-abstract |
| TU035 | 2025 | Pattern Recognition Algorithms in Pharmacogenomics and Drug Repurposing-Case Study: Ribavirin and Lopinavir. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.3390/ph18111649 | pending-dedup; pending-title-abstract |
| TU036 | 2025 | Mining the gaps: Deciphering Alzheimer's biology through AI-driven reconciliation. | needs-manual-triage | europepmc | tu3_biomedical_ai_agent | 10.1016/j.tjpad.2025.100402 | pending-dedup; pending-title-abstract |
| TU037 | 2025 | Large Language Model Agent: A Survey on Methodology, Applications and Challenges | benchmark/eval-or-critique | arxiv | tu5_self_driving_lab_agent | https://arxiv.org/abs/2503.21460v1 | pending-dedup; pending-title-abstract |
| TU038 | 2025 | Kosmos: An AI Scientist for Autonomous Discovery | core-system-or-framework | semantic_scholar | tu1_ai_scientist | 10.48550/arXiv.2511.02824 | pending-dedup; pending-title-abstract |
| TU039 | 2025 | Kepler: The Pioneer of Data Science and AI | needs-manual-triage | europepmc | tu4_science_agent_benchmark | 10.32388/0eeg86.2 | pending-dedup; pending-title-abstract |
| TU040 | 2025 | Kepler: The Pioneer of Data Science and AI | needs-manual-triage | europepmc | tu4_science_agent_benchmark | 10.32388/0eeg86 | pending-dedup; pending-title-abstract |
| TU041 | 2025 | Institutional Platform for Secure Self-Service Large Language Model Exploration. | infrastructure-or-domain-agent | pubmed | tu2_llm_science_agent | https://pubmed.ncbi.nlm.nih.gov/40502230/ | pending-dedup; pending-title-abstract |
| TU042 | 2025 | Human interpretable grammar encodes multicellular systems biology models to democratize virtual cell laboratories. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.1016/j.cell.2025.06.048 | pending-dedup; pending-title-abstract |
| TU043 | 2025 | Human gut microbiota-derived antimicrobials against Salmonella Typhi: diversity, mechanisms, and therapeutic potential. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.1007/s00203-025-04410-3 | pending-dedup; pending-title-abstract |
| TU044 | 2025 | How Far Are AI Scientists from Changing the World? | core-system-or-framework | arxiv | tu1_ai_scientist | https://arxiv.org/abs/2507.23276v2 | pending-dedup; pending-title-abstract |
| TU045 | 2025 | From Automation to Autonomy: A Survey on Large Language Models in Scientific Discovery | infrastructure-or-domain-agent | arxiv | tu2_llm_science_agent | https://arxiv.org/abs/2505.13259v3 | pending-dedup; pending-title-abstract |
| TU046 | 2025 | Domain Knowledge Infused Conditional Generative Models for Accelerating Drug Discovery | domain-discovery-context | arxiv | tu3_biomedical_ai_agent | https://arxiv.org/abs/2510.09837v2 | pending-dedup; pending-title-abstract |
| TU047 | 2025 | Biomni: A General-Purpose Biomedical AI Agent. | benchmark/eval-or-critique | pubmed | tu1_ai_scientist | 10.1101/2025.05.30.656746 | pending-dedup; pending-title-abstract |
| TU048 | 2025 | Benchmarking AI scientists for omics data driven biological discovery | benchmark/eval-or-critique | arxiv | tu3_biomedical_ai_agent | https://arxiv.org/abs/2505.08341v2 | promoted-to-R062; pending-full-text |
| TU049 | 2025 | Autonomous Scientific Discovery Through Hierarchical AI Scientist Systems | core-system-or-framework | europepmc | tu1_ai_scientist | 10.20944/preprints202507.1951.v1 | pending-dedup; pending-title-abstract |
| TU050 | 2025 | Autonomous Agents for Scientific Discovery: Orchestrating Scientists, Language, Code, and Physics | core-system-or-framework | arxiv | tu2_llm_science_agent | https://arxiv.org/abs/2510.09901v2 | pending-dedup; pending-title-abstract |
| TU051 | 2025 | Autonomous 'self-driving' laboratories: a review of technology and policy implications. | integrity/context | europepmc | tu5_self_driving_lab_agent | 10.1098/rsos.250646 | pending-dedup; pending-title-abstract |
| TU052 | 2025 | Automating quantum computing laboratory experiments with an agent-based AI framework. | domain-discovery-context | pubmed | tu2_llm_science_agent | 10.1016/j.patter.2025.101372 | pending-dedup; pending-title-abstract |
| TU053 | 2025 | AI-Researcher: Autonomous Scientific Innovation | benchmark/eval-or-critique | semantic_scholar | tu1_ai_scientist | 10.48550/arXiv.2505.18705 | pending-dedup; pending-title-abstract |
| TU054 | 2025 | AI Scientists Fail Without Strong Implementation Capability | benchmark/eval-or-critique | arxiv | tu1_ai_scientist | https://arxiv.org/abs/2506.01372v2 | promoted-to-R064; pending-full-text |
| TU055 | 2024 | Understanding complex crowd dynamics with generative neural simulators | domain-discovery-context | arxiv | tu4_science_agent_benchmark | https://arxiv.org/abs/2412.01491v2 | pending-dedup; pending-title-abstract |
| TU056 | 2024 | Strangeness-driven exploration in multi-agent reinforcement learning. | benchmark/eval-or-critique | pubmed | tu4_science_agent_benchmark | 10.1016/j.neunet.2024.106149 | pending-dedup; pending-title-abstract |
| TU057 | 2024 | Spatial analysis of femtosecond laser generated plasma using principal component analysis. | needs-manual-triage | europepmc | tu4_science_agent_benchmark | 10.1038/s41598-024-81389-9 | pending-dedup; pending-title-abstract |
| TU058 | 2024 | ScienceAgentBench: Toward Rigorous Assessment of Language Agents for Data-Driven Scientific Discovery | benchmark/eval-or-critique | arxiv | tu4_science_agent_benchmark | https://arxiv.org/abs/2410.05080v3 | pending-dedup; pending-title-abstract |
| TU059 | 2024 | Quantum-machine-assisted Drug Discovery | integrity/context | arxiv | tu3_biomedical_ai_agent | https://arxiv.org/abs/2408.13479v5 | pending-dedup; pending-title-abstract |
| TU060 | 2024 | PediatricsGPT: Large Language Models as Chinese Medical Assistants for Pediatric Applications | benchmark/eval-or-critique | arxiv | tu5_self_driving_lab_agent | https://arxiv.org/abs/2405.19266v4 | pending-dedup; pending-title-abstract |
| TU061 | 2024 | Learning From Failure: Integrating Negative Examples when Fine-tuning Large Language Models as Agents | infrastructure-or-domain-agent | arxiv | tu5_self_driving_lab_agent | https://arxiv.org/abs/2402.11651v2 | pending-dedup; pending-title-abstract |
| TU062 | 2024 | Integrated multi-omics analyses identify anti-viral host factors and pathways controlling SARS-CoV-2 infection. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.1038/s41467-023-44175-1 | pending-dedup; pending-title-abstract |
| TU063 | 2024 | How Evaluation Choices Distort the Outcome of Generative Drug Discovery | benchmark/eval-or-critique | arxiv | tu3_biomedical_ai_agent | https://arxiv.org/abs/2501.05457v2 | pending-dedup; pending-title-abstract |
| TU064 | 2024 | Creating and leveraging bespoke large-scale knowledge graphs for comparative genomics and multi-omics drug discovery with SocialGene | infrastructure-or-domain-agent | europepmc | tu3_biomedical_ai_agent | 10.1101/2024.08.16.608329 | pending-dedup; pending-title-abstract |
| TU065 | 2024 | "Turing Tests" For An AI Scientist | benchmark/eval-or-critique | arxiv | tu1_ai_scientist | https://arxiv.org/abs/2405.13352v1 | pending-dedup; pending-title-abstract |
| TU066 | 2023 | Scientific discovery in the age of artificial intelligence. | infrastructure-or-domain-agent | pubmed | tu1_ai_scientist | 10.1038/s41586-023-06221-2 | pending-dedup; pending-title-abstract |
| TU067 | 2023 | Protein Therapeutic Target Candidates Against <i>Acinetobacter baumannii</i>, a Pathogen of Concern to Planetary Health: A Network-Based Integrative Omics Drug Discovery Approach. | benchmark/eval-or-critique | europepmc | tu3_biomedical_ai_agent | 10.1089/omi.2022.0180 | pending-dedup; pending-title-abstract |
| TU068 | 2023 | Probiotics: insights and new opportunities for Clostridioides difficile intervention. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.1080/1040841X.2022.2072705 | pending-dedup; pending-title-abstract |
| TU069 | 2023 | PB-LLM: Partially Binarized Large Language Models | needs-manual-triage | arxiv | tu5_self_driving_lab_agent | https://arxiv.org/abs/2310.00034v2 | pending-dedup; pending-title-abstract |
| TU070 | 2023 | Hepatocytes demarcated by EphB2 contribute to the progression of nonalcoholic steatohepatitis. | infrastructure-or-domain-agent | pubmed | tu1_ai_scientist | 10.1126/scitranslmed.adc9653 | pending-dedup; pending-title-abstract |
| TU071 | 2023 | Demystifying Instruction Mixing for Fine-tuning Large Language Models | needs-manual-triage | arxiv | tu5_self_driving_lab_agent | https://arxiv.org/abs/2312.10793v3 | pending-dedup; pending-title-abstract |
| TU072 | 2023 | Computational Scientific Discovery in Psychology. | infrastructure-or-domain-agent | pubmed | tu1_ai_scientist | 10.1177/17456916221091833 | pending-dedup; pending-title-abstract |
| TU073 | 2023 | Autonomous x-ray scattering. | infrastructure-or-domain-agent | pubmed | tu1_ai_scientist | 10.1088/1361-6528/acd25a | pending-dedup; pending-title-abstract |
| TU074 | 2022 | Rethinking the Physician-Scientist Pathway. | needs-manual-triage | pubmed | tu1_ai_scientist | 10.1097/ACM.0000000000004788 | pending-dedup; pending-title-abstract |
| TU075 | 2022 | Days of Antibiotic Spectrum Coverage: A Novel Metric for Inpatient Antibiotic Consumption. | benchmark/eval-or-critique | pubmed | tu4_science_agent_benchmark | 10.1093/cid/ciab1034 | pending-dedup; pending-title-abstract |
| TU076 | 2022 | Context meta-reinforcement learning via neuromodulation. | benchmark/eval-or-critique | pubmed | tu4_science_agent_benchmark | 10.1016/j.neunet.2022.04.003 | pending-dedup; pending-title-abstract |
| TU077 | 2022 | Can we share models if sharing data is not an option? | needs-manual-triage | pubmed | tu4_science_agent_benchmark | 10.1016/j.patter.2022.100603 | pending-dedup; pending-title-abstract |
| TU078 | 2021 | PHENSIM: Phenotype Simulator. | benchmark/eval-or-critique | pubmed | tu4_science_agent_benchmark | 10.1371/journal.pcbi.1009069 | pending-dedup; pending-title-abstract |
| TU079 | 2021 | Locoregional therapies in the era of molecular and immune treatments for hepatocellular carcinoma. | benchmark/eval-or-critique | pubmed | tu4_science_agent_benchmark | 10.1038/s41575-020-00395-0 | pending-dedup; pending-title-abstract |
| TU080 | 2021 | AGA Clinical Practice Update on the Management of Refractory Helicobacter pylori Infection: Expert Review. | needs-manual-triage | pubmed | tu4_science_agent_benchmark | 10.1053/j.gastro.2020.11.059 | pending-dedup; pending-title-abstract |
| TU081 | 2020 | Harnessing big 'omics' data and AI for drug discovery in hepatocellular carcinoma. | infrastructure-or-domain-agent | pubmed | tu3_biomedical_ai_agent | 10.1038/s41575-019-0240-9 | pending-dedup; pending-title-abstract |
| TU082 | 2019 | Measuring Antimicrobial Efficacy against Biofilms: a Meta-analysis. | benchmark/eval-or-critique | pubmed | tu4_science_agent_benchmark | 10.1128/AAC.00020-19 | pending-dedup; pending-title-abstract |
| TU083 | 2019 | Lethal autonomous weapons. | needs-manual-triage | pubmed | tu1_ai_scientist | 10.1136/bmj.l1171 | pending-dedup; pending-title-abstract |
| TU084 | 2018 | Artificial Intelligence in Surgery: Promises and Perils. | needs-manual-triage | pubmed | tu1_ai_scientist | 10.1097/SLA.0000000000002693 | pending-dedup; pending-title-abstract |
| TU085 | ? | Editorial: Drug target discovery and molecular tools for parasites and hostâ€“pathogen interactions | infrastructure-or-domain-agent | europepmc | tu3_biomedical_ai_agent | https://europepmc.org/article/PMC/PMC13226105 | pending-dedup; pending-title-abstract |
| TU086 | ? | Autonomous Scientific Discovery Through Hierarchical AI Scientist Systems | core-system-or-framework | semantic_scholar | tu1_ai_scientist | https://www.semanticscholar.org/paper/87792b8fa82622033413d7d61554b2c8a9956a66 | pending-dedup; pending-title-abstract |
