---
title: Company article-code-blog leads
created: 2026-06-05
updated: 2026-06-05
authority: working
freshness: tentative
---

# Company article-code-blog leads

Search frame:

Find sources where a large company or large research lab has at least two of:

- official blog / product or research announcement
- peer-reviewed or arXiv paper
- public code / dataset / benchmark repository

Promote to `source-inventory.md` only after checking the paper, code, license, and relevance to AI scientist / autonomous discovery.

## High-confidence triplets

| Company / lab | System | Blog / announcement | Paper | Code / data | Review role | Status |
|---|---|---|---|---|---|---|
| Google Research / DeepMind | ERA / Empirical Research Assistance | https://research.google/blog/empirical-research-assistance-era-from-nature-publication-to-catalyzing-computational-discovery/ | Nature DOI 10.1038/s41586-026-10658-6; arXiv:2509.06503 | https://github.com/google-research/era | Scientific coding / computational discovery | Pull next |
| Google DeepMind | AlphaEvolve | https://deepmind.google/blog/alphaevolve-a-gemini-powered-coding-agent-for-designing-advanced-algorithms/ | White paper / technical report | Google Colab results linked from blog; full code unclear | Algorithm discovery via evolutionary coding agent | Evidence strong, code partial |
| Microsoft Research AI for Science | MatterGen | https://www.microsoft.com/en-us/research/blog/mattergen-a-new-paradigm-of-materials-design-with-generative-ai/ | Nature DOI 10.1038/s41586-025-08628-5 | https://github.com/microsoft/mattergen | Generative materials design | Pull candidate |
| Microsoft Research AI for Science | MatterSim | Microsoft AI4Science materials pages / MatterGen blog context | arXiv:2405.04967 | https://github.com/microsoft/mattersim | Atomistic simulation / evaluator layer for materials discovery | Pull candidate |
| Microsoft Research AI for Science | BioEmu | https://www.microsoft.com/en-us/research/project/biomolecules/ | Science DOI 10.1126/science.adv9817 | https://github.com/microsoft/bioemu | Protein ensemble emulator | Pull candidate |
| Meta FAIR | ESM / ESMFold / ESM Atlas | Meta AI protein releases / ESM Atlas pages | Science DOI 10.1126/science.ade2574; PNAS DOI 10.1073/pnas.2016239118 | https://github.com/facebookresearch/esm | Protein foundation model baseline, not agentic | Pull candidate if broadening to foundation models |
| Meta FAIR | OMol25 / UMA | https://ai.meta.com/blog/meta-fair-science-new-open-source-releases/ | arXiv:2505.08762; arXiv:2506.23971 | data/model release; exact GitHub/HF path needs verification | Molecular/materials model + dataset layer | Verify repo |
| NVIDIA | BioNeMo Framework | https://blogs.nvidia.com/blog/bionemo-large-language-models-drug-discovery/ | arXiv:2411.10548 | https://github.com/NVIDIA/bionemo-framework | Drug-discovery model framework / platform infrastructure | Pull candidate |
| OpenAI | FrontierScience | https://openai.com/index/frontierscience/ | arXiv:2601.21165 / OpenAI paper PDF | public benchmark code not confirmed | Science reasoning benchmark | Verify dataset/code availability |
| OpenAI | Early Science Acceleration Experiments with GPT-5 | OpenAI science post / PDF | arXiv:2511.16072 | code not expected / case-study paper | Frontier lab case-study evidence | Paper only, no repo expected |

## Medium-confidence leads

| Company / lab | System | Evidence found | Why it may matter | Status |
|---|---|---|---|---|
| Amazon / AWS | AutoClimDS | Amazon Science PDF mentions GitHub repository | Climate data science agentic AI with KG workflows | Need exact repo |
| Amazon / AWS | DGL-LifeSci | AWS/GitHub + ACS Omega paper | Chemistry/biology graph ML toolkit | Not AI scientist, useful infrastructure |
| Amazon / AWS | CodeStruct | Amazon Science page has GitHub link | Code agent architecture, adjacent to scientific coding agents | Not science-specific |
| Microsoft | Bioagents / Biocoder | Scientific Reports PDF points to Microsoft bioinformatics GitHub | Bioinformatics code generation benchmark / agents | Need exact repo |
| Meta FAIR | FastCSP with UMA | Meta research publication | Materials crystal-structure prediction with UMA | Need code path |

## Count estimate

Strict high-value triplets:

- 8-10 more candidates.

Broader company-backed article + code pairs:

- 15-25 more candidates.

Likely useful for the core AI-scientist review:

- 5-7 more after filtering.

Likely appendix / infrastructure only:

- 10-18 more.

## Triage rule

Pulled:

1. Google ERA - `open-source/era`
2. Microsoft MatterGen - `open-source/mattergen`
3. Microsoft MatterSim - `open-source/mattersim`
4. Microsoft BioEmu - `open-source/bioemu`
5. NVIDIA BioNeMo Framework - `open-source/bionemo-framework`

Verify before pulling:

1. Meta OMol25 / UMA exact repo or model card
2. OpenAI FrontierScience dataset/code availability
3. Amazon AutoClimDS exact repo
4. Microsoft Bioagents / Biocoder exact repo

Avoid promoting to core evidence unless agentic:

- ESM
- MatterSim
- BioEmu
- OMol25 / UMA
- DGL-LifeSci

These are important scientific AI infrastructure, but not autonomous research agents by themselves.
