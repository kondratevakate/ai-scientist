---
title: Search execution log
created: 2026-06-05
updated: 2026-06-15
authority: working
freshness: tentative
---

# Search Execution Log

Search folder:

`D:\projects\02_academia\ai-scientist\searches\2026-06-05`

## Initial Broad Pass

Databases:

- PubMed
- arXiv
- Semantic Scholar
- OpenAlex

Queries:

- `queries.json`

Results:

| Database | Query | Count / status |
|---|---|---:|
| PubMed | q1 AI scientist | 785 |
| PubMed | q2 science agents | 913344 |
| PubMed | q3 LLM science discovery | 28 |
| PubMed | q4 biomedical agents | 13313 |
| PubMed | q5 benchmarks | 1883 |
| PubMed | q6 self-driving labs | 22 |
| Semantic Scholar | all broad queries | 429 errors |
| arXiv | broad boolean queries | 429/timeouts |
| OpenAlex | broad boolean queries | exported, but counts not reliable for screening |

Decision:

- Broad pass is not suitable for screening.
- It is retained as a query-calibration record.

## Refined Pass

Queries:

- `queries-refined.json`

Results:

| Database | Query | Count | Status |
|---|---|---:|---|
| PubMed | r1_ai_scientist_phrase | 48 | exported |
| PubMed | r2_llm_science_agents | 28 | exported |
| PubMed | r3_biomedical_agents | 20 | exported |
| PubMed | r4_science_agent_benchmarks | 7 | exported |
| PubMed | r5_self_driving_lab_llm | 24 | exported |
| OpenAlex | refined queries | 0 | exported but likely syntax mismatch |
| arXiv | refined queries | error | timeout/API failure |

Decision:

- PubMed refined pass is usable for biomedical subset screening.
- OpenAlex requires revised syntax.
- arXiv should be rerun one query at a time with cooldown.

## ToolUniverse Attempt

Reason:

User requested ToolUniverse search.

Planned tools:

- `PubMed_search_articles`
- `SemanticScholar_search_papers`
- `ArXiv_search_papers`
- `EuropePMC_search_articles`

Files:

- `searches/2026-06-05/tooluniverse/queries-tooluniverse.json`
- `searches/2026-06-05/tooluniverse/tooluniverse-search-summary.json`

Runtime:

- system Python: 3.7.9
- ToolUniverse required Python: >=3.10

Attempts:

1. Direct import failed: `ModuleNotFoundError("No module named 'importlib.metadata'")`.
2. Installed `importlib_metadata` backport and shimmed `importlib.metadata`.
3. Next failure: `ModuleNotFoundError("No module named 'yaml'")`.
4. Installed `pyyaml`.
5. Next failure: `TypeError("unsupported operand type(s) for |: 'type' and 'NoneType'")`, consistent with Python 3.10 union type syntax.

Decision:

- Initial ToolUniverse run was blocked in system Python 3.7.9.
- Blocker resolved on 2026-06-06 by running local ToolUniverse source under Python 3.12 through `uv` and using `ToolUniverse.load_tools(include_tools=...)` instead of generated `tooluniverse.tools` wrappers.

Executed ToolUniverse Pass, 2026-06-06:

| Database | Queries | Status | Retrieved records |
|---|---:|---|---:|
| ToolUniverse/PubMed | 5 | success | 37 |
| ToolUniverse/SemanticScholar | 5 | partial: first query succeeded, later queries hit 429 | 5 |
| ToolUniverse/arXiv | 5 | success | 25 |
| ToolUniverse/EuropePMC | 5 | success | 25 |

Observed output:

- 92 raw database-query records across successful calls.
- 84 unique titles before formal deduplication.
- Notable new screening candidates include `Towards a Medical AI Scientist`, `Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery`, `AI Scientists Fail Without Strong Implementation Capability`, `Benchmarking AI scientists for omics data driven biological discovery`, `EvoScientist`, `PiFlow`, `Building MCP-native hierarchical AI scientist ecosystems`, `TeLLAgent`, `PantheonOS`, `Autonomous Chemistry and Materials Innovation Driven by Scientific Agents`, and `Polymer-Agent`.

Limitations:

- Semantic Scholar rate-limited after the first query (`429`).
- Raw ToolUniverse exports still need normalization into `prisma-records.md`, formal deduplication, and title/abstract screening decisions.

## Targeted Follow-Up Verification, 2026-06-15

Purpose:

Verify the highest-priority ToolUniverse candidates and reviewer-surfaced critique/evaluation sources before promoting them into `prisma-records.md`.

Promoted records:

| Source | Verified surface | PRISMA record |
|---|---|---|
| Towards a Medical AI Scientist | arXiv:2603.28589 | R060 |
| EvoScientist | arXiv:2603.08127 | R061 |
| Benchmarking AI scientists for omics data driven biological discovery | arXiv:2505.08341 | R062 |
| SoundnessBench | arXiv:2605.30329 | R063 |
| AI Scientists Fail Without Strong Implementation Capability | arXiv:2506.01372 | R064 |
| The More You Automate, the Less You See: Hidden Pitfalls of AI Scientist Systems | arXiv:2509.08713 | R065 |
| Agentic AI Scientists Are Not Built For Autonomous Scientific Discovery | arXiv:2605.08956 | R066 |

Decision:

- Promoted these records to full-text/code screening where appropriate.
- Kept freshness as `tentative`; promotion is not full extraction.
- Remaining ToolUniverse candidates still need deduplication and title/abstract screening.

## Next Required Search Steps

1. Continue normalizing remaining ToolUniverse candidates into screening records.
2. Re-run arXiv one query at a time for coverage beyond the ToolUniverse arXiv subset.
3. Re-run Semantic Scholar with API key or slow rate limit.
4. Re-run OpenAlex with non-boolean natural-language syntax.
5. Run Europe PMC directly for any ToolUniverse gaps.
6. Record final title/abstract include/exclude decisions with controlled exclusion labels.

