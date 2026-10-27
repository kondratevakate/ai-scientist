# Handoff: five research ideas from the ICML 2026 reproduction assets

Written 2026-09-15. Read fully before acting. Chat with Kate in Russian (no dashes,
no plus signs in chat), write files and code in English. Do not publish, submit,
email, install packages, or download files without her explicit word. Kate runs
any PhysioNet authentication herself; never handle credentials.

Companion files in this folder: `HANDOFF_2026-09-13_censoring_yardstick.md`
(full plan for idea 1), `NOVELTY_CHECK_2026-09-13_censoring_yardstick.md`,
`ICML2026_CROSSMAP.md` (verified ICML map, local data, empty niches),
`ICLR_AISTATS_MAP.md`, `VERIFICATION_QUEUE.md`,
`REGULATORY_AND_2026_FACTCHECK.md`. Memory: `project-aistats2027-paper-planning.md`,
`project-cro-rl-environment-idea.md`, `reference-paper-verification-routes.md`.

---

## 0. Summary table

| # | Idea | Maturity on 2026-09-15 | Novelty | Best venue |
|---|---|---|---|---|
| 1 | Censoring Breaks the Yardstick | Gate run: GO by rule, with caveats; 100-seed exploratory probe done | Open but narrowed (Lillelund, Qi, Greiner) | AISTATS 2027: abstract 29 Sep, full 6 Oct 2026 AoE (verified) |
| 2 | Recovering Cox subgroups under right censoring | Uncensored Theorem 6.1 proof audited; no censored work yet | Gap is real, not searched in depth | ICML 2027: 16 / 22 Jan 2027 (aggregator dates, confirm on icml.cc) |
| 3 | Validation protocol for process-mined ED digital twins (MIMICEL) | Existing repo in phase 0; only Sepsis EDA executed | Positioned against 7 competitors in the repo (May 2026 map) | PODS4H 2027 at ICPM: abstract 11 Nov, paper 18 Nov 2026 (verified) |
| 4 | Decision-targeted RL environment or digital twin for trials and ED | Product scoping and regulatory fact-check only | Not checked | Depends on 1 or 3; no deadline chosen |
| 5 | Conditional coverage diagnostics | Paper reproduced (forecast 11 to 12 of 12) | **Headline finding is the paper's own claim; not novel as stated** | Only through an extension (5.3) |

ICLR 2027 (abstract 18 Sep, full 25 Sep 2026) is judged unrealistic for all five.

---

## 1. Censoring Breaks the Yardstick (target AISTATS 2027)

### 1.1 Claim
Standard fidelity metrics used to choose synthetic survival control arms are
computed on censored data. Their generator rankings disagree with an oracle
that sees true event times, and the disagreement grows with how prognostic the
censoring mechanism is.

### 1.2 Where everything is
- Code: `iclr_aistats/censoring_yardstick/` (`src/data.py`, `censoring.py`,
  `generators.py`, `gen_survivalgan.py`, `metrics.py`; `run_gate.py`,
  `analyze_gate.py`, `analyze_bias.py`, `probe_mechanism.py`,
  `analyze_probe.py`; `tests/test_invariants.py`; `env/*.sh`).
- Pre-registration with full deviations log: `PREREGISTRATION.md` (read Section 7).
- Results: `runs/gate/analysis.txt`, `runs/gate/analysis_bias_posthoc.txt`,
  `runs/probe/analysis_probe_posthoc.txt`, reruns in `runs/rerun/`.
- WSL venvs: `~/.venvs/cy-eval` (py3.12, sksurv 0.28, lifelines 0.30.3,
  numpy 2.5) and `~/.venvs/cy-gen` (py3.11, synthcity 0.2.12, torch 2.2.2 cpu).
  synthcity and scikit-survival cannot share a venv (numpy<2 vs numpy>=2).
  Run WSL commands through script files, not inline `bash -c` with `$VAR`.
