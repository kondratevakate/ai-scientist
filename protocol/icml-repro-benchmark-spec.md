---
title: ICML-2026 AI-Scientist Reproduction Benchmark — Experiment Design Spec
created: 2026-08-04
authority: design-rationale + pre-registration
freshness: locked-for-42-run
repo: icml-repro (branch hermes-agentic-research) · paper: ai-scientist (this repo)
---

# ICML-2026 AI-Scientist Reproduction Benchmark — Experiment Design Spec

This document does two jobs:
1. **Records how we arrived at exactly this experiment design** (provenance / design rationale),
   so the method paper is honest about the iterative path.
2. **Pre-registers the locked protocol for the full 42-paper run**, so the scale-out is a
   confirmatory execution, not an ad-hoc fishing expedition.

Everything below is grounded in artifacts already in the repos; no result is invented.

---

## Part 1 — Design rationale: how we landed on this design

### 1.1 Attempt 1 — Opus 4.8, the `master` branch (the "AI Scientist review for paper reproduction" origin)

The project started as a direct **AI-Scientist reproduction attempt** using Claude **Opus 4.8**
on the `master` branch of `icml-repro`. The agent was asked to reproduce ICML-2026 submissions
from their claims, with the HF Spaces challenge (`ICML-2026-agent-repro`) as the serialization.

- Evidence (git): `master` head = *"Freeze judged results for the Claude (Opus) run:
  **63/136 over 13 judged logbooks**"*.
- What it established: a working scaffold (scaffold → work → validate → publish), the canonical
  logbook format, and the judge (`score_run.py`). It also surfaced the dominant failure modes
  (mutation-test absence, single-seed proof, toy substitutions, WebFetch-hallucinated specs) that
  later became the scoring rubric.
- What was weak: a **single architecture** (one agent, one model), so no architecture-comparison
  was possible — the run could not answer *"does agent design change reproduction quality?"*

### 1.2 Attempt 2 — Codex Sonnet, the `codex/medical-reproducibility-map` branch

A parallel track used **Codex (Sonnet)** on the `codex/medical-reproducibility-map` branch,
focused on the medical/clinical subset and a reproducibility map.

- Evidence (git): `codex/medical-reproducibility-map` head = *"Freeze judged results for the
  Codex run: **115/266 over 25 judged logbooks**, 10 unjudged (publish quota)"*.
- What it established: a second model/agent instance on the same claims, enlarging the judged
  corpus and the GT layer (`claims_anchored.json`, `corpus_all.json`, `audit_*.py`).
- What was still weak: still a **single architecture per run**; the two attempts differed in
  *both model and harness*, so any quality delta was confounded — could not isolate architecture
  from model.

### 1.3 Literature review — available skills and AI-Scientists for Hermes

Before building a third attempt, we reviewed (a) the **Hermes scientific-agent skills** available
to wire into an agent, and (b) the **AI-Scientist systems** in the literature, to choose an
architecture space worth comparing.

- Hermes skills: the K-Dense `scientific-agent-skills` layer (mutation-test / experiment /
  literature / writing / researchclaw / a-evolve / hypothesis / statistical-reporting / …) — the
  `06 Experiment design — 4 arms.md` documents that arm 2 = the same leaf agent **+ 9 K-Dense
  skills (9/9 valid)**, inherited from the profile. The comparison arm1 vs arm2 is a *scaffold
  ablation* (same agent + skills); arms 1/3/4 are *system-level* (different harness, same model).
- AI-Scientist landscape: Co-Scientist (Gemini multi-agent), and the challenge's own agent
  designs; the review concluded the defensible architecture axes for *our* benchmark are
  (i) bare leaf agent, (ii) leaf + scientific skills, (iii) a third-party AI-Scientist harness
  (Sakana), (iv) an autonomous-research-claw harness (ARC/AutoResearchClaw).

### 1.4 Attempt 3 — Hermes branch (`hermes-agentic-research`), the current benchmark design

