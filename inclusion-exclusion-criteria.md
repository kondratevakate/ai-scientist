---
title: Inclusion and exclusion criteria
created: 2026-06-05
updated: 2026-06-05
authority: working
freshness: tentative
---

# Inclusion And Exclusion Criteria

## Include Core

Include if both are true:

- source describes an AI system for scientific research workflows
- source provides technical evidence: paper, benchmark, code, dataset, methods, or validation

Eligible system types:

- AI scientist systems
- autonomous or semi-autonomous research agents
- multi-agent scientific discovery systems
- hypothesis-generation systems
- scientific coding / empirical software agents
- lab-in-the-loop or self-driving-lab agents
- biomedical AI agents for discovery workflows
- paper-to-agent / reproducibility systems

Eligible evidence:

- peer-reviewed paper
- arXiv / bioRxiv / medRxiv technical paper
- benchmark or dataset release
- public code repository
- reproducible examples / trajectories
- prospective or wet-lab validation
- official lab technical blog linked to primary evidence

## Include Benchmark

Include if the source evaluates agentic scientific capabilities:

- scientific code generation
- data-driven discovery tasks
- ML research engineering
- paper replication
- literature review / synthesis
- hypothesis generation
- experiment design
- review/meta-review

Required extraction fields:

- ecological validity
- contamination risk
- human baseline
- task horizon
- source of examples
- number of tasks
- scoring method
- hidden/public test status

## Include Infrastructure

Include as infrastructure, not core autonomous discovery evidence, if it provides:

- scientific tool library
- biomedical database/tool interface
- foundation model used as evaluator/tool
- simulator/emulator for scientific workflows
- reproducibility/MCP/paper-to-agent tooling

## Include Integrity

Include if source addresses:

- scientific hallucination
- weak novelty assessment
- AI-generated papers/reviews
- benchmark contamination
- unsafe tool use
- lab automation risk
- reproducibility failures
- scientific monoculture / illusions of understanding
- interpretability/trustworthiness of biomedical models

## Appendix Only

Use appendix for:

- company/product pages without methods
- funding news
- policy strategy documents
- startup/lab watch items
- enterprise platform announcements without benchmark/code/validation

## Exclude Core

Exclude from core evidence if:

- no AI/scientific agent component
- no technical method or evaluation
- purely speculative opinion without system/evidence
- generic LLM-for-science discussion with no workflow specificity
- foundation model only, unless used inside an agent/evaluation loop
- clinical decision support without research/discovery workflow
- duplicated record already represented by a primary paper/repo
- unofficial third-party repo for a named system

## Exclusion Reason Labels

- `not-science-agent`
- `no-technical-evidence`
- `market-only`
- `news-only`
- `foundation-model-only`
- `clinical-only`
- `duplicate`
- `unofficial-source`
- `out-of-scope-domain`
