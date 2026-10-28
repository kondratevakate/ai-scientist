---
title: AI Scientist code repositories
created: 2026-06-05
updated: 2026-06-15
authority: working
freshness: confirmed
---

# Code repositories

Local clone root:

`D:\projects\02_academia\ai-scientist\open-source`

Clone mode:

- originally pulled as shallow clones
- internal `.git` directories removed after move
- stored as ordinary source snapshots, not submodules
- no `.gitignore` changes were made

Snapshot reproducibility caveat:

- These folders are inspectable source snapshots, not reproducible git checkouts.
- The listed short commits should be treated as provenance hints until rehydrated against upstream remotes.
- Full repository audits should re-clone or verify each upstream remote, full commit SHA, tag/release, submodules, license file hash, dependency lockfiles, dirty-tree status, and clone date.
- Do not report a repository as fully reproducible only because a local snapshot exists.
- Do not include these local snapshots in a CC0/public-domain release of the compilation. Publish repository URLs, commit provenance, and audit notes instead; see `THIRD_PARTY_SOURCES.md`.

## Pulled repositories

| Solution / role | Repository | Local path | Commit |
|---|---|---|---|
| Scientific Agent Skills | https://github.com/k-dense-ai/scientific-agent-skills.git | `D:\projects\02_academia\ai-scientist\open-source\scientific-agent-skills` | `b2a969e` |
| AutoScientists | https://github.com/mims-harvard/AutoScientists.git | `D:\projects\02_academia\ai-scientist\open-source\AutoScientists` | `c71a923` |
| Sakana AI Scientist | https://github.com/SakanaAI/AI-Scientist.git | `D:\projects\02_academia\ai-scientist\open-source\AI-Scientist` | `1de1dbc` |
| Sakana AI Scientist v2 | https://github.com/SakanaAI/AI-Scientist-v2.git | `D:\projects\02_academia\ai-scientist\open-source\AI-Scientist-v2` | `96bd516` |
| ToolUniverse | https://github.com/mims-harvard/ToolUniverse.git | `D:\projects\02_academia\ai-scientist\open-source\ToolUniverse` | `41b0f04` |
| Biomni | https://github.com/snap-stanford/Biomni.git | `D:\projects\02_academia\ai-scientist\open-source\Biomni` | `400c1f3` |
| Paper2Agent | https://github.com/jmiao24/Paper2Agent.git | `D:\projects\02_academia\ai-scientist\open-source\Paper2Agent` | `e573687` |
| Stanford / Zou Virtual Lab | https://github.com/zou-group/virtual-lab.git | `D:\projects\02_academia\ai-scientist\open-source\virtual-lab` | `8a3a4fd` |
| FutureHouse Robin | https://github.com/Future-House/robin.git | `D:\projects\02_academia\ai-scientist\open-source\robin` | `4a5cce3` |
| FutureHouse Aviary | https://github.com/Future-House/aviary.git | `D:\projects\02_academia\ai-scientist\open-source\aviary` | `5ab324b` |
| FutureHouse LDP | https://github.com/Future-House/ldp.git | `D:\projects\02_academia\ai-scientist\open-source\ldp` | `e95d6fe` |
| FutureHouse BixBench | https://github.com/Future-House/BixBench.git | `D:\projects\02_academia\ai-scientist\open-source\BixBench` | `4931118` |
| ScienceAgentBench | https://github.com/OSU-NLP-Group/ScienceAgentBench.git | `D:\projects\02_academia\ai-scientist\open-source\ScienceAgentBench` | `72220ee` |
| AstaBench | https://github.com/allenai/asta-bench.git | `D:\projects\02_academia\ai-scientist\open-source\asta-bench` | `fc0f716` |
| Asta agent baselines | https://github.com/allenai/agent-baselines.git | `D:\projects\02_academia\ai-scientist\open-source\agent-baselines` | `6ee642d` |
| MLE-Bench | https://github.com/openai/mle-bench.git | `D:\projects\02_academia\ai-scientist\open-source\mle-bench` | `507f92e` |
| PaperBench / OpenAI frontier evals | https://github.com/openai/frontier-evals.git | `D:\projects\02_academia\ai-scientist\open-source\frontier-evals` | `51052ce` |
| Medical interpretability LLM maps | https://github.com/TheLumos/medical-interpretability-llms.git | `D:\projects\02_academia\ai-scientist\open-source\medical-interpretability-llms` | `554e686` |
| Medea | https://github.com/mims-harvard/Medea | `D:\projects\02_academia\ai-scientist\open-source\Medea` | `d44d1d4` |
| PROTON | https://github.com/mims-harvard/PROTON | `D:\projects\02_academia\ai-scientist\open-source\PROTON` | `7d2bae9` |
| ARK agent CLI | https://github.com/mims-harvard/ark-agent-cli | `D:\projects\02_academia\ai-scientist\open-source\ark-agent-cli` | `e47f778` |
| CMU Coscientist | https://github.com/gomesgroup/coscientist | `D:\projects\02_academia\ai-scientist\open-source\coscientist` | `417e82b` |
| Aspuru-Guzik Atlas | https://github.com/aspuru-guzik-group/atlas | `D:\projects\02_academia\ai-scientist\open-source\atlas` | `ebb1f4f` |
| Agents4Science paper list | https://github.com/OSU-NLP-Group/awesome-agents4science | `D:\projects\02_academia\ai-scientist\open-source\awesome-agents4science` | `804867a` |
| Google ERA | https://github.com/google-research/era | `D:\projects\02_academia\ai-scientist\open-source\era` | `37637a4` |
| Microsoft MatterGen | https://github.com/microsoft/mattergen | `D:\projects\02_academia\ai-scientist\open-source\mattergen` | `a245cf2` |
| Microsoft MatterSim | https://github.com/microsoft/mattersim | `D:\projects\02_academia\ai-scientist\open-source\mattersim` | `40a1eb8` |
| Microsoft BioEmu | https://github.com/microsoft/bioemu | `D:\projects\02_academia\ai-scientist\open-source\bioemu` | `53e73d7` |
| NVIDIA BioNeMo Framework | https://github.com/NVIDIA/bionemo-framework | `D:\projects\02_academia\ai-scientist\open-source\bionemo-framework` | `534f7f1` |

