# ICML 2026 cross-map

Everything in this file is `VERIFIED` against local sources, unlike most of
`ICLR_AISTATS_MAP.md`. Provenance for each section is stated explicitly.

**Source for all paper rows:** `all_papers.csv` in `icml-repro-working`,
6341 rows, fields `orid, area, sub, type, spotlight, n_claims, max_pts, title,
authors, arxiv, openreview`. Points are `max_pts` as recorded there.

---

## 1. Survival, hazard, censoring

| orid | Pts | Title |
|---|---:|---|
| `3tlaoBZrSg` | 12 | Subgroup Discovery with the Cox Model |
| `Y9gsOEdaNE` | 4 | When Can We Trust Survival Model Evaluation? |
| `SldP4LGjdz` | 12 | Functional Decomposition and Shapley Interactions for Interpreting Survival Models |
| `0xJt4PqPJv` | 4 | Explicitly Modeling Censoring Produces Superior Survival Predictors |
| `wNL0qGb2MN` | 12 | FunCQNet: Functional Censored Quantile Neural Network, post-transplant kidney survival |
| `RKqL4GYXz3` | 12 | DPsurv: Dual-Prototype Evidential Fusion for WSI Survival Prediction |
| `TvLOddG9Ay` | 12 | Online Learning and Inference for Cox Proportional Hazards via Renewable Sieve Estimation |
| `LhGxRnGmGJ` | 12 | Accurate Evaluation of Quickest Changepoint Detectors via Non-parametric Survival Analysis |
| `boeY2syj2r` | 12 | SurvDiff: A Diffusion Model for Generating Synthetic Data in Survival Analysis (arXiv 2509.22352) |
| `8jViL8YrB1` | 4 | A Strictly Proper Scoring Rule and Calibration Metric for Interval-Censored Data |
| `wjsUR2vppX` | 4 | Discrete Survival Knowledge Distillation for Competing Risks Analysis |
| `WgrRyHYbo5` | — | Component-Wise Composite Likelihood Distillation for Censored Time-to-Event Data |

## 2. Trial-design machinery, found under other names

A full scan for trial vocabulary returns zero papers. These are the papers that
implement the mechanisms a platform trial actually needs.

| orid | Pts | Title | Trial mechanism |
|---|---:|---|---|
| `FXWnvznHMW` | 10 | Design-Based Anytime-Valid Inference for Randomized Experiments with Delayed Outcomes and Staggered Entry (arXiv 2603.25971) | Interim analyses, delayed endpoints, staggered site entry |
| `tUpQVC7LvO` | 10 | JADAI: Jointly Amortizing Adaptive Design and Bayesian Inference (arXiv 2512.22999) | Adaptive design, amortised so re-planning is instant |
| `Np7Y3AEVNq` | 12 | Budgeted Active Experimentation for Treatment Effect Estimation from Observational and Randomized Data (arXiv 2602.22021) | How much to randomise given routine data |
| `698yKwEXf0` | 12 | Personalized Policy Learning through Discrete Experimentation (arXiv 2602.05099) | Policy learning from experiments |
| `Q7lEZjtDKO` | 10 | Robust Sequential Experimental Design for A/B Testing (arXiv 2605.12899) | Sequential design with stopping |
| `mLZlTzepbr` | 10 | Modeling Covariate Transition for Longitudinal Treatment Effects in Randomized Experiments (arXiv 2605.31443) | Covariate drift within a trial |
| `S7mxhzgv5p` | 6 | Adaptively Grouped Contextual Bandits with Conformal Prediction | Response-adaptive randomisation with coverage |
| `srhmyF8k2w` | 6 | Nonlinear Covariate Balance in Experimental Design | Balance at randomisation |
| `1lKO23WFt8` | 4 | Minimax Approach for Optimal Intervention Policy Learning with Two-Stage Outcomes | SMART-style two-stage designs |
| `9kWVQtpvJi` | 10 | Learning Treatment Allocations with Risk Control Under Partial Identifiability (arXiv 2505.08378) | Validated on Tennessee STAR and the International Stroke Trial |

