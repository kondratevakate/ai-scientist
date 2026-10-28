---
title: Requirements critique from open-source AI scientist projects
created: 2026-06-06
updated: 2026-06-15
authority: working
freshness: tentative
---

# Requirements Critique

Purpose: pressure-test `protocol/systematic-review-requirements-2026.md` against the strongest local open-source evidence in `open-source/`.

This is not a claim that these authors reviewed this project. It is a structured critique derived from the requirements, warnings, and evaluation practices visible in their local repositories.

## Critic Roles

| Critic | Source | What they show |
|---|---|---|
| ScienceAgentBench / OSU NLP Group | `open-source/ScienceAgentBench` | Benchmarks need false-negative mitigation, contamination control, subject-matter validation, and reproducible evaluation harnesses. |
| AstaBench / Allen Institute for AI | `open-source/asta-bench` | Evaluation needs standardized environments, solver metadata, git SHA logging, cost accounting, validation/test splits, and sandboxed tools. |
| BixBench / FutureHouse + ScienceMachine | `open-source/BixBench` | Real-world computational-biology benchmarks require trajectories, postprocessing, replicas, dataset access control, Docker, and cost/time reporting. |
| Sakana AI Scientist-v2 | `open-source/AI-Scientist-v2` | Autonomous research agents create safety risks through LLM-written code, package execution, web access, process spawning, and weak novelty checks under API limits. |
| Paper2Agent / Zou-Pritchard-Davis-Miao | `open-source/Paper2Agent` | Paper-to-agent reproducibility needs benchmark extraction, assessment reports, explicit assumptions, limitations, and human-readable quality artifacts. |
| ToolUniverse / HMS Zitnik Lab | `open-source/ToolUniverse` | Tooling should be assessed as a protocol and registry ecosystem, not only as a list of parsers or APIs. |
| scientific-agent-skills / K-Dense | `open-source/scientific-agent-skills` | Skills require permission boundaries, contribution review, and manual inspection; automated scans reduce review noise but do not replace review. |

## Concrete Critiques

### 1. Benchmark false negatives are under-specified

ScienceAgentBench explicitly released a verified version to mitigate false negatives and uses multiple rounds of manual validation by annotators and subject-matter experts.

Critique of current requirements:

- The requirements mention bias and benchmark leakage, but they do not yet require false-negative analysis.
- For AI Scientist systems, false negatives matter because agents may solve a task in an unexpected but scientifically valid way.

Required change:

- Add `false_negative_risk` to benchmark extraction.
- Record whether benchmark answers were validated by subject-matter experts.
- Record whether alternative valid solutions are accepted or only one gold answer is accepted.

### 2. Benchmark contamination needs operational controls

ScienceAgentBench withholds full benchmark artifacts from public redistribution to reduce contamination. AstaBench separates validation and test splits.

Critique of current requirements:

- The requirements say to assess contamination, but do not specify operational evidence.

Required change:

- Extract whether benchmark data, gold programs, rubrics, or hidden answers are public.
- Extract whether the benchmark has validation/test splits.
- Extract whether model familiarity, data leakage, or temporal leakage was measured.

### 3. LLM-as-judge requires versioned audit

ScienceAgentBench uses GPT-4o to judge output visualizations. AstaBench documents rescoring workflows when judge models change.

Critique of current requirements:

- The requirements mention LLM judges only indirectly under AI-use disclosure.
- They do not require judge-model versioning, rescoring policy, or judge instability reporting.

Required change:

- Record judge model, version/date, prompt/rubric, and whether human adjudication exists.
- Record whether historical scores can be rescored when the judge model changes.
- Treat LLM-judged scores as weaker than deterministic tests unless validated.

### 4. Trajectory-level evidence is mandatory for agentic systems

BixBench stores trajectories and evaluates them through postprocessing. AstaBench includes trajectory-based scoring for some tasks. Robin and AutoScientists preserve logs/trajectories for research workflows.

Critique of current requirements:

- The current reproducibility grade mentions prompts/trajectories, but it should be elevated to a first-class evidence criterion.

Required change:

- Add `trajectory_available` and `trajectory_format` to repository extraction.
- Record whether trajectories include tool calls, code, intermediate files, model outputs, failures, and final outputs.
- Penalize systems that publish only final papers/results without execution traces.

### 5. Cost and compute are evidence, not implementation detail

AstaBench treats model usage and cost logging as core evaluation design. BixBench warns that agentic evaluation can take 24-48 hours and significant API credits.

Critique of current requirements:

- The current requirements include compute requirements but do not require cost-normalized comparison.

Required change:

