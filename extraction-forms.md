---
title: PRISMA extraction forms
created: 2026-06-05
updated: 2026-06-15
authority: working
freshness: tentative
---

# PRISMA extraction forms

Use these forms for every included paper and repository.

## Paper extraction form

| Field | Value |
|---|---|
| Record ID |  |
| System / benchmark |  |
| Title |  |
| Authors |  |
| Year |  |
| Venue |  |
| DOI / arXiv |  |
| Institution / company |  |
| Domain |  |
| Task type |  |
| Architecture |  |
| Human role |  |
| Tools / databases |  |
| Memory / state |  |
| Code execution |  |
| Lab automation |  |
| Evaluation dataset |  |
| Number of tasks/examples |  |
| Baselines |  |
| Human baseline |  |
| Contamination controls |  |
| False-negative risk |  |
| Subject-matter validation |  |
| Benchmark publicness |  |
| Validation/test split |  |
| Judge model and version |  |
| Judge prompt or rubric |  |
| Human adjudication |  |
| Metrics |  |
| Main results |  |
| Wall-clock time |  |
| Cost / token logging |  |
| Replicas / runs |  |
| Wet-lab / prospective validation |  |
| Ablations |  |
| Failure modes |  |
| Limitations stated by authors |  |
| Reviewer limitations / inference |  |
| Evidence level |  |
| Core / benchmark / infrastructure / appendix |  |

## Repository extraction form

| Field | Value |
|---|---|
| Record ID |  |
| Repository |  |
| Local path |  |
| Commit |  |
| Created at |  |
| Last push |  |
| Stars / forks |  |
| Open issues/PRs |  |
| License |  |
| Maintainers / top contributors |  |
| Package manager |  |
| Install command |  |
| Entry points |  |
| Required API keys |  |
| Required models |  |
| Required datasets |  |
| Example runs |  |
| Prompts / trajectories included |  |
| Trajectory available |  |
| Trajectory format |  |
| Trajectory contents |  |
| Eval scripts included |  |
| Tests included |  |
| Dirty tree status |  |
| Dependency lockfile |  |
| Tool permission model |  |
| Sandboxing model |  |
| Network access policy |  |
| Search backend status |  |
| Rate limit / API failure |  |
| Tool registry quality |  |
| Skill review status |  |
| Cost / token logging |  |
| Wall-clock time |  |
| Replicas / runs |  |
| Reproducibility level |  |
| Blocking issues |  |
| Notes |  |

## Benchmark quality addendum

Use this addendum for benchmarks, eval harnesses, and papers that report benchmark-style results.

| Field | Value |
|---|---|
| Record ID |  |
| Benchmark name |  |
| Task horizon |  |
| Ecological validity |  |
| Hidden/public test status |  |
| Gold answer / rubric source |  |
| Alternative valid solutions accepted |  |
| False-negative mitigation |  |
| Contamination mitigation |  |
| Temporal leakage mitigation |  |
| Human baseline |  |
| Subject-matter expert review |  |
| Scoring reliability |  |
| LLM judge audit |  |
| Rescoring policy |  |
| Cost-normalized reporting |  |
| Dataset access constraints |  |
| Main benchmark limitations |  |

## Tool / skill governance addendum

Use this addendum for tool registries, skill libraries, MCP-style systems, and agent platforms that dynamically call external tools.

| Field | Value |
|---|---|
| Record ID |  |
| Tool / skill source |  |
| Tool schema quality |  |
| Argument validation |  |
| Result provenance |  |
| Tool versioning |  |
| Async / long-job handling |  |
| Result caching |  |
| Error propagation |  |
| Tool-call reproducibility from logs |  |
| Permission boundary |  |
| Manual review status |  |
| Community contribution policy |  |
| Dependency risk |  |
| Lab / robotic / clinical access |  |
| Security notes |  |

## Evidence levels

| Level | Label | Criteria |
|---|---|---|
| 1 | high | Peer-reviewed primary paper + code/data + prospective/wet-lab or strong reproducible benchmark evidence. |
| 2 | moderate | Technical paper + code/benchmark + retrospective evaluation. |
| 3 | limited | Paper/blog + partial code or non-reproducible claims. |
| 4 | context | Product/company/news/policy context only. |

## Reproducibility levels

| Level | Label | Criteria |
|---|---|---|
| A | runnable | Code, data or scripts, clear install, examples/evals runnable locally or with documented credentials. |
| B | inspectable | Code and examples present, but data/API/model access blocks full reproduction. |
| C | partial | Code snapshot exists but missing key data, prompts, trajectories, or eval scripts. |
| D | unavailable | No public code or reproduction path. |
