---
title: "Session memo — 2026-08-04 (ICML-2026 repro benchmark: paper scaffolding)"
created: 2026-08-04
authority: handoff-support
freshness: as-of-end-of-session
---

# Session memo — 2026-08-04

Scope of this session: verify the new-agent handoff, then **scaffold the method paper** from the
existing experiments (no new runs executed). All numbers below are read from real artifacts
(`_score.json`, `verdicts_live.json`, `COMPACTION.md`), not invented.

## 1. What was accomplished

### 1a. Handoff verification + one bug fixed
- Gave Kate a 7-question checklist + a "fresh agent" prompt to prove the handoff works.
- Simulated agent answered all 7 correctly; I then **ran its proposed first command and caught a
  real bug**: it used `-maxdepth 2` but claim files live at depth 3 → returned 0 (a new agent
  would think "no salvageable runs"). Fixed the handoff to use `-maxdepth 3` (returns exactly 10).
- Committed `icml-repro` `7f8930a..8909c2e`.

### 1b. Experiment-design SPEC (provenance + locked 42-paper protocol)
- Kate: story starts Opus 4.8 (`master`) → Codex Sonnet (`codex/medical-reproducibility-map`) →
  Hermes skills/AI-Scientist literature review → Hermes branch (`hermes-agentic-research`).
- Verified the git reality: `master` = Opus run ("63/136 over 13 judged logbooks"); `codex` branch
  = Codex run ("115/266 over 25 judged logbooks"); `ai-scientist` repo exists with `protocol/`.
- Wrote `ai-scientist/protocol/icml-repro-benchmark-spec.md`: Part 1 = design rationale (the
  provenance chain + why each attempt changed the design); Part 2 = the 3 nested results (A/B/C);
  Part 3 = locked full-42 protocol (frozen stimulus set, fixed model, arms, compaction OFF,
  pre-fed primary / RQ8 open, prompt v2.1, judge, mixed-effects analysis plan, conditional re-run
  clause). Kate chose spec location = **both**: full spec in `ai-scientist`, short pointer in
  `icml-repro` HANDOFF.
- `ai-scientist` remote was HTTPS (push failed) → switched to SSH, pushed. `ai-scientist` `b2d88d3`.

### 1c. Result A — one reproduction × 4 arms (CAffNet `20hdQQQrA4`)
- Found `VALIDATION_TABLE.xlsx` was an **empty stub** (2 cols of opaque numbers, no labels).
  Rebuilt as `experiments/run03_hermes_leaf_pilot/docs/VALIDATION_TABLE_caffnet.csv` from
  `_score.json` (machine-checkable).
- Wrote `ai-scientist/synthesis/result-A-caffnet-4arm.md` with human-readable table.
  Computed full-ev: arm1 0.6 · **arm2 0.8** · arm3 0.8 (Sakana, non-viable ~7h) · arm4 0.2
  (exec FALSE) · arm2b 0.6.
- `ai-scientist` `cc79b59`; `icml-repro` `cf8396b`.

### 1d. Result B — context compaction
- CAffNet = **clean test** (same prompt): arm2 0.8 → arm2b 0.6, claim4 regressed V→Inc →
  **compaction WORSE** → D2 locked OFF.
- **TBSyYj4VV6 = confounded** (arm2b changed prompt v2.1 + real Grover sim, not just compaction)
  → documented honestly as NOT a clean ablation.
- Wrote `ai-scientist/synthesis/result-B-compaction.md`. `ai-scientist` `8a701a3`.

### 1e. Result D — features predicting low reproducibility (NEW, Kate's request)
- Ran real analysis on the full **6,627-paper challenge corpus** (`verdicts_live.json`, eval model
  `zai-org/GLM-5.2` — NOT our `hy3` benchmark; caveat stated in doc).
- Findings: **75.6% not fully reproduced**; **42.4% toy-contaminated**; verdicts verified 48% /
  inconclusive 26% / toy 21% / falsified 4%. Top failure modes: no public artifacts (89% fail,
  full-ev 0.11), scale mismatch (88.7% fail, 71% toy), toy/proxy substitution (82.4% fail, 70% toy).