## 3. Digital twins and RL environments

| orid | Pts | Area | Title |
|---|---:|---|---|
| `BoQg93y6iT` | 12 | Reinforcement Learning | **Decision-Targeted Digital Twins** |
| `oWqRhYpJb6` | 12 | Applications | TwinWeaver: LLM-Based Foundation Model Framework for Pan-Cancer Digital Twins (GENIE, restricted) |
| `9GKURFWGeh` | 12 | Applications | Marrying Generative Model of Healthcare Events with Digital Twin of Social Determinants of Health (UK Biobank, restricted) |
| `kSUGLBHd0T` | 10 | Reinforcement Learning | Safety Generalization Under Distribution Shift in Safe RL: A Diabetes Testbed |
| `JLQV6NxS6W` | 12 | Deep Learning | RLAnything: Forge Environment, Policy, and Reward Model in a Dynamic RL System |
| `OvLnVkV14P` | 10 | Deep Learning | Agent World Model: Infinity Synthetic Environments for Agentic RL |
| `DRqjMnDQGq` | 12 | Deep Learning | RLVE: Scaling Up RL for Language Models with Adaptive Verifiable Environments |

## 4. Off-policy evaluation

| orid | Pts | Title |
|---|---:|---|
| `vpSFJoxyDz` | 10 | Off-Policy Evaluation for Missingness-Aware Policies in MDPs with Rewards MNAR |
| `IG956mtgzL` | 10 | Off-Policy Evaluation with Strategic Agents via Local Disclosure |
| `potpaozpjv` | 4 | Reward Shaping Control Variates for Off-Policy Evaluation Under Sparse Rewards |
| `srIStBTJiu` | 12 | Off-Policy Learning in Large Action Spaces: Optimization Matters More Than Estimation |

## 5. Synthetic data: generation, privacy, and collapse

| orid | Pts | Title | Why it matters here |
|---|---:|---|---|
| `kwvtSA9ed3` | 12 | Curated Synthetic Data Doesn't Have to Collapse: A Theoretical Study of Generative Retraining | Conditions under which training on synthetic data does not degrade a model |
| `boeY2syj2r` | 12 | SurvDiff | Joint generation of covariates, event times, and censoring |
| `aaFfUg013C` | 10 | EPSVec: Efficient and Private Synthetic Data Generation via Dataset Vectors | Private tabular synthesis |
| `KfLkjLH7s4` | 10 | FHAIM: Fully Homomorphic AIM for Private Tabular Synthetic Data Generation | Synthesis without the holder seeing the data |
| `73OIdmCkSh` | 6 | FedUSD: Unbiased Synthetic Data for Federated Learning | Multi-site synthesis |

## 6. Privacy audit and re-identification

| orid | Pts | Title |
|---|---:|---|
| `Kux5q1mL1x` | 10 | From Weak Cues to Real Identities: Evaluating Inference-Driven De-Anonymization in LLM Agents |
| `BSxSIzUPSZ` | 8 | Membership Inference Attacks for Unseen Classes |
| `QZlNaWuxO6` | 12 | Enhancing Membership Inference Attacks on Diffusion Models from a Frequency-Domain Perspective |
| `rSytT800kl` | 12 | How does Bayesian Sampling help Membership Inference Attacks? |
| `p3Cgr7EgTZ` | 6 | The Hidden Risk: Membership Inference Attacks on Multimodal Federated Learning |

## 7. Already reproduced locally

**Source:** publication preflight and report files in `icml-repro-working`,
plus published Hugging Face Spaces under `kondratevakate`.