## Code status by review category

Core autonomous discovery systems with public code:

- Sakana AI Scientist
- Sakana AI Scientist v2
- AutoScientists
- Stanford Virtual Lab
- FutureHouse Robin

Biomedical agent / tool infrastructure with public code:

- ToolUniverse
- Biomni
- Paper2Agent
- Scientific Agent Skills
- Medea
- PROTON
- ARK agent CLI

FutureHouse ecosystem with public code:

- Robin
- Aviary
- LDP
- BixBench

Benchmarks and eval harnesses with public code:

- ScienceAgentBench
- AstaBench
- Asta agent baselines
- MLE-Bench
- PaperBench via OpenAI frontier-evals
- BixBench
- Medea
- PROTON
- ARK agent CLI

Safety / interpretability code:

- Medical Interpretability and Knowledge Maps of LLMs

Chemistry / self-driving lab code:

- CMU Coscientist
- Aspuru-Guzik Atlas

Big-company executable science infrastructure:

- Google ERA
- Microsoft MatterGen
- Microsoft MatterSim
- Microsoft BioEmu
- NVIDIA BioNeMo Framework

## Not yet pulled / needs verification

- Kosmos: official system repository not found. Paper/report references `EdisonScientific/kosmos-figures`, but direct clone was not verified; unofficial third-party `jimmc414/Kosmos` exists and should not be treated as primary source.
- Agents4Science official dataset/artifacts: conference submissions/audits are web-hosted; a central official code/data repository was not found. Pulled `awesome-agents4science` as a curated paper list only.
- Andrew Cooper / Liverpool robotic chemist code: not yet scoped beyond paper trail.
- Connor Coley / MIT closed-loop chemistry code: not yet scoped.
- Other self-driving lab packages may be relevant, but require targeted search by paper.

## Next audit pass

For each pulled repository, extract:

- license
- installation method
- entry points / CLI
- required API keys
- required datasets
- whether example trajectories are included
- whether eval scripts are reproducible locally
- paper / DOI mapping
