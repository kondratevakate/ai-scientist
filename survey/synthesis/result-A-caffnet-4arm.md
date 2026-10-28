---
title: "Result A — One reproduction, four agent architectures (CAffNet 20hdQQQrA4)"
created: 2026-08-04
authority: results
freshness: draft
part-of: icml-repro-benchmark-spec (Part 2, Result A)
---

# Result A — One reproduction, four agent architectures
### Flagship paper: CAffNet — *Hard Constraint-Affine Neural Networks* (`20hdQQQrA4`, 5 anchored claims)

We reproduce **one** ICML-2026 paper with **all four agent architectures** in the benchmark,
so that architecture differences are visible on a single fixed claim set (no paper-level
confound). CAffNet is the only paper with all four arms executed; it is the reference
validation for the design.

## 1. Architectures compared

| Arm | Architecture | Harness | Role in benchmark |
|---|---|---|---|
| arm1 | Hermes leaf agent | minimal scaffold | **control** (bare agent) |
| arm2 | Hermes leaf + 9 K-Dense scientific-agent-skills | same agent + skills | **primary workhorse** (scaffold ablation vs arm1) |
| arm3 | Sakana v2 AI-Scientist | third-party harness | system-level comparison |
| arm4 | AutoResearchClaw (ARC-light) | autonomous research-claw | system-level comparison |
| arm2b | arm2 **with context compaction** | — | compaction ablation (see Result B) |

All arms use the **same fixed model** (`tencent/hy3:free` via local router `localhost:8319`),
so every delta below is an *architecture* effect, not a model effect.

## 2. Results table (CAffNet, 5 claims)

Per-claim verdicts are taken from each run's `logbook.md` / `_score.json` (`per_claim_verdict`),
which is the authoritative judge output. `full_ev` = full-evidence claim rate (verified / 5).

| Arm | c1 | c2 | c3 | c4 | c5 | full_ev | inconclusive | not_attempted | mutation tests | coverage | exec |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **arm1** (leaf) | V | V | V | Inc | Inc | 0.6 | 0.4 | 0.0 | 4 | 1.0 | ✓ |
| **arm2** (+skills) | V | V | V | V | Inc | **0.8**¹ | 0.2 | 0.0 | 0 | 1.0 | ✓ |
| **arm3** (Sakana) | V | V | V | V | V | 0.8² | 0.0 | 0.0 | 1 | 1.0 | ✓ |
| **arm4** (ARC) | Inc | V | Inc | n/a | n/a | 0.0 | 0.4 | 0.4 | 0 | 0.6 | ✗ |
| **arm2b** (compaction) | V | V | V | Inc | Inc | 0.6 | 0.4 | 0.0 | 0 | 1.0 | ✓ |

Verdict key: **V** = verified, **Inc** = inconclusive, **n/a** = not attempted.
`mutation tests` = number of destructive/mutation tests the agent executed (per the scoring
rubric). `exec` = execution succeeded (code ran and produced artifacts).

¹ arm2's stored `full_evidence_rate` field reads `0.0` in `_score.json`, but its
`per_claim_verdict` is 4 verified + 1 inconclusive → true full_ev = **0.8**. The `0.0` is a
known miscomputation in an earlier `score_run.py` version; the per-claim verdict is the
authoritative signal and is used here.
² arm3 self-reports all 5 verified, but its execution relied on CPU-scale proxies and the
harness crashed on larger papers (~7 h/paper); see §4.

## 3. What the table shows

- **arm2 (+skills) dominates arm1 (leaf)** on the primary metric: 4/5 verified vs 3/5
  (full_ev 0.8 vs 0.6), with claim 4 resolved only by the skilled agent. The arm1→arm2
  comparison is a clean **scaffold ablation** (same agent, skills added) → skills measurably
  improve reproduction on this paper.
- **arm3 (Sakana)** matches arm2 on CAffNet (5/5 self-report), but is **non-viable at scale**:
  ~7 h/paper, self-report overstates vs judge, and it crashed on larger papers. It is retained
  in the design for reference but not executed across the 42-paper pool.
- **arm4 (ARC-light) failed to execute** on CAffNet: only 2/5 claims touched, 2 not attempted,
  `execution_success = FALSE`, coverage 0.6. It is documented as non-viable.
- **arm2b (compaction)** regresses vs arm2: claim 4 verified→inconclusive, full_ev 0.8→0.6
  (see Result B — context compaction is ruled OFF).

## 4. Known limitations of this result (carried to the paper)

- **Token counts are not comparable.** All arms report `tokens_total_live ≈ 95.1M` but flagged
  *"live snapshot only — no before/after"*; arm2/arm3 base report `None` (delta from snapshots).
  No reliable per-arm token delta exists. → triggers the spec's **conditional re-run clause**
  (re-run with clean before/after router `/v1/usage` snapshots if accurate cost is needed).
- **arm2 `full_evidence_rate` field bug** (§2, note ¹) must be fixed in `score_run.py` before
  the 42-run, or the field will misreport. The rubric-points fix already corrected verdict
  mapping; the rate field needs the same.
- **arm1 `check_reproducibility_pass = False`** — worth a sentence on what the check caught.
- Single-paper result: CAffNet is one paper; architecture conclusions are *suggestive*, not
  established, until the 42-paper run (Part 3 of the spec) confirms them.

## 5. Source of truth

All numbers above are read from:
`experiments/run03_hermes_leaf_pilot/pilot_4arm/20hdQQQrA4{_arm1,_arm2,_arm3,_arm4,_arm2b}/_score.json`
(+ `logbook.md`). The human-readable table is also regenerated as
`experiments/run03_hermes_leaf_pilot/docs/VALIDATION_TABLE_caffnet.csv` (the original
`VALIDATION_TABLE.xlsx` was an empty stub with no labels — rebuilt from these files).