- Prescriptive half: maps each failure mode to a design rule for OUR paper (ship runnable
  corpus+judge+Trackio; pin model/prompts/seeds; run full 42 scale; canonical verdict vocab;
  mandate mutation tests).
- Wrote `ai-scientist/synthesis/result-D-reproducibility-features.md`. `ai-scientist` `22adde0`.

### 1f. Result C — prompts v1 vs v2.1
- v1 permitted toy proxies; v2.1 mandates real verification, bans "toy" for math claims + "no paper
  body" excuse. All 18 prefed logbooks contain "toy" (v1 policy); TBSy arm2b has clean paired
  `logbook.md.bak_v1` (toy) → `logbook.md` (6/6 real Grover sim).
- Honest limitation: prompt version not logged per-run → no broad score table; v2.1 framed as the
  **intervention against D's #1 failure mode** (toy substitution) → why 42-run locks v2.1.
- Wrote `ai-scientist/synthesis/result-C-prompts-v1-v2.1.md`. `ai-scientist` `1b585fb`.

## 2. Bugs / data-quality issues found (carried to paper + spec)
- **arm2 `full_evidence_rate` field = 0.0 but per-claim = 4V+1Inc → true 0.8**. Miscomputed by an
  earlier `score_run.py`; the rubric-points fix corrected verdict mapping, the rate field still
  needs fixing before the 42-run.
- **Token counts unreliable**: all arms report `tokens_total_live ≈ 95.1M` flagged *"live snapshot
  only — no before/after"* → not a valid per-arm delta. → justifies spec's conditional re-run clause.
- **Handoff first-command maxdepth bug** (fixed, §1a).
- `VALIDATION_TABLE.xlsx` empty stub (rebuilt as CSV, §1c).
- `ai-scientist` remote was HTTPS → switched to SSH.

## 3. Files created this session
- `ai-scientist/protocol/icml-repro-benchmark-spec.md` (provenance + locked 42 protocol)
- `ai-scientist/synthesis/result-A-caffnet-4arm.md`
- `ai-scientist/synthesis/result-B-compaction.md`
- `ai-scientist/synthesis/result-C-prompts-v1-v2.1.md`
- `ai-scientist/synthesis/result-D-reproducibility-features.md`
- `ai-scientist/synthesis/SESSION_MEMO_2026-08-04.md` (this memo)
- `icml-repro/.../docs/VALIDATION_TABLE_caffnet.csv` (rebuilt validation table)
- `icml-repro/HANDOFF_NEW_AGENT.md` (pointer + branch labels: master=Opus, codex=Codex)
- `/tmp/repro_fix/resultD_features.py`, `/tmp/repro_fix/build_caffnet_table.py` (analysis scripts)

## 4. Commits pushed
- `ai-scientist` (main): `b2d88d3` → `cc79b59` → `8a701a3` → `22adde0` → `1b585fb`
- `icml-repro` (hermes-agentic-research): `8909c2e` → `6596068` → `cf8396b`

## 5. Open items for next session
- Recover the 10 salvageable `runs_incomplete/` runs (rewriter, verdicts from `results/`, never
  invent) → move to `benchmark_v1_prefed/`; discard 35 empty shells to `runs_discarded/`.
- Optional 2nd clean compaction pilot (prompt held) to firm up D2 (currently on 1 clean point).
- Build `extraction-GT` layer if promoting RQ8 (autonomous claim extraction) to primary.
- Fix `score_run.py` `full_evidence_rate` field bug.
- Write the **integrated full paper** narrative (the four results → method → benchmark validation).
- Decide whether to re-run for accurate token counts (conditional re-run clause).

## 6. Hard rules reaffirmed (never violate)
- Never invent verdicts; canonical words verified|supported|inconclusive|falsified.
- Never create a 2nd HF Space for an existing paper — EDIT `paper-<orid>`.
- Model held constant at `tencent/hy3:free` (localhost:8319); never swap mid-benchmark.
- No commit before validation; no push without permission.
- Data fetched on demand (HF/OpenML/URLs), NOT stored in git.