The review produced the **4-arm design** on a **fixed model** (`tencent/hy3:free` via local router
`localhost:8319`) so that architecture — not model — is the varied factor. This is the design all
subsequent runs use, and the one pre-registered in Part 2.

**Why a fixed model (the key design decision):** Attempts 1 and 2 confounded model with harness.
Holding `hy3:free` constant across all 4 arms makes every measured delta an *architecture* effect.
Swapping the model mid-benchmark is forbidden — it would re-introduce the confound.

---

## Part 2 — The three nested empirical results (write-up order)

The paper is built **bottom-up**: one reproduction deep, then two ablation axes, then the whole.

### Result A — One reproduction, 4 arms (flagship: CAffNet `20hdQQQrA4`)

A single ICML-2026 paper reproduced by **all 4 arms**, so architecture differences are visible on
one fixed claim set.

- **Why CAffNet `20hdQQQrA4`:** it is the *only* paper with all 4 arms executed
  (`pilot_4arm/20hdQQQrA4_{arm1,arm2,arm3,arm4}`). It is the reference validation.
- **Full write-up + human-readable table:** `ai-scientist/synthesis/result-A-caffnet-4arm.md`.
  Machine-readable table regenerated from `_score.json` →
  `experiments/run03_hermes_leaf_pilot/docs/VALIDATION_TABLE_caffnet.csv`
  (the original `VALIDATION_TABLE.xlsx` was an empty stub — rebuilt).
- **Arms:**
  - arm1 — Hermes leaf (control)
  - arm2 — Hermes + 9 K-Dense scientific-agent-skills (primary workhorse)
  - arm3 — Sakana v2 harness (~7 h/paper, self-report overstates, crashes → documented
    non-viable at scale)
  - arm4 — AutoResearchClaw / ARC-light (did not execute on CAffNet → documented non-viable)
- **Recorded finding:** arm2 > arm1 on verified-claim rate; arm3/arm4 non-viable at scale
  (evidence in `pilot_4arm/20hdQQQrA4/_score.json` + `_run_meta.json`).

### Result B — Context compaction

Whether compressing the agent's context window (compaction) preserves reproduction quality.

- **Clean test:** CAffNet arm2 (no compaction) vs arm2b (compaction), *same prompt*.
  Result: **compaction WORSE** (arm2 = 4 verified + 1 inconclusive; arm2b = 3 verified +
  2 inconclusive → claim 4 regressed verified→inconclusive; `full_evidence_rate` 0.8→0.6).
- **Confounded test:** TBSyYj4VV6 arm2b also changed the *prompt* (v2.1 real-verification), so it
  is not a clean ablation (both original and arm2b = 6/6, but prompt covaries).
- **Full write-up + tables:** `ai-scientist/synthesis/result-B-compaction.md`.
- **Decision (locked, `DECISIONS.md` D2): compaction OFF** for the bundle. The rule rests on one
  clean data point (CAffNet); a 2nd clean compaction pilot is listed as optional before fully
  locking.

### Result C — Prompts v1 vs v2.1

The agent prompt evolved (v1 → v2.1 real-verification wording). Comparing runs across prompt
versions is a third result axis.

- v1 = original arm2 bundle prompts; v2.1 = `arm2_prompt_v2.1.txt` (real quantum-sim verification
  for TBSyYj4VV6, etc.).
- The `benchmark_v1_prefed/` (18 complete) and `benchmark_v1_arm2b/` (10 frozen) runs span these
  versions; the spec fixes *which* version applies to the full run (see Part 2 §3).

---

## Part 3 — Locked protocol for the full 42-paper run (pre-registration)

Executed ONLY after Parts 1–2 are written and this spec is frozen.

### 3.1 Stimulus set (frozen)
- **42 ICML-2026 papers** = `groundtruth/out/selected_for_runs.json` (the "alive" pool; extends
  only by adding new logbooks, not by dropping).
