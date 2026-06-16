---
title: Primary paper notes - Co-Scientist and Robin
created: 2026-06-05
updated: 2026-06-05
authority: working
freshness: tentative
---

# Primary paper notes

## Co-Scientist

Source:

- Nature: https://doi.org/10.1038/s41586-026-10644-y
- arXiv predecessor: https://arxiv.org/abs/2502.18864
- Google DeepMind blog: https://deepmind.google/blog/co-scientist-a-multi-agent-ai-partner-to-accelerate-research/

Citation anchor:

- Gottweis, Weng, Daryin, Tu, et al. "Accelerating scientific discovery with Co-Scientist." Nature, published 2026-05-19. DOI: 10.1038/s41586-026-10644-y.

System type:

- Multi-agent AI system built on Gemini.
- Goal: structured scientific thinking and hypothesis generation.
- Mode: scientist provides research objective and constraints; system generates, critiques, ranks, evolves, and summarizes hypotheses for experimental verification.

Architecture:

- Generation agent: proposes hypotheses grounded in scientific literature and data.
- Proximity agent: clusters and diversifies hypotheses.
- Reflection agent: peer-review-style critique.
- Ranking agent: tournament / pairwise debate to prioritize hypotheses.
- Evolution agent: refines and combines top hypotheses.
- Meta-review agent: synthesizes debates into final research proposal.
- Supervisor / planner: coordinates parallel work.

Evidence / validation:

- Nature abstract reports automated evaluations showing benefits from test-time compute scaling.
- Main biomedical validation areas:
  - drug repurposing
  - novel target discovery
  - antimicrobial resistance mechanism explanation
- Reported wet-lab validation includes acute myeloid leukemia drug repurposing candidates and synergistic therapies validated in vitro.
- arXiv predecessor reports AML candidates, liver fibrosis epigenetic targets validated in human hepatic organoids, and recapitulation of an unpublished bacterial gene-transfer mechanism.

Review interpretation:

- Strong evidence for AI-assisted hypothesis generation with lab follow-up.
- Not fully autonomous science: human scientists define goals, review candidates, select experiments, and run wet-lab validation.
- Best classified as "multi-agent hypothesis engine with human-in-the-loop experimental validation."

Key uncertainties / extraction needs:

- Need full Nature methods, figures, supplementary data, and peer review file if accessible.
- Need exact scoring rubrics, automated evaluation design, baselines, and ablation results.
- Need distinguish claims from the 2025 arXiv version versus the 2026 Nature version.
- Need determine product availability and reproducibility: model access, code availability, prompts, trajectories, and data.

## Robin

Source:

- Nature: https://doi.org/10.1038/s41586-026-10652-y
- arXiv preprint: https://arxiv.org/abs/2505.13400
- FutureHouse announcement: https://www.futurehouse.org/research-announcements/demonstrating-end-to-end-scientific-discovery-with-robin-a-multi-agent-system

Citation anchor:

- Ghareeb, Chang, Mitchener, et al. "A multi-agent system for automating scientific discovery." Nature, published 2026-05-19. DOI: 10.1038/s41586-026-10652-y.

System type:

- Multi-agent system for automating major intellectual steps of experimental biology.
- Goal: disease-in, hypotheses/experiments/data-analysis/updated-hypotheses out.
- Mode: lab-in-the-loop; humans execute wet-lab experiments and feed results back.

Architecture:

- Integrates literature search agents with data-analysis agents.
- FutureHouse context indicates Robin builds on agents such as Crow/Falcon for literature and Finch for data analysis.
- Nature abstract describes generating hypotheses, proposing experiments, interpreting results, and generating updated hypotheses.

Evidence / validation:

- Target disease: dry age-related macular degeneration (dAMD).
- Proposed therapeutic strategy: enhance retinal pigment epithelium phagocytosis.
- Identified candidates: ripasudil and KL001.
- Nature abstract states in vitro efficacy was confirmed for ripasudil and KL001.
- Follow-up RNA-seq experiment proposed and analyzed by Robin suggested ABCA1 upregulation as a possible mechanism / target.
- Nature page exposes supplementary materials, including agent prompts, experimental workflows, flow cytometry gating/analyses, RNA-seq results, evaluation rubrics, LLM-judge versus human-expert concordance, and BixBench-related data.

Review interpretation:

- Stronger closed-loop claim than Co-Scientist because the paper emphasizes hypothesis generation, experimental planning, data analysis, and updated hypotheses within one workflow.
- Still semi-autonomous rather than physically autonomous: humans run experiments.
- Best classified as "lab-in-the-loop multi-agent discovery workflow for drug repurposing."

Key uncertainties / extraction needs:

- Need full supplementary extraction: prompts, ablations, rubrics, concordance, and raw evaluation tables.
- Need inspect Future-House/robin repository and example trajectories.
- Need verify novelty claim: ripasudil not previously proposed for dAMD.
- Need evaluate generality: one disease area / drug repurposing use case may not transfer to arbitrary scientific domains.

## Comparison

| Dimension | Co-Scientist | Robin |
|---|---|---|
| Institution | Google DeepMind / Google Research / Google Cloud with collaborators | FutureHouse with academic collaborators |
| Primary Nature DOI | 10.1038/s41586-026-10644-y | 10.1038/s41586-026-10652-y |
| Core task | Hypothesis generation and ranking | End-to-end intellectual loop: hypotheses, experiment proposals, data analysis, updated hypotheses |
| Main architecture | Generate-debate-evolve tournament of ideas | Integrated literature and data-analysis agents |
| Human role | Set objectives, review/select candidates, conduct validation | Enter disease/query, run wet-lab experiments, return data |
| Wet-lab validation | AML drug repurposing; liver fibrosis and AMR examples in arXiv predecessor | dAMD drug repurposing; ripasudil/KL001 in vitro validation |
| Reproducibility | Unclear; likely limited by Gemini system access | Better prospects; FutureHouse states Robin code/trajectories are released |
| Evidence boundary | Multi-domain biomedical validation, but system access opaque | Strong single-disease lab-in-loop demonstration; generality uncertain |

## Working conclusion

These two papers should be treated as central primary sources for the review. They represent two leading designs:

- Co-Scientist: broad hypothesis-generation engine with scalable test-time debate/evolution.
- Robin: narrower but more complete lab-in-the-loop research cycle with data analysis and follow-up hypothesis generation.

The review should not collapse them into the same category. Co-Scientist is stronger as a general hypothesis engine; Robin is stronger as a closed-loop discovery demonstration.
