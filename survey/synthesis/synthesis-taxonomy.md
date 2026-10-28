---
title: Synthesis taxonomy
created: 2026-06-05
updated: 2026-07-01
authority: working
freshness: tentative
---

# Synthesis taxonomy

This taxonomy is for organizing findings before narrative synthesis.

## System classes

1. Hypothesis engines

- Co-Scientist
- ResearchAgent
- VirSci
- Qi et al. hypothesis generation

2. Closed-loop / lab-in-the-loop discovery systems

- Robin
- Stanford Virtual Lab
- Coscientist
- BioDiscoveryAgent
- self-driving lab systems

3. End-to-end paper / ML research automation

- Sakana AI Scientist
- AI Scientist v2
- AutoScientists
- Medical AI Scientist
- EvoScientist
- MLR-Copilot
- AgentLaboratory

4. Scientific coding / executable research agents

- ERA
- ScienceAgentBench systems
- AstaBench agents
- PaperBench / MLE-Bench agents
- RE-Bench
- SoundnessBench
- omics AI scientist benchmark

5. Biomedical agent operating systems / tool layers

- ToolUniverse
- Biomni
- Scientific Agent Skills
- Medea
- ARK
- Paper2Agent

6. Scientific literature agents

- PaperQA2
- CHIME
- NotebookLM / Literature Insights

7. Scientific workbenches / product infrastructure

- Claude Science
- Claude for Life Sciences
- Gemini for Science
- FutureHouse Platform

8. Foundation model / evaluator infrastructure

- MatterGen
- MatterSim
- BioEmu
- BioNeMo
- ESM / ESMFold
- OMol25 / UMA

9. Scientific integrity / review / safety

- Agents4Science
- AgentReview
- ReviewCritique
- Tang et al. safeguarding
- Messeri & Crockett illusions of understanding
- medical interpretability maps
- AI Scientists Fail Without Strong Implementation Capability
- Hidden Pitfalls of AI Scientist Systems
- Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery

## Evidence axes

Autonomy:

- assistant
- tool-using agent
- multi-agent workflow
- autonomous coding/research loop
- lab-in-the-loop
- self-driving lab / robotic loop

Validation:

- no validation
- expert preference
- benchmark
- retrospective reproduction
- prospective prediction
- wet-lab validation
- clinical/real-world outcome

Reproducibility:

- no code
- code only
- code + examples
- code + data
- code + data + trajectories/prompts
- runnable benchmark/eval harness

Scope:

- literature-only
- code/data analysis
- computational experiment
- wet-lab design
- wet-lab execution
- scientific writing/review
- platform/tool ecosystem

Risk:

- hallucinated citations
- weak novelty assessment
- benchmark contamination
- overclaiming autonomy
- irreproducibility
- hidden human labor
- unsafe tool/lab access
- model/data leakage
- scientific monoculture

## Working synthesis claim

The field is splitting into three families:

1. Agentic research workflows that try to behave like scientists.
2. Benchmarks that expose how brittle these agents still are.
3. Executable science infrastructure that may become the substrate for future AI scientists.

The systematic review should keep those families separate. Otherwise the story becomes mush: a protein emulator, a literature agent, a wet-lab planner, and a paper-writing agent all get called "AI scientist" even though they automate very different parts of science.
