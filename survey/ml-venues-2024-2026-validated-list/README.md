# AI-scientist papers at ML and vision venues, 2024-2026 (from the ICML reproduction audit, 2026-10-24)

A validated list of papers about AI scientists and autonomous research agents, drawn from the paper sets of the
ICML 2026 reproduction audit. Nothing is pushed; all commits are local.

## Where things are

* This folder (`ai-scientist/survey/ml-venues-2024-2026-validated-list/`) holds the code, codes and results:
  * `PROTOCOL.md`: the keyword screen rule and Amendment 1 (validation codebook), both frozen before use.
  * `screen.py`: keyword screen; `code.py`: candidate pool, coder agreement, adjudication, validated list.
  * `CODER_PROMPT.md`: the blind coder prompt.
  * `codes/`: both coders' labels (`as1_*`, `as2_*`) and `adjudication.csv` (with reasons).
  * `results/validated.csv`: the list (venue-year, paper id, title, label, category, whether the keyword screen found
    it, and for ICML 2026 whether the paper was attempted and decided in the challenge).
  * `results/validated_summary.json`: counts; `results/papers.csv`, `results/summary.json`: the first keyword screen.
  * `work/` (git-ignored): coding sheets and candidate keys.
* The same work, with its history, is on branch `ai-scientist-papers` of
  `C:/Projects/02_academia/studies/icml-repro`. **That branch is on GitHub** (checked 2026-10-27,
  `kondratevakate/icml-2026-repro`, tip `069103a7`), so this list is public, by way of that repository rather
  than this one. An earlier version of this line said "local commits, not pushed"; that was true when it
  was written and is not true now. Its separate worktree was
  removed on 2026-10-24; the branch keeps every commit.
* Inputs are read from that repository's main checkout (git-ignored there): `verdict_audit/readiness/data/papers.json`
  (50,185 papers: ICLR 2025-2026, ICML 2025-2026, NeurIPS 2024-2026, CVPR 2024-2025, ICCV 2025, ECCV 2024 and 2026)
  and the verdict snapshot `data/verdicts_confirmation_2026-10-17/verdicts.json`. Set `MAIN_CHECKOUT` to point
  elsewhere.

## Method

1. Keyword screen of titles and abstracts (fixed phrases: AI scientist, research agent, automated research,
   automated discovery, self-driving lab, paper reproduction, named benchmarks such as PaperBench and MLE-bench).
2. Candidate pool of 327 papers: screen matches plus every paper naming both an agent or LLM and a research task.
3. Two blind coders (Claude Sonnet subagents), title and abstract only, venue hidden: include, exclude or unclear,
   plus a category for included papers. Agreement kappa 0.87; all 26 disagreements adjudicated by a Claude Opus
   subagent with a written reason.

Include = the paper's main subject is an AI system that carries out research steps itself (ideas or hypotheses,
experiments, analysis, writing, reviewing, reproducing papers) or a benchmark of such systems. Web-search "deep
research" agents, general coding or tool-use agents and scientific question answering are excluded.

## Findings

* 111 papers included (2 unclear) out of 327 candidates.
* By category: benchmarks of research agents 46, single research step (ideation, experiments, writing, review) 46,
  end-to-end AI scientist 15, self-driving labs 2, agents that reproduce papers 2.
* By venue-year: ICML 2026 26, NeurIPS 2026 23, ICLR 2026 22, NeurIPS 2025 16, ICLR 2025 10, ICML 2025 10,
  ECCV 2026 2, NeurIPS 2024 2; none in CVPR 2024-2025, ICCV 2025 or ECCV 2024. The topic grows sharply in 2026.
* ICML 2026 agent reproduction challenge: of the 26 ICML 2026 papers, 14 were attempted and 7 received a verified or
  falsified verdict.
* The first keyword screen was unreliable: 45 of its 95 matches were correct (precision 0.47), and it found only 45 of
  the 111 validated papers. Use `validated.csv`, not `papers.csv`.

## Limits

Titles and abstracts only; the candidate pool is itself keyword-based, so papers that never mention agents, LLMs or
research tasks in their abstract are missed. Labels come from language-model coders, validated against each other.
