---
title: "Result C — Agent prompt evolution: v1 (toy-permitting) vs v2.1 (real-verification)"
created: 2026-08-04
authority: results
freshness: draft
part-of: icml-repro-benchmark-spec (Part 2, Result C)
---

# Result C — Prompt evolution: v1 (toy-permitting) vs v2.1 (real-verification)

**Question:** does the agent *prompt* design change reproduction quality? We compare the two
prompt generations used across the benchmark runs.

## 1. What changed between v1 and v2.1

The v2.1 prompt (`arm2_prompt_v2.1.txt`, dated 2026-08-03) refines the v1 bundle-2 prompt.
The material differences:

| Aspect | v1 (bundle-2 prompt) | v2.1 |
|---|---|---|
| Empirical claims | allows a **toy / reduced-scale CPU run** as "honest best effort" | toy still allowed *for empirical* claims, but… |
| Mathematical claims (bound/identity/theorem) | sometimes marked "toy" | **must be verified for real** on CPU (numerical check or independent re-derivation); **never "toy"** |
| "No access to paper body" | could surface as a verdict excuse | **explicitly banned** as a bare excuse — agent must fetch the PDF / fix the blocker itself |
| Context compaction | (COMPACTION.md mandated) | COMPACTION.md mandated; raw numbers preserved verbatim |

In short: **v1 permitted toy-scale proxies; v2.1 pushes REAL verification** and removes the
easy "can't access / toy" escape hatches.

## 2. Population signal (honest scope)

Prompt version was **not logged as a field** in `_run_meta.json`, so we cannot do a clean
per-paper v1-vs-v2.1 score comparison across all runs. But two pieces of real evidence locate
the versions:

- **All 18 `benchmark_v1_prefed/` runs contain "toy" claims** in their logbooks (per-logbook
  toy-mention counts: 1KRpajnd6u 3, 4ltyJqAHMg 2, 9uENnRAcSl 6, MyBVUgacQ9 8, LJdacnMXkr 4,
  arc2pWtZLN 4, …; none use v2.1 "real verification" language). → these ran under the **v1
  toy-permitting policy**.
- **v2.1 is exemplified by TBSyYj4VV6 arm2b**, which has both `logbook.md` (v2.1 real run) and
  `logbook.md.bak_v1` (the prior v1 toy-labelled run) — a clean **paired before/after**.

## 3. The clean paired example — TBSyYj4VV6

`TBSyYj4VV6_arm2b/COMPACTION.md` + `logbook.md.bak_v1` document the transition:

| | v1 (`logbook.md.bak_v1`) | v2.1 (`logbook.md`) |
|---|---|---|
| quantum *cost* half of each claim | labelled **"toy"** (counted iterations of a *classical* rejection loop with a hardcoded formula) | **REAL** Grover amplitude-amplification state-vector simulation; reproduces Θ(1/√p) theorem by execution |
| verdicts | weaker / toy-labelled | **6/6 VERIFIED** (real, not toy) |
| what changed | — | verification method + prompt (v2.1) |

Note: TBSy arm2b also changed compaction (Result B) — so it is **not a pure prompt ablation**,
but the `bak_v1`→v2.1 logbook pair isolates the *prompt/verification* improvement: the v1 run
degraded mathematical claims to "toy"; v2.1 verified them by actually executing the quantum
algorithm.

## 4. Why this matters — link to Result D

Result D showed **toy/proxy substitution is the #1 reproducibility killer** (70% toy rate where
the agent lacks the paper's real artifacts; toy-contamination present in 42% of all attempted
papers). **v2.1 is the intervention that attacks exactly that failure mode** at the prompt level:
by forbidding "toy" for mathematical claims and banning the "no paper body" excuse, it forces
real verification instead of proxy substitution.

This is why the **locked full-42 protocol (spec Part 3 §3.6) mandates prompt v2.1**: the prompt
generation is itself a reproducibility control, not a cosmetic choice.

## 5. Limitations

- No per-run `prompt_version` field → no broad v1-vs-v2.1 score table; the population signal is
  the toy-mention presence in all 18 prefed logbooks + the single paired TBSy example.
- The TBSy pair is confounded with compaction (Result B); only the `bak_v1`→v2.1 logbook delta
  isolates the prompt effect.
- "toy" mention counts are a proxy, not a verdict diff — they indicate v1 policy usage, not the
  precise v1-v2.1 score delta per paper.
