---
title: AI Scientist watchlist
created: 2026-06-05
updated: 2026-06-05
authority: working
freshness: tentative
---

# Watchlist

## Demis Hassabis / Google DeepMind

Track under the canonical spelling: Demis Hassabis.

Why watch:

- Google DeepMind is now publishing and productizing multi-agent science systems.
- Co-Scientist and Gemini for Science are directly relevant to AI scientist workflows.
- Google has primary-paper pointers in Nature for Co-Scientist and Empirical Research Assistance.
- DeepMind's science strategy connects models, specialized tools, AlphaFold/AlphaGenome-style assets, and enterprise R&D deployment.
- As of 2026-05-19, the public science strategy is not a single system. It is a suite: Hypothesis Generation via Co-Scientist, Computational Discovery via ERA + AlphaEvolve, Literature Insights via NotebookLM, and Science Skills in Antigravity.

Current source anchors:

- https://deepmind.google/blog/co-scientist-a-multi-agent-ai-partner-to-accelerate-research/
- https://blog.google/innovation-and-ai/technology/research/gemini-for-science-io-2026/

Primary follow-up queue:

- Nature DOI 10.1038/s41586-026-10644-y: Co-Scientist.
- Nature DOI 10.1038/s41586-026-10658-6: Empirical Research Assistance.
- Google Research ERA code and experiments.
- AlphaEvolve paper / technical artifacts.
- Google Labs / Gemini for Science availability and product docs.
- Any technical talks/interviews where Hassabis states the science-AI roadmap.

Current interpretation:

- Co-Scientist is the hypothesis-generation / idea-tournament branch.
- ERA is the empirical scientific software branch: LLM + tree search writes and optimizes code against quality metrics.
- AlphaEvolve is the algorithm-discovery branch: Gemini-powered code evolution using automated evaluators.
- Gemini for Science is the product umbrella that packages these capabilities for researchers.
- Evidence strength is highest for Nature papers and code-linked ERA artifacts; product availability claims remain tentative until docs/access are checked.

## FutureHouse

Why watch:

- FutureHouse explicitly frames its mission as building an AI Scientist.
- It has public agents, open-source training infrastructure, biology benchmarks, and a new Nature-linked Robin system.
- It is useful as a comparison case against Google DeepMind: nonprofit lab, science-specific agents, open tooling, and benchmark-first positioning.

Current source anchors:

- https://www.futurehouse.org/research-announcements/launching-futurehouse-platform-ai-agents
- https://www.futurehouse.org/research-announcements/aviary
- https://www.futurehouse.org/

Primary follow-up queue:

- Nature DOI 10.1038/s41586-026-10652-y: Robin.
- arXiv:2412.21154: Aviary / training language agents on biology tasks.
- Future-House/aviary GitHub repository.
- Future-House/ldp GitHub repository.
- LAB-Bench benchmark details and human baselines.
- FutureHouse platform docs for Crow, Falcon, Owl, Phoenix, and any Robin access.

## Monitoring questions

1. Are these systems producing new validated scientific findings, or mainly improving literature search and hypothesis ranking?
2. What is the evidence boundary: benchmark score, expert preference, prospective lab validation, or clinical/experimental outcome?
3. How much of the system is open and reproducible?
4. What role do humans play in reviewing, approving, and executing experiments?
5. Where are leakage and memorization controlled?