- `workspace/` holds synthcity metric caches; not results.

### 1.3 Design as run
ACTG 320 (`load_aids(endpoint="aids")`, 1,151 patients, 574 vs 577, 96 events).
Weibull AFT oracle (Cox with Breslow gave absurd tails at 91.7% censoring).
Control arm censored at matched 60%: administrative, independent,
covariate-dependent (age), plus a 0% sanity cell. Generators trained on the
censored control arm: CART-SPD, SurvivalGAN (`n_iter=100`, 136 s per fit),
CoxBoot. Metrics computed ST (censored) and OR (oracle) on the same synthetic
set: `km_dist` (primary), `rmst_diff`, `hrd`, `tstr_cindex`, `tstr_ibs`.
10 seeds.

### 1.4 Results so far
Gate (confirmatory, 10 seeds), top-1 agreement between ST and OR best generator:

| Mechanism | km_dist | rmst_diff | hrd | tstr_cindex | tstr_ibs |
|---|---|---|---|---|---|
| none (0%) | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| administrative | 1.00 | 1.00 | 1.00 | 1.00 | 1.00 |
| independent | 0.80 | 0.90 | 0.80 | 0.90 | 0.80 |
| covariate-dependent | 0.60 | 0.60 | 0.60 | 1.00 | 0.90 |

Verdict: **GO by the literal rule.** Caveats recorded before further analysis:
(1) administrative agreement is a mathematical identity (horizon below `tau`);
between the two non-trivial mechanisms the spread is 0.2, under the 0.3
threshold; (2) SurvivalGAN is about 7x worse and never top-1, so every flip is
between near-tied CART-SPD and CoxBoot; (3) H2 is uninformative on ACTG 320
because the oracle trial is significant in 10 of 10 seeds.

Exploratory probe (100 seeds, cheap generators, censoring driven by noise, age,
or CD4 at strength 1 and 2), km_dist top-1 agreement:
independent 0.81, noise 0.73 / 0.80, age 0.67 / 0.50, **cd4 0.12 / 0.01**.
Direction: ST flatters CART-SPD (copies the joint censored distribution) and
penalises CoxBoot (assumes independent censoring). Differential gap at cd4
strength 2: +0.1454 [+0.1381, +0.1525]. `tstr_ibs` stays 0.81 to 0.90 across
drivers. Pre-committed P1 (destructive control) **failed as written** because
independent censoring itself has a small positive gap; P2 (dose) and P3
(ranking) held. Report P1 as failed. Probe is exploratory; a confirmatory claim
needs a new pre-registered run.

Bugs fixed during the probe (regression tests added): IBS grid past the largest
synthetic time; CoxBoot and `tstr` Cox fits diverging on degenerate dummies
(ridge fallback 0.1, 1, 10 only when non-finite); a silent `except ValueError:
nan` removed. Gate rows were scanned: 0 non-finite, unaffected.