- Extract wall-clock time, API/model cost, number of replicas/runs, token usage where available, and hardware requirements.
- Compare systems on performance and cost, not performance alone.
- Mark claims as weak if performance is reported without run budget.

### 6. Dirty state and commit identity matter

AstaBench logs git SHA and warns that running with uncommitted changes can harm reproducibility.

Critique of current requirements:

- The current repository extraction asks for commit, but does not require dirty-tree status or exact eval version.

Required change:

- Record commit hash, tag/release, dirty tree status, dependency lockfile, and evaluation artifact version.
- Treat unpinned main-branch claims as tentative.

### 7. Sandbox and tool permissions need explicit review

AI-Scientist-v2 warns that LLM-written code can install dangerous packages, use uncontrolled web access, and spawn unintended processes. AstaBench uses sandboxed tools. scientific-agent-skills uses `allowed-tools` and says scans do not replace manual review.

Critique of current requirements:

- The current requirements mention safety, but do not yet require a tool-permission matrix.

Required change:

- Add `tool_permission_model` to repository extraction.
- Record filesystem, network, shell, package-install, cloud, database, and lab/robotic access.
- Record whether runs happen in Docker/VM/sandbox and whether network isolation is enforced.
- Record whether skills/tools underwent manual review.

### 8. Literature search tools need coverage and failure accounting

ToolUniverse provides unified literature search across PubMed, Semantic Scholar, arXiv, bioRxiv, Europe PMC, and more. AI-Scientist-v2 depends on Semantic Scholar for novelty checking and citation generation, with known rate-limit degradation.

Critique of current requirements:

- The current tool list is broad but does not force per-tool coverage, rate-limit, and failure accounting.

Required change:

- Record which search backends actually ran, not just which were planned.
- Record API keys, rate limits, errors, partial results, and skipped citation/novelty phases.
- Treat failed novelty checks as a limitation in system claims.

### 9. Tool registry quality is different from parser availability

ToolUniverse frames tools as an interaction protocol, registry, async execution system, and composable workflow layer.

Critique of current requirements:

- Listing parsers/APIs is insufficient for AI Scientist systems that call tools dynamically.

Required change:

- Assess tool schemas, argument validation, provenance, versioning, async job handling, result caching, and error propagation.
- Record whether tool calls are reproducible from logs.
- Record whether the system can inspect tool metadata before calling tools.

### 10. Skill ecosystems need contribution provenance

scientific-agent-skills distinguishes internally reviewed K-Dense skills from community contributions and warns not to install everything blindly.

Critique of current requirements:

- The requirements treat skill libraries as infrastructure, but do not require provenance or review status.

Required change:

- Extract skill author/source, review status, permissions, tests, examples, dependency risk, and maintenance status.
- Separate curated skills from community-contributed skills.

## Updates Needed In Requirements

Add these fields to `protocol/extraction-forms.md` and/or `protocol/systematic-review-requirements-2026.md`:

- `false_negative_risk`
- `subject_matter_validation`
- `contamination_controls`
- `benchmark_publicness`
- `validation_test_split`
- `judge_model_and_version`
- `judge_prompt_or_rubric`
- `human_adjudication`
- `trajectory_available`
- `trajectory_format`
- `cost_or_token_logging`
- `wall_clock_time`
- `replicas_or_runs`
- `dirty_tree_status`
- `dependency_lockfile`
- `tool_permission_model`
- `sandboxing_model`
- `network_access_policy`
- `search_backend_status`
- `rate_limit_or_api_failure`
- `tool_registry_quality`
- `skill_review_status`

## Priority Fixes

1. Add an AI assistance / tool-use log before using AI for screening, extraction, or synthesis.
2. Extend extraction forms with benchmark validity, trajectory, cost, sandbox, and tool-permission fields.
3. Add a benchmark-quality checklist based on ScienceAgentBench, AstaBench, and BixBench.
4. Add a tool/skill governance checklist based on ToolUniverse and scientific-agent-skills.
5. In final synthesis, downgrade claims when code, trajectories, costs, contamination controls, or human validation are absent.

## Status Update, 2026-06-15

Completed:

- `logs/ai-assistance-log.md` created.
- `protocol/extraction-forms.md` extended with benchmark validity, trajectory, cost, sandbox, tool-permission, search-backend, and skill/tool governance fields.
- Benchmark-quality and tool/skill governance addenda added to `protocol/extraction-forms.md`.

Still required:

- Fill the expanded forms for Tier A systems and benchmark/eval sources.
- Apply downgrades consistently in synthesis when code, trajectories, costs, contamination controls, or human validation are missing.
- Preserve source-to-claim traceability before writing final conclusions.
