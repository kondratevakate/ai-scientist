---
title: "Result D — What makes ICML-2026 submissions less reproducible, and how to harden our benchmark paper"
created: 2026-08-04
authority: results
freshness: draft
part-of: icml-repro-benchmark-spec (Part 2, new Result D)
---

# Result D — Features predicting low reproducibility, and reproducibility of our own paper

## 0. Provenance caveat (read first)

The empirical analysis below runs on **`verdicts_live.json` = the full ICML-2026 challenge
leaderboard: 6,627 attempted papers, 33,899 claims**, judged by the challenge's evaluation model
(`zai-org/GLM-5.2` per the file metadata). **This is NOT our `hy3:free` 4-arm benchmark** — it is
the broader population of all challenge reproduction attempts. We use it for *statistical power*
to characterize *which paper features predict low reproducibility*, then translate the findings
into design rules for **our** benchmark paper. Conclusions about "papers in general" come from
this corpus; conclusions about our benchmark come from the 4-arm / 42-paper work (Results A–C).

## 1. Population outcomes

| Metric | Value |
|---|---|
| Attempted papers | 6,627 |
| **Fully reproduced** (all claims verified) | **1,617 (24.4%)** |
| **Attempted but NOT fully reproduced** | **5,010 (75.6%)** |
| Toy-contaminated (≥1 claim = toy) | 2,813 (42.4%) |
| Mean full-evidence rate | 0.475 |
| Mean claims / paper | 5.12 |

Verdict mix across all 33,899 claims: **verified 48.3% · inconclusive 26.4% · toy 20.9% ·
falsified 4.4%**. So even in attempted reproductions, only ~half of claims reach verified, and
~1 in 5 is degraded to a toy-scale proxy.

## 2. Which features predict non-reproduction?

We classified each paper's judge `overall` commentary by failure-mode keywords (code/artifact
availability, toy/proxy substitution, scale mismatch, need for real data/video/SOTA baselines,
degeneracy). Association with outcome:

| Failure-mode feature | Papers | % not-fully-reproduced | % toy-contaminated | mean full-ev |
|---|---|---|---|---|
| no public artifacts (code/data/model) | 94 | **89.4%** | 7.4% | **0.11** |
| scale mismatch (proxy too small) | 97 | 88.7% | **71.1%** | 0.27 |
| data unavailable | 80 | 87.5% | 38.8% | 0.22 |
| **toy / proxy substitution** | 3,012 | 82.4% | **70.3%** | 0.39 |
| needs real data / video / SOTA baseline | 243 | 81.9% | 59.7% | 0.44 |
| code unavailable | 60 | 78.3% | 18.3% | 0.25 |
| degeneracy (chance-level / flipped result) | 40 | 67.5% | 50.0% | 0.54 |

**Reading:** the strongest predictors of failure are **absence of public artifacts** (code/data/
model) and **scale/proxy mismatch** — when the agent cannot obtain the paper's real pipeline, it
substitutes a small synthetic proxy, and the claim cannot be verified (toy rate jumps to 70%+).
Toy/proxy substitution is also the *most frequent* feature (3,012 papers, 45% of the corpus).

Claim-count association (secondary): papers with 1–2 claims show *lower* full-evidence (0.29)
than 5–6 claims (0.49) — likely a selection effect (few-claim papers are the risky/hard ones
agents attempt selectively), not evidence that fewer claims are inherently harder.

## 3. What this means for OUR benchmark paper (prescriptive)

The failure modes above are *agent-side* (the reproducing agent lacks artifacts / substitutes
proxies). But they map directly onto **design choices that make a benchmark paper itself
reproducible** — i.e. we must not repeat the same mistakes when publishing *our* method:

| Failure mode observed | Design rule for OUR paper |
|---|---|
| no public artifacts → 89% fail | **Ship all artifacts as runnable code**: the GT corpus (`corpus_all.json`, `claims_anchored.json`), the judge (`score_run.py`), and the Trackio regenerator (`local_to_trackio.py`) are committed and executable, not described. A reader must be able to `git clone` + run. |
| toy/proxy substitution → 70% toy | **Pin the exact environment**: fixed model (`tencent/hy3:free` via `localhost:8319`), fixed prompts (v2.1), `requirements.txt`, fixed seeds where stochastic. No "approximate" stand-ins for our own method. |
| scale mismatch | **Report at the real scale**: run the full 42-paper pool, not a 1–2 paper teaser; state N, compute power, wall-time. |
| data unavailable | **Separate data from code**: our repo holds code + metadata; datasets are URL-fetched and documented (HF/OpenML), so a reader can reproduce without opaque local files. |
| degeneracy / flipped result | **Mandate mutation tests + evidence boundaries** (from the scoring rubric) so a flipped/lucky result is caught, not published. |
| inconclusive 26% | **Canonical verdict vocabulary** (verified/supported/inconclusive/falsified) + require `**Verdict: <Word>.**` so judges and readers agree on what was claimed. |

In short: **a reproducible benchmark paper is one where the entire pipeline — corpus, judge,
logbook format, environment, and seeds — is re-runnable from a clone**, which is exactly what
the `HANDOFF_NEW_AGENT.md` + `SPEC` + Trackio format in this repo are designed to guarantee.

## 4. Limitations of this analysis

- The corpus is the **challenge leaderboard**, judged by `GLM-5.2`, not our `hy3` benchmark — the
  feature→outcome associations describe the challenge population, and we *extrapolate* them to our
  design rules (Section 3). They are not measured on our 4-arm runs.
- Failure-mode features are extracted by **keyword regex on free-text judge comments**; they are
  indicative, not a hand-labeled gold standard. A subset should be LLM/review-labeled to confirm.
- `toy` vs `inconclusive` vs `verified` boundaries depend on the challenge judge; our own judge
  (`score_run.py`) uses the same vocabulary but independent scoring.