### 1.5 Novelty position
Taken: metric bias under dependent censoring and the semi-synthetic oracle
recipe (Lillelund, Qi, Greiner, UAI 2026, arXiv 2502.19460, IBS-Dep,
`github.com/thecml/DependentEVAL`; Lillelund et al., Position "Stop Chasing the
C-index", ICML 2026 Spotlight, arXiv 2506.02075). Closest on trial validity:
Chassat et al., ML4H 2025, arXiv 2511.16551. **Corrected 2026-09-15:** they do
simulate independent vs covariate-conditional censoring (code in
`C:\Projects\data\refs\survgen-clinical-trials\utils\simulations.py`, dependent
`C` shares the event-time marker), but every metric is scored on censored data
and there is no oracle. General analogue: Kuo, Gallego, Jorm, arXiv
2606.08903. Our claim narrows to **ST vs OR ranking disagreement and
oracle-referenced trial conclusions**, not metric bias and not "varying the
mechanism". Residual risk: the Greiner group or the Chassat group could add an
oracle layer at any time; their simulated `dep` result CSVs could even be
re-scored if true times were saved (check before claiming they were not).

Reference code cloned 2026-09-15 to `C:\Projects\data\refs\`: survgen (commit
`14251eb`, no licence, 4.3 GB mostly simulation outputs), official
`Y9gsOEdaNE` code `When-Can-We-Trust-Survival-Model-Evaluation` (`796a5c8`, no
licence), independent repro `repro-survival-model-evaluation` (`9aed23a`, MIT),
`SurvDiff` (`025b352`, no licence), `SurvivalEVAL` (`ada4074`, GPL-3.0),
`DependentEVAL` (`b8e82d3`, MIT); PDFs in `refs\papers\`.

### 1.6 Next steps
1. New confirmatory pre-registration for the prognostic-censoring dose design
   (driver prognostic strength as the factor), written before running.
2. Add a dataset where the trial conclusion is borderline so H2 can bite
   (IST-1 at `C:\Projects\data\ist-1\IST_corrected.csv`: time `TD` in days,
   event `DIED`, latin-1, cohort 18,298; or ACTG 175 via CRAN `speff2trial`,
   needs R or a CSV export, ask before installing).
3. H3: compare IPCW-corrected metrics, IBS-Dep, and a censoring stress grid.
4. Reuse the Chassat et al. type I error and power protocol for H2.
5. Decide co-authors and a reciprocal reviewer before 29 Sep.

---

## 2. Recovering Cox subgroups under right censoring

### 2.1 Claim
Subgroup Discovery with the Cox Model (`3tlaoBZrSg`, ICML 2026) proves box
recovery (Theorem 6.1) only under **no censoring**. Extend the guarantee to
independent right censoring and show what breaks under covariate-dependent
censoring.

### 2.2 Assets
- Proof audit: `C:\Projects\02_academia\studies\icml\icml-repro-working\cox_subgroup\repro_cox_subgroup\THEOREM_6_1_AUDIT.md`,
  script `audit_theorem_6_1.py`, result `cox_subgroup/results/theorem_6_1.json`.
  Verdict VERIFIED under A1 to A5 (proportional hazards; no censoring; unique
  largest box with linear `h` inside; oracle core and coefficients; limiting CRS
  distribution). Two appendix typos: cites Lemma D.7 where D.6 is used; writes
  `vol(R* \ R_hat)` where `vol(R_hat \ R*)` is proved.
- Published reproduction (2026-07-29): C1 EPE properness, C2 recovery theorem,
  C4 Synth-Nonlinear verified; C3, C5, C6 not attempted.
- Data: METABRIC at `cox_subgroup/data/raw/metabric.h5` (not an RCT).

### 2.3 Where censoring enters the proof (from the audit steps)
1. Step 1 time change `u = Lambda_0(t)` makes times Exp(exp(h(x))); with
   censoring only `min(u, Lambda_0(C))` and the event flag are observed.
2. Steps 2 and 4 use exact exponential-tail quantiles of the CRS. Under
   censoring the late-failure tail is unobservable past the censoring time, so
   the late-tail rejection route weakens or disappears.
3. Step 3 needs `m >= c epsilon n` informative points per outer slab; censoring
   shrinks the effective sample toward events, so constants pick up
   `P(T <= C | x)`.

Working conjecture (unproved): under independent censoring with
`P(T <= C | x) >= pi_min > 0` on the support, the threshold stays
`O(log(1/epsilon))` with `n` effectively replaced by `pi_min n`; under
covariate-dependent censoring, recovery can fail at faces where censoring
concentrates.

### 2.4 Framing warnings (verified earlier, do not reopen)
- DDGroup finds regions where a Cox model fits; it is **prognostic** and uses no
  treatment variable. Do not frame as adaptive enrichment.
- Heterogeneous-Cox treatment subgroups already exist (Hu et al. 2020).

### 2.5 Next steps
1. Novelty search: subgroup discovery with censoring guarantees, box recovery
   for Cox under censoring (Consensus plus arXiv PDFs).
2. Simulation first: authors' synthetic setup with independent and
   covariate-dependent censoring at 30, 60, 80%; measure excess volume and
   containment rate. This decides whether the conjecture is worth proving.
3. Then the proof. Timeline fits ICML 2027, not AISTATS 2027.

---

## 3. Validation protocol for process-mined ED digital twins

### 3.1 Existing project (read first)
`C:\Projects\02_academia\studies\digitaltwin\` is a git repo (latest commit
"docs: pivot to validation-protocol claim for DT4H@MICCAI 2026"). Read
`README.md`, `docs/RESEARCH_DESIGN.md`, `docs/RESEARCH_PLAN.md`,
`docs/RELATED_WORK.md`, `docs/HYPOTHESIS_AND_REVIEW_AUDIT.md`,
`docs/AI_SCIENTIST_CONTEXT_HANDOFF.md`, `autoresearch/program.md`.
Its original venues (DT4H at MICCAI 2026, ProHealth at ICPM 2026) have passed.

### 3.2 Claim
When, why, and how far a process-mining-discovered simulator of ED operations
can be trusted for counterfactual policy evaluation, validated against an
independent doubly robust OPE estimator, with a Synthea positive control.

### 3.3 Hypotheses already in the repo
- H1 calibration: SIMOD plus Prosimos matches held-out LoS (EMD < 0.15),
  per-activity KS, path-frequency cosine; H1b: aggregate fit can hide stratum
  failure.
- H2 agreement: PM-DT and DR-OPE agree on at least 2 of 3 pre-registered
  policies; H2b predicts disagreement when policies touch hidden severity.
- H3 positive control on Synthea.

Open peer-review concerns from the audit (2026-06-05): no target-trial table
per policy; no separation contract between simulator features and causal
nuisance features; policies underspecified; H1 thresholds under-justified;
Synthea may not encode a real ground-truth policy value.

### 3.4 Data (verified 2026-09-12)
`C:\Projects\data\digitaltwin\`: MIMICEL 2.1 zip (integrity verified;
`mimicel.csv` 1.09 GB, `mimicel.xes` 10.5 GB), MIMIC-IV-ED demo 2.2 (222 stays),
Sepsis Cases log, BPIC 2011 hospital log, Hospital Billing log, Synthea sample
(1,171 patients). MIMICEL is PhysioNet credentialed: never commit it or push it
to a Space. Full MIMIC-IV-ED 2.2 tables and MIMIC-IV core are not on disk.

### 3.5 Positioning
ICML 2026 has 0 titles with `process mining`, `event log`, `care pathway`,
`patient flow`. Closest competitors listed in the repo: MDPI Appl Sci 2025 ED
fast track (PM plus simulation); npj Digit Med 2025 s41746-025-01738-4; Barón-Espitia
et al. 2024 PeerJ CS; Verboven and Martin 2022; Laudy 2026 arXiv 2604.01325;
Hao et al. 2025; Wei et al. 2025 (MIMICEL). Re-verify each before citing.

### 3.6 Next steps
1. Re-run the novelty search for 2026 publications (repo map is from May).
2. Write the target-trial table for the three policies before touching data.
3. Unzip only `mimicel.csv`; smoke test on 1,000 cases with timing.
4. Target PODS4H 2027: abstract 11 Nov, paper 18 Nov 2026.

---

## 4. Decision-targeted RL environment or digital twin for trials and ED

### 4.1 Idea
Turn the product scoping (RL environment on trial or ED data) into a research
artefact: an environment whose simulator is judged by the decisions it gets
right, not by fidelity. Two instantiations: (a) ED operations on top of idea 3's
calibrated simulator; (b) trial control arms on top of idea 1's generators,
with the reward tied to preserving the trial conclusion.

### 4.2 Anchors (ICML 2026 titles, verified in `all_papers.csv`)
`BoQg93y6iT` Decision-Targeted Digital Twins; `kSUGLBHd0T` Safe RL diabetes
testbed (Kate published a reproduction); `JLQV6NxS6W` RLAnything;
`OvLnVkV14P` Agent World Model; `DRqjMnDQGq` RLVE; OPE papers `vpSFJoxyDz`,
`IG956mtgzL`, `potpaozpjv`, `srIStBTJiu`. NeurIPS 2026 WMHS workshop (clinical
trial simulation) closed 15 Sep 2026 AoE.

### 4.3 Constraints already established
- CRO trial data belong to sponsors; derivative clauses usually cover synthetic
  data and trained weights. PhysioNet data cannot ship in a product; ship code
  and a build pipeline.
- PROCOVA is the only regulator-qualified digital-twin method (EMA 2022),
  continuous outcomes only. FDA Jan 2025 AI draft guidance excludes
  operational-efficiency AI. See `REGULATORY_AND_2026_FACTCHECK.md`.
- The MNAR OPE counterexample does not hit the qualified theorem; do not build
  on it.

### 4.4 Next steps
1. Read `BoQg93y6iT` primary PDF (curl plus PyMuPDF) and decide whether (a) or
   (b) is a genuine extension or a duplicate.
2. Novelty search: clinical trial RL environment; ED simulator benchmark with
   decision-focused evaluation.
3. Do not start independently; it needs a validated simulator from 1 or 3.

---

## 5. Conditional coverage diagnostics (`vaApZm6MKM`)

### 5.1 What exists
Braun, Holzmuller, Jordan, Bach, ICML 2026, arXiv 2512.11779. Reproduction
preflight: `C:\Projects\02_academia\studies\icml\icml-repro-working\ccd\PUBLICATION_PREFLIGHT_V2.md`,
script `ccd/verify_ert.py`, official experiments at commit `39a99dca`.
Space `kondratevakate/repro-conditional-coverage-diagnostics-for-conformal-prediction`.
Claims C1 to C6 PASS (C2 and C5 replay released outputs). Crossmap summary:
with groups unspecified CovGap reads 0.005 against a true 0.095; ERT recovers 92%.

### 5.2 Novelty verdict
**Not a paper as stated.** "ERT has more power than binning diagnostics such as
CovGap" is the paper's own claim (C1, C3); confirming it is reproduction, not
new work. The earlier suggestion of a short negative-result paper is withdrawn.

### 5.3 Possible extensions (unchecked, each needs a novelty search)
1. ERT for **censored outcomes**: conditional coverage of conformal survival
   sets, where `1[Y in C(X)]` is unobserved for censored rows; needs an IPCW or
   oracle version. Connects to ideas 1 and 2 and to Sesia et al. 2025 (LTT with
   IPCW for survival screening).
2. ERT as a reliability audit for MRI segmentation or brain-age intervals
   (IXI, SRPBS traveling subjects), fitting Kate's reliability line and ISBI
   2027 (4-page papers 26 Oct 2026).

### 5.4 Next steps
Search novelty for 5.3 item 1 first; if open, fold it into idea 1 as a section
or follow-up rather than a standalone paper.

---

## 6. Rules for the next session
- Verify every paper, venue and number against a primary source. OpenReview is
  bot-challenge blocked; use Consensus MCP, curl plus PyMuPDF, ClinicalTrials MCP.
- Pre-register thresholds before any confirmatory run; log deviations.
- Smoke test one item before loops; print s/item and total estimate; fail loudly.
- Clean, unhedged verdict sentences; caveats in a separate place.
- No silent `except` that returns NaN (bug found in the idea 1 probe).

## 7. First message for the next session
> Прочитай `C:\Projects\02_academia\icml-repro\iclr_aistats\HANDOFF_2026-09-15_five_ideas.md`. Работаем над идеей N. Перед установкой пакетов и скачиванием спроси меня.