| Target | orid | Outcome |
|---|---|---|
| Subgroup Discovery with the Cox Model | `3tlaoBZrSg` | Published 2026-07-29. C1 EPE properness VERIFIED (20-seed audit, KL identity error 2.2e-16), C2 recovery theorem VERIFIED, C4 Synth-Nonlinear VERIFIED on a fresh 10-seed run. C3, C5, C6 explicitly NOT ATTEMPTED. Locked forecast 5-6 of 12. |
| Explicitly Modeling Censoring (SALaD) | `0xJt4PqPJv` | REFUTED. On SUPPORT the SALaD variant loses to the plain baseline on 5 of 5 paired splits; on semi-SUPPORT it ties. Independently replicated on a disjoint seed base. Covers the N-MTLR layer only. |
| Off-Policy Evaluation with MNAR Rewards | `vpSFJoxyDz` | Published. C1 prepared as FALSIFIED AS WRITTEN via a constructive counterexample: a complete, relevant, positive one-stage MDP whose bridge coefficients are not square summable. |
| Learning Treatment Allocations with Risk Control | `9kWVQtpvJi` | Published. C1 Lemma 4.1 VERIFIED on 268,800 exact checks. C2 PARTIAL, Eq. (18) counterexample reproduced, finite-grid repair with zero failures over 1,396,054 UCB patterns. C4 STAR and C5 IST NOT ATTEMPTED, cohorts unavailable. |
| Conditional Coverage Diagnostics | `vaApZm6MKM` | Reproduced. With groups unspecified, CovGap reads 0.005 against a true 0.095; ERT recovers 92 percent. |
| When Can We Trust Survival Model Evaluation | `Y9gsOEdaNE` | Reproduced. Metric bias is mechanism dependent: IBS bias of −0.080 under administrative censoring, near zero under covariate-dependent censoring. Under 80 percent censoring, ranking agrees with the oracle in only 29 to 42 percent of cases. |
| Safe RL Diabetes Testbed | `kSUGLBHd0T` | Published. C3 requires training three models over a 24-step horizon, C5 requires a persistent Linux or GCP host. |

## 8. Local data, verified

**Source:** direct filesystem inspection and SHA-256 comparison, 2026-09-12.

| Dataset | State |
|---|---|
| MIMIC-IV-Note 2.2 | Complete. All four file hashes match the bundled `SHA256SUMS.txt`. Discharge table: 331,793 notes over 145,914 patients. |
| MIMICEL 2.1, MIMIC-IV-ED event log | Archive integrity verified. Contains `mimicel.csv` at 1.09 GB and `mimicel.xes` at 10.5 GB. |
| MIMIC-IV-Ext-CDM 1.1 | Present, unpacked. |
| METABRIC | Present in `cox_subgroup/data`, raw `metabric.h5` plus processed pickle, 78 MB total. |
| Sepsis event log, Hospital Billing log, BPIC 2011 hospital log, Synthea sample | Present and unpacked. |
| SleepEDF, OpenNeuro ds004504, CIFAR-100N, MFIDDR sample, MIMIC-III demo, MIMIC-IV-ED demo | Present. |
| MIMIC-IV core (`hosp`, `icu`), MIMIC-III v1.4, MIMIC-IV-ECG | **Absent.** The MLCI readiness scanner reports `status: blocked`, all four required tables missing, for both releases. No partial downloads exist anywhere on disk. |

## 9. Verified empty niches at ICML 2026

Scanned across all 6341 titles.

| Query | Hits |
|---|---|
| `clinical trial`, `randomised`, `RCT`, `platform trial` | 0 |
| `dose`, `dose-finding`, `phase II`, `phase III`, `interim`, `enrollment` | 0 |
| `vaccine`, `biomarker`, `sample size` | 0 |
| `process mining`, `event log`, `care pathway`, `patient flow` | 0 |
| `anonymi*` | 1 (`Kux5q1mL1x`, de-anonymisation by LLM agents) |

Separately, `PAPERS.md` records zero hits for `brain age`, `biological age`,
`chronological age`, `aging`, and `faceage`. That scan predates this map and was
not re-run here.

The gap between "zero papers named after clinical trials" and "ten papers
implementing trial machinery under other names" is the single most useful fact
in this map.
