---
title: Database search strategy
created: 2026-06-05
updated: 2026-06-06
authority: working
freshness: tentative
---

# Database Search Strategy

Search exports:

`D:\projects\02_academia\ai-scientist\searches\2026-06-05`

## Sources

Primary databases:

- PubMed / PMC
- arXiv
- Semantic Scholar
- OpenAlex
- Europe PMC
- bioRxiv / medRxiv
- GitHub

Tool-mediated source:

- ToolUniverse literature tools:
  - `PubMed_search_articles`
  - `SemanticScholar_search_papers`
  - `ArXiv_search_papers`
  - `EuropePMC_search_articles`
  - `BioRxiv_*`

## Concept Blocks

AI scientist:

```text
"AI scientist" OR "AI scientists" OR "autonomous scientist" OR "autonomous scientific discovery" OR "automated scientific discovery"
```

Language agents:

```text
"large language model" OR LLM OR "language agent" OR "LLM agent" OR "multi-agent"
```

Scientific workflow:

```text
"scientific discovery" OR "hypothesis generation" OR "experiment design" OR "data analysis" OR "research automation" OR "scientific coding"
```

Biomedical/life science:

```text
biomedical OR biology OR medicine OR omics OR "drug discovery" OR "drug repurposing" OR "therapeutic discovery"
```

Evaluation:

```text
benchmark OR evaluation OR "human baseline" OR contamination OR reproducibility OR "data-driven scientific discovery"
```

Closed-loop labs:

```text
"self-driving lab" OR "self-driving laboratory" OR "closed-loop discovery" OR "autonomous laboratory" OR "wet-lab validation"
```

## PubMed Queries

Use Title/Abstract tags to avoid broad irrelevant retrieval.

```text
("AI scientist"[Title/Abstract] OR "AI scientists"[Title/Abstract] OR "autonomous scientist"[Title/Abstract] OR "autonomous scientific discovery"[Title/Abstract])
```

```text
(("large language model"[Title/Abstract] OR LLM[Title/Abstract])
AND (agent[Title/Abstract] OR agents[Title/Abstract])
AND ("scientific discovery"[Title/Abstract] OR "hypothesis generation"[Title/Abstract] OR "experiment design"[Title/Abstract]))
```

```text
(("biomedical AI agent"[Title/Abstract] OR "biomedical agent"[Title/Abstract] OR "AI scientist"[Title/Abstract])
AND (biology[Title/Abstract] OR biomedical[Title/Abstract] OR medicine[Title/Abstract] OR omics[Title/Abstract] OR drug[Title/Abstract]))
```

```text
("science agent benchmark"[Title/Abstract] OR "scientific agent benchmark"[Title/Abstract] OR "data-driven scientific discovery"[Title/Abstract] OR "AI research agent benchmark"[Title/Abstract])
```

```text
(("self-driving lab"[Title/Abstract] OR "self-driving laboratory"[Title/Abstract] OR "closed-loop discovery"[Title/Abstract] OR "autonomous laboratory"[Title/Abstract])
AND ("large language model"[Title/Abstract] OR agent[Title/Abstract] OR AI[Title/Abstract]))
```

## arXiv Queries

Use simple fielded strings and run one at a time.

```text
all:"AI scientist"
all:"large language model" AND all:"scientific discovery" AND all:agent
all:biomedical AND all:agent AND all:"large language model"
all:"science agent" AND all:benchmark
all:"self-driving lab" AND all:agent
```

## Semantic Scholar Queries

Use natural language and slow rate limiting.

```text
AI scientist autonomous scientific discovery
large language model agents scientific discovery hypothesis generation
biomedical AI agent omics drug discovery
science agent benchmark data-driven scientific discovery
self-driving laboratory large language model agent closed-loop discovery
```

## Europe PMC Queries

```text
"AI scientist" OR "autonomous scientific discovery"
"large language model" AND agent AND "scientific discovery"
"biomedical AI agent" OR ("AI scientist" AND omics)
"data-driven scientific discovery" AND benchmark
"self-driving laboratory" AND agent
```

## ToolUniverse Status

ToolUniverse is an executed search layer because it unifies PubMed, Semantic Scholar, arXiv, Europe PMC, bioRxiv, and other biomedical sources.

Execution:

- Date: 2026-06-06
- Runtime: Python 3.12 through `uv`
- Source: local snapshot `open-source/ToolUniverse`
- API path: `ToolUniverse.load_tools(include_tools=[...])` and `run_one_function(...)`
- Raw exports: `searches/2026-06-05/tooluniverse/`

Executed tools:

- `PubMed_search_articles`
- `SemanticScholar_search_papers`
- `ArXiv_search_papers`
- `EuropePMC_search_articles`

Results:

- PubMed: 37 records across five queries
- Semantic Scholar: 5 records from the first query; later calls returned API 429
- arXiv: 25 records across five queries
- Europe PMC: 25 records across five queries
- Unique titles before deduplication: 84

Next handling:

- Normalize raw ToolUniverse exports into PRISMA records.
- Deduplicate against existing 59 seed records.
- Apply inclusion/exclusion criteria at title/abstract stage.
- Re-run Semantic Scholar later with slower rate limiting or API key.
- save raw JSON under `searches/2026-06-05/tooluniverse`

