---
title: "Result B — Context compaction ablation (CAffNet clean test + TBSy confounded)"
created: 2026-08-04
authority: results
freshness: draft
part-of: icml-repro-benchmark-spec (Part 2, Result B)
---

# Result B — Does context compaction preserve reproduction quality?

**Question:** when the agent's context window is compressed (compaction) mid-run, does the
reproduction quality hold? We test this as an ablation: same paper, same prompt, same arm —
with vs without compaction.

## 1. Clean test — CAffNet `20hdQQQrA4` (arm2 vs arm2b)

This is the **only clean compaction comparison**: identical prompt and arm, compaction is the
single varied factor. Source: `pilot_4arm/20hdQQQrA4_arm2/` vs `pilot_4arm/20hdQQQrA4_arm2b/`
(`_score.json` + `logbook.md`).

| Claim | arm2 (no compaction) | arm2b (compaction) | Δ |
|---|---|---|---|
| c1 | V | V | = |
| c2 | V | V | = |
| c3 | V | V | = |
| c4 | **V** | **Inc** | ⚠ regressed |
| c5 | Inc | Inc | = |
| **full_ev (computed)** | **0.8** | **0.6** | **−0.2** |
| inconclusive rate | 0.2 | 0.4 | +0.2 |
| mutation tests | 0 | 0 | = |
| coverage | 1.0 | 1.0 | = |
| execution_success | ✓ | ✓ | = |

**Finding:** compaction **worsens** reproduction on this paper. Claim 4 drops from verified to
inconclusive — the agent simplified the verification under context pressure. Full-evidence rate
falls 0.8 → 0.6. → **Compaction is ruled OFF for the benchmark** (Decision D2).

## 2. Confounded test — TBSyYj4VV6 (NOT a clean ablation)

`TBSyYj4VV6_arm2b/` was a re-run that changed **two things at once**: compaction *and* the
verification method. Per its `COMPACTION.md`:

- The prior (v1) run had labelled the quantum *cost* half of every claim **"toy"** (it counted
  iterations of a classical rejection loop with a hardcoded formula).
- The arm2b re-run replaced that with a **REAL quantum amplitude-amplification simulation**
  (Grover iterate on a state vector), reproducing the Θ(1/√p) theorem by execution.
- Result: **6/6 VERIFIED** (real, not toy).

But the **baseline** (original TBSy arm2) lives in `runs_incomplete/TBSyYj4VV6` and has **no
finalized logbook** (it is one of the 45 incomplete runs; its v1 verdicts were the weak
"toy"-labelled ones). So we cannot compare "TBSy with vs without compaction" cleanly — the
arm2b also upgraded the verification from toy to real. Both endpoints happen to be high, but the
delta is attributed to **method + prompt (v2.1)**, not compaction alone.

| | arm2 (v1, toy-labelled, incomplete) | arm2b (v2.1, real quantum) |
|---|---|---|
| verdicts | incomplete (no logbook) | 6/6 V (real sim) |
| what changed | — | compaction **+** verification method **+** prompt v2.1 |
| isolates compaction? | — | **NO — confounded** |

**Conclusion from TBSy:** inconclusive for the compaction question. It shows the v2.1
real-verification method is strong (6/6), but cannot separate that from compaction.

## 3. Decision and limitation

- **Locked decision (D2): compaction OFF** for the benchmark bundle, based on the **one clean
  data point** (CAffNet). The confounded TBSy case neither supports nor overturns it.
- **Limitation:** the rule rests on a single clean paper. A **2nd clean compaction pilot**
  (prompt held constant, only compaction varied — on a different paper) is listed as *optional*
  in the spec before fully locking D2. TBSyYj4VV6 would need a clean re-run (prompt held) to
  contribute a second clean point.
- Both CAffNet arm2 and arm2b show `n_mutation_tests = 0` — neither executed destructive
  mutation tests, a separate scoring gap noted in Result A.

## 4. Source of truth

- Clean: `pilot_4arm/20hdQQQrA4_arm2/_score.json`, `pilot_4arm/20hdQQQrA4_arm2b/_score.json`.
- Confounded: `benchmark_v1_arm2b/TBSyYj4VV6_arm2b/COMPACTION.md` (no `_score.json`; baseline
  in `runs_incomplete/TBSyYj4VV6` is unfinalized).