- 13 Clinical/EHR orids within it are benchmark *stimuli*, not hand-repro targets.

### 3.2 Model (frozen, non-negotiable)
- `tencent/hy3:free` via local router `localhost:8319`, **identical for all arms**. No mid-run
  model swap.

### 3.3 Arms (frozen)
- **arm2 (+skills) = primary executed arm** for the 42-paper scale-out.
- arm1 (leaf) = control comparison (subset, not all 42).
- arm3 (Sakana) / arm4 (ARC) = documented non-viable at scale; retained in the *design* for
  reference, **not** re-run on 42 (would waste compute for confirmed-failed harnesses).
- **Conditional re-run clause:** if we later need *more arms* (e.g. a 5th architecture) or an
  *accurate per-arm token count* (router `/v1/usage` was intermittently unavailable), we **re-run
  what we have** under the corrected condition rather than inferring — re-runs are cheap vs
  inventing.

### 3.4 Context compaction (frozen)
- **OFF** for all 42 runs (Decision D2).

### 3.5 Claim feed (frozen)
- **Pre-fed anchored claims = primary scored condition** (`claims_anchored.json`, judge-used).
- **Autonomous claim-extraction = RQ8 (OPEN)** — reported as a separate question, not mixed into
  the primary score. Promotion to a 5th axis requires building an `extraction-GT` layer in
  `corpus_all` first (documents the methodological critique: pre-fed measures execution, not
  comprehension/extraction — the step architectures actually differ on).

### 3.6 Prompt version (frozen)
- Full run uses **prompt v2.1** (real-verification wording) for arm2.

### 3.7 Judge + metrics (frozen)
- Judge = `score_run.py` reading `logbook.md` (universal row parser), NOT the JSON verdict field.
- Metrics: normalized validated score (points/available), full-evidence claim rate, false-full
  rate (agent said full, judge gave toy/inconclusive), execution success, claim coverage, wall
  time / CPU-hours / $, human-intervention minutes, calibration (Brier) over full-verdict
  probability.
- Canonical verdict vocabulary (case-insensitive, anywhere): `verified | supported | inconclusive
  | falsified`. Non-canonical (refuted/unsupported/partial/reproduced) → 0; fix by inserting
  `**Verdict: <Word>.**`.

### 3.8 Analysis plan (pre-registered)
- Primary: mixed-effects model with **arm** as fixed effect, **paper** and **claim type** as
  random effects (per `06 Experiment design — 4 arms.md` RQ7).
- Architecture effect = arm2 vs arm1 (scaffold ablation) on full-evidence rate.
- Ablation axes reported separately: compaction (B), prompt v1/v2.1 (C).
- Target N: 42 papers × arm2 (primary) + arm1 subset; power justified post-hoc from CAffNet
  pilot variance.

### 3.9 Hard rules (non-negotiable)
1. **Never invent a verdict.** `not attempted` / `not executed` / `not reproduced` stay truthful 0.
2. **HF Spaces:** EDIT existing `paper-<orid>` Space; never create a 2nd.
3. **No commit before validation; no push without permission.**
4. **Model fixed** at `hy3:free` — no swap.
5. **Trackio reproducibility:** every complete run has `logbook.md` + regenerable
   `.trackio/logbook/logbook.json` (`groundtruth/local_to_trackio.py <dir>`).

---

## Part 4 — Open items carried into the paper (not blocking the run)
- 45 `runs_incomplete/`: 10 salvageable (rewriter from `results/claimN.json`, verdicts from the
  agent's own JSON only) → fold into v1/v2.1 evidence; 35 empty shells → discard.
- 2nd clean compaction pilot (optional, before locking D2 fully).
- RQ8 `extraction-GT` layer (if promoting autonomous extraction to primary).
- Where the 42-run results append: this `ai-scientist` paper repo (synthesis) + mirrored as
  logbooks in `icml-repro`.
