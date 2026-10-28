---
title: Awesome Agents4Science triage
created: 2026-06-05
updated: 2026-06-05
authority: working
freshness: tentative
source: OSU-NLP-Group/awesome-agents4science
---

# Awesome Agents4Science triage

Source:

- Local snapshot: `open-source/awesome-agents4science`
- GitHub: https://github.com/OSU-NLP-Group/awesome-agents4science

## What is good here

The strongest part is the benchmark table. It already separates:

- task type
- scientific domain
- number of examples
- source of tasks
- ecological validity
- contamination risk
- human performance availability
- time horizon

That is directly useful for our systematic review, because it gives criteria for separating serious evals from leaderboard theater.

## Promote to benchmark/evaluation core

| Item | Why it matters | Code status | Action |
|---|---|---|---|
| DiscoveryBench | Data-driven discovery workflows from real/synthetic publication tasks; broad scientific domains | Repo exists: https://github.com/allenai/discoverybench | Pull / audit |
| SciCode | Scientist-curated research coding tasks; low contamination risk; math/physics/bio/chem/materials | Repo exists: https://github.com/scicode-bench/SciCode | Pull / audit |
| BLADE | Data-driven science benchmark with expert validation; strong fit for analysis/report workflows | Repo exists: https://github.com/behavioral-data/BLADE | Pull / audit |
| RE-Bench | Frontier AI R&D benchmark with human expert comparison and longer time horizon | Repo exists: https://github.com/METR/RE-Bench | Pull / audit |
| MLAgentBench | Predecessor / adjacent benchmark for ML experimentation agents | Repo exists: https://github.com/snap-stanford/MLAgentBench | Pull / audit |
| CHIME | Biomedical literature-review organization benchmark | Repo not confirmed from obvious URL | Search exact code / data |
| Qi et al. 2023 | Biomedical hypothesis-generation benchmark / framing | Code not checked | Read; likely source-inventory, not code-first |
| AAAR-1.0 | R&D workflow benchmark: equations, experiment design, paper weakness, review critique | Code not checked | Search exact repo |

Already in our project:

- ScienceAgentBench
- MLE-Bench
- BixBench
- AstaBench
- PaperBench/frontier-evals

## Promote to agent systems backlog

| Item | Why it matters | Code status | Action |
|---|---|---|---|
| PaperQA2 | Strong literature-search / synthesis agent; FutureHouse lineage; useful for scientific knowledge synthesis | Repo exists: https://github.com/Future-House/paper-qa | Pull / audit |
| BioDiscoveryAgent | Genetic perturbation experiment design; Stanford/SNAP; strong biomedical fit | Repo exists: https://github.com/snap-stanford/BioDiscoveryAgent | Pull / audit |
| ChemCrow | Chemistry tool-using agent; Nature Machine Intelligence; important tool-augmented chemistry baseline | Repo exists: https://github.com/ur-whitelab/chemcrow-public | Pull / audit |
| AgentLaboratory | End-to-end research workflow agent; not in README but adjacent and code exists | Repo exists: https://github.com/SamuelSchmidgall/AgentLaboratory | Pull / audit after source verification |
| MLR-Copilot | Autonomous ML research idea + implementation agent | Code not checked | Search exact repo |
| ProtAgents | Protein design multi-agent system by Buehler group | Code not checked | Search exact repo |
| AtomAgents | Alloy/materials multi-agent design by Buehler group | Code not checked | Search exact repo |
| TAIS | Disease-predictive gene discovery from gene expression | Code not checked | Search exact repo |
| DrugAgent | Drug repurposing multi-agent / DTI workflow | Code not checked | Search exact repo |
| Chemist-X | Reaction-condition recommendation agent | Obvious GitHub URL not found | Search exact repo |
| ChatMOF | MOF prediction/generation agent | Code not checked | Search exact repo |

Already in our project:

- AI Scientist / AI Scientist v2
- AutoScientists
- Coscientist
- Robin
- Virtual Lab
- ToolUniverse
- Biomni
- Medea
- PROTON
- ARK

## Promote to integrity / safety section

| Item | Why it matters | Action |
|---|---|---|
| Tang et al. 2024b, "Prioritizing Safeguarding Over Autonomy" | Direct risk framework for LLM agents in science | Add to source inventory after reading |
| Messeri & Crockett 2024, "Artificial intelligence and illusions of understanding" | Nature-level critique of AI-driven scientific monocultures / overconfidence | Add to integrity section |
| AgentReview | Peer-review dynamics and bias simulation | Add to scientific communication subsection |
| ReviewCritique | AI-assisted meta-reviewing benchmark | Keep with review/integrity benchmarks |

## Lower priority / appendix

| Item | Reason |
|---|---|
| GIS Copilot / autonomous GIS agent | Useful outside biomedical/materials; keep if review scope broadens |
| Mephisto | Interesting astronomy use case; appendix unless broad science-agents scope |
| ChatGPT Research Group for MOFs/COFs | Relevant to chemistry automation; weaker direct agent-code path until code/source checked |
| MedAgents / AgentMD | Medical reasoning/clinical calculator agents, useful but not discovery-first |

## Immediate pull candidates

1. DiscoveryBench
2. SciCode
3. BLADE
4. RE-Bench
5. MLAgentBench
6. PaperQA
7. BioDiscoveryAgent
8. ChemCrow

Optional:

- AgentLaboratory, after source verification.

## Working conclusion

Yes, there is good material here. The best use is not as a bibliography dump, but as a benchmark/eval expansion pack. It adds the missing evaluation layer around our current agent systems:

- Can the agent write scientific code?
- Can it perform data-driven discovery tasks?
- Does the benchmark resemble real research?
- Is contamination risk low?
- Is there a human baseline?
- How long is the task horizon?

For systematic review structure, this repo should inform the "Evaluation and benchmarks" section more than the "AI scientist systems" section.
