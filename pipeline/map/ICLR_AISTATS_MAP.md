# ICLR / AISTATS map: health AI, trials, survival, conformal, privacy

Status legend and verification protocol: see `README.md`.

## Verification tally, 2026-09-12

All 26 rows seeded from secondary summaries were checked by title through
Consensus and Semantic Scholar. OpenReview itself could not be queried.

| Outcome | Count | Rows |
|---|---:|---|
| Venue confirmed as ICLR or AISTATS | **2** | Semiparametric Conformal Prediction (AISTATS 2025); Conformal Structured Prediction (ICLR) |
| Paper exists, published at a **different** venue | 5 | Proper Scoring Rules for Survival (ICML 2023); DySurv (JAMIA 2024); TrialDura (ACM BCB 2024); Retrieval-Reasoning Synthetic Trials (ACM BCB); Temporal Visiting-Monitoring (Knowledge-Based Systems 2025) |
| Paper exists, venue still unconfirmed | 11 | COMPASS, PyTrial, Context Clues, Dynamic Survival Analysis, Deep Extended Hazard, CP Masks, Fair CP, Morphological CP, EHRMIND, SlotSPE, AIR-Bench 2024 |
| Title was wrong in the source | 2 | "Outcome" is really TrialDura, **duration** prediction; "Morphological Operations" is really **Morphological Prediction Sets** |
| **Not found under the claimed title** | **8** | Conformalized Survival Analysis for General Right-Censored Data; Conformalized Survival Counterfactuals; Privacy-Protected Causal Survival; ICALD (predecessor exists); LongSurv; Simpler Calibration for Survival; Bayesian Networks for Individual Survival; HeLoM |

Not found is not proof of fabrication: recent or withdrawn submissions may be
unindexed. But none of the eight may be cited until seen on OpenReview.

Added from own research, not from the summaries: **SurvivalGAN, AISTATS 2023**,
venue confirmed through DBLP and PMLR v206. Regulatory and 2026 industry claims
are checked separately in `REGULATORY_AND_2026_FACTCHECK.md`.

Rule for use: cite only rows marked `VERIFIED` with a stated venue, and use
the venue in the `Evidence` column, not the claimed one.

---

## Cluster A. Conformal prediction plus survival

The densest overlap with the ICML 2026 survival work already reproduced locally.

| Paper | Claimed venue | Claimed ID | Status | Evidence | Link to own work |
|---|---|---|---|---|---|
| Conformalized Survival Analysis for General Right-Censored Data | ICLR 2025 poster | `JQtuCumAFD` | UNVERIFIED | Consensus 2026-09-12: exact title not found. Nearest real work: Candès et al. 2021, "Conformalized Survival Analysis" (JRSSB, type-I censoring); Sesia et al. 2024, "Doubly Robust Conformalized Survival Analysis with Right-Censored Data" (arXiv); Qin et al. 2024, bootstrap conformal intervals for general right-censored data (Biometrics). The claimed paper may be one of these under a different title. | FunCQNet `wNL0qGb2MN`, censored quantile regression on the same task |
| Conformalized Survival Counterfactuals Prediction for General Right-Censored Data | ICLR 2026 poster | `1j0ormf8uI` | UNVERIFIED | Consensus 2026-09-12: exact title not found. Nearest: Sesia et al. 2024 (weighted conformal inference, right-censored, arXiv); Yi et al. 2025, "Survival Conformal Prediction Under Random Censoring" (Stat); Shin et al. 2025, "Weighted Conformal Prediction for Survival Analysis under Covariate Shift". Also not arXiv 2411.02114, see conflicts. | Treatment Allocations with Risk Control `9kWVQtpvJi` |
| Privacy-Protected Causal Survival Analysis Under Distribution Shift | ICLR 2026 poster | `aTxnsFFO7t` | UNVERIFIED | Consensus 2026-09-12: exact title not found. Nearest real work: FedPseudo, federated survival with differential privacy (KDD 2023); Han et al. 2023, "Multiply Robust Federated Estimation of Targeted Average Treatment Effects" (arXiv); Guo et al. 2024, "Collaborative Heterogeneous Causal Inference Beyond Meta-analysis". The topic is real; the specific paper is unconfirmed. | No ICML counterpart found. Open gap. |
| Learning Survival Distributions with Individually Calibrated ALD (ICALD) | ICLR 2026 submission | `frv3s3AtUD` | UNVERIFIED (predecessor VERIFIED) | Consensus 2026-09-12: the "individually calibrated" version was not found, but its evident predecessor exists: Deming Sheng et al. 2025, "Learning Survival Distributions with the Asymmetric Laplace Distribution" (PMLR). Related: Shi-ang Qi et al. 2024, "Toward Conditional Distribution Calibration in Survival Prediction" (conformal, 15 datasets), same first author as SALaD. | DPsurv `RKqL4GYXz3`, SurvFD `SldP4LGjdz`; SALaD `0xJt4PqPJv` shares the Qi and Greiner group |
| Proper Scoring Rules for Survival Analysis | ICLR 2023 submission (claimed) | `Xj9V-stmIcO` | **CONFLICT** (venue) | Semantic Scholar 2026-09-12: paper exists, indexed as **ICML 2023**, arXiv 2305.00621. ICLR 2023 submission not confirmed. Cite as ICML 2023 unless the OpenReview page shows otherwise. | When Can We Trust Survival Model Evaluation `Y9gsOEdaNE` (direct polemic) |
| Simpler Calibration for Survival Analysis | ICLR 2022 submission | `8hkf29PXCn` | **CONFLICT**, title not found | Same ID also claimed for EHRMIND. Consensus 2026-09-12: no paper under this title. EHRMIND, the other claimant, does exist, so the ID more plausibly belongs to it. Real calibration anchors: X-CAL, Goldstein et al., NeurIPS 2020 (MIMIC-III length of stay, TCGA brain cancer); Austin et al. 2020, calibration curves and ICI for survival models (Statistics in Medicine). | Same as above |

## Cluster B. Conformal prediction, method and imaging

| Paper | Claimed venue | Claimed ID | Status | Evidence | Link to own work |
|---|---|---|---|---|---|
| COMPASS: Robust Feature Conformal Prediction for Medical Segmentation Metrics | ICLR 2026 poster (claimed) | virtual `10006913` | **CONFLICT** (ID) / title VERIFIED | Consensus 2026-09-12: paper exists, Matt Y. Cheung et al., 2025, arXiv. Four medical segmentation tasks, area estimation of skin lesions and anatomical structures, coverage recovered under covariate shift. ICLR 2026 acceptance not confirmed. Virtual ID still collides with LongSurv. | uqct `a6vCNSBBeq`, TCSeg `bGxMpQsIuN`, Med-SegLens `vaRFU0xKQa`. Closest match to the segmentation-metric-reliability track. |
| Conformal Prediction Masks: Visualizing Uncertainty in Medical Imaging | ICLR 2023 TML4H workshop (claimed) | `J4QatK02Qc` | VERIFIED (title) | Consensus 2026-09-12: Gilad Kutiel et al., 2023, 25 citations. **Caveat:** the abstract evaluates on colorisation, completion, and super-resolution, not on named medical datasets. Medical imaging is the motivation in the title, not the demonstrated application. Workshop venue unconfirmed. | DC-PnPDP `jEBkuuETjr`, EviScreen `FCVPVqRLDJ` |
| Semiparametric Conformal Prediction (vine copulas) | AISTATS 2025 | arXiv 2411.02114 | VERIFIED | Semantic Scholar 2026-09-12: venue AISTATS, 2025; arXiv 2411.02114 | Multi-Distribution Robust CP `Vv4XRZDMM0`, Stable Localized CP `lSMTccAN61` |
| Conformal Structured Prediction | ICLR 2025 | `2ATD8a8P3C` (ID not checked) | VERIFIED (title, venue) | Semantic Scholar 2026-09-12: venue ICLR; arXiv 2410.06296 (Oct 2024). OpenReview ID still unchecked. | Coverage-Length Metric critique `r3h23Jv26a`, ROCP `VAXW59dyfk` |
| Fair Conformal Predictors for Applications in Medical Imaging | AAAI 2022 (claimed) | — | EXTERNAL, title VERIFIED | Consensus 2026-09-12: Charles Lu et al., 2021 record, 108 citations. Radiologist field interviews, skin-lesion classification, equalised coverage across skin tones. AAAI 2022 venue not confirmed by this source. Not ICLR or AISTATS. | Conditional Coverage Diagnostics `vaApZm6MKM` (reproduced: CovGap reads 0.005 against a true 0.095 when groups are unspecified) |
| Conformal Prediction for Image Segmentation Using **Morphological Prediction Sets** | MICCAI 2025 (claimed) | — | EXTERNAL, title CORRECTED | Consensus 2026-09-12: real title ends "Morphological Prediction Sets", not "Morphological Operations". Luca Mossina et al., 2025, 20 citations. Dilation margin around predicted binary masks, several medical imaging applications. MICCAI venue not confirmed. Not ICLR or AISTATS. | Same segmentation-reliability line |

## Cluster C. Deep hazard, ICU, EHR survival

| Paper | Claimed venue | Claimed ID | Status | Evidence | Link to own work |
|---|---|---|---|---|---|
| Dynamic Survival Analysis for Early Event Prediction | ICLR virtual 2024 or 2025 (claimed) | — | VERIFIED (title) | Consensus 2026-09-12: Hugo Yèche et al., 2024, arXiv. Risk localisation integrated into alarm policies, up to 11% AuPRC gain at event level, matching the source summary. Conference and year still unconfirmed. | PathwayLLM `oB7gZX7MKP`, Time-Conditioned Foreseeing `IalpB5Mzaz`. Uses HiRID, which needs contributor-review access. |
| DySurv: Dynamic Deep Learning Model for Survival Prediction in the ICU | OpenReview (claimed) | `kDbD2GkLfy` | VERIFIED (title) / published EXTERNAL | Consensus 2026-09-12: Mesinovic et al., arXiv 2023. Journal version: "DySurv: dynamic deep learning model for survival analysis with conditional variational inference", **JAMIA 2024**, evaluated on 6 benchmarks plus eICU and MIMIC-IV. Cite the JAMIA version, not an ICLR one. | MedMamba `qPqJH0heR0` |
| Deep Extended Hazard Models for Survival Analysis | OpenReview (claimed) | `GUD7rNkaWKr` | VERIFIED (title) | Consensus 2026-09-12: Qixian Zhong et al., 2021, 61 citations, venue not given. DeepEH subsumes DeepSurv and DeepAFT, with consistency and convergence-rate results. The "gene expression plus clinical features" detail in the source summary is not in the abstract and stays unconfirmed. | COLSA `TvLOddG9Ay` |
| LongSurv: Bridging Short-Term Data and Causal Long-Term Survival | OpenReview | `5kinne2hCb` | UNVERIFIED | Consensus 2026-09-12: not found under this title. The underlying problem is established in health technology assessment: Jackson 2016, "Extrapolating Survival from Randomized Trials Using External Data" (Medical Decision Making review); Jackson 2023, survextrap R package (BMC Medical Research Methodology); Timmins et al. 2026 simulation study (Medical Decision Making). These are the citable anchors for trial survival extrapolation regardless of LongSurv. | FunCQNet `wNL0qGb2MN`, long-term endpoint extrapolation |
| Structural Prognostic Event Modeling for Multimodal Cancer Survival (SlotSPE) | OpenReview (claimed) | `WqCRSn2WAY` | VERIFIED (title) | Consensus 2026-09-12: Yilan Zhang et al., arXiv 2025. Slot attention over histology plus gene profiles; beats baselines in 8 of 10 cancer cohorts, +2.9% overall; robust to missing genomics. Venue unconfirmed. | DPsurv `RKqL4GYXz3` |
| SurvivalGAN: Generating Time-to-Event Data for Survival Analysis | **AISTATS 2023** | PMLR v206 | VERIFIED | Own research 2026-09-12: DBLP record `conf/aistats/NorcliffeCILS23`, PMLR v206 pp. 10279-10304. Norcliffe, Cebere, Imrie, Liò, van der Schaar. Three survival-specific generative failure modes and metrics; plugin in the `synthcity` library. Refutes the claim that SurvDiff was the first survival-specific generator. | SurvDiff `boeY2syj2r`; synthetic cohort module for the CRO product |
| Bayesian Networks Framework for Estimating Individual Survival | OpenReview | `UAM4Kvab4z` | UNVERIFIED | Consensus 2026-09-12: not found under this title. Nearest: Sheidaei et al. 2022, dynamic Bayesian network for survival data (BMC Medical Informatics and Decision Making). **New verified find in the same search:** SurvivalPFN, Shi-ang Qi et al., arXiv 2026, prior-data fitted network amortising survival inference in one forward pass, benchmarked on 61 datasets, 21 methods, 5 metrics; code github.com/rgklab/SurvivalPFN. Same first author as SALaD. | SurvFD `SldP4LGjdz`; SALaD `0xJt4PqPJv` (SurvivalPFN) |

## Cluster D. EHR foundation models and clinical prediction

| Paper | Claimed venue | Claimed ID | Status | Evidence | Link to own work |
|---|---|---|---|---|---|
| Context Clues: Long Context Models for Clinical Prediction on EHR (EHRSHOT) | ICLR 2025 poster (claimed) | `zg3ec1TdAP` | VERIFIED (title) | Consensus 2026-09-12: Michael Wornow et al., arXiv 2024 plus a separate 2025 record consistent with a conference version. Mamba-based model beats prior state of the art on 9 of 14 EHRSHOT tasks. Code: github.com/som-shahlab/long_context_clues. ICLR 2025 not directly confirmed. | PyHealth 2.0 `gMLVFN9hl8`, benchmark against benchmark |
| HeLoM: Progressive Disease Detection with Longitudinal EHRs via Memory-Augmented LLMs | ICLR 2026 withdrawn | `VBMdD2owBe` | UNVERIFIED | Consensus 2026-09-12: not found. Nearest real work: CPLLM, Ben Shoham and Rappoport, PLOS Digital Health; EHR-KnowGen, Niu et al. 2024, Information Fusion. Essential context: Wornow et al. 2023, "The shaky foundations of large language models and foundation models for electronic health records", npj Digital Medicine, review of 84 EHR foundation models. | MLCI `C6ZTjSXbz7` |
| Temporal Visiting-Monitoring Feature Interaction Learning for Modelling Structured EHRs | ICLR 2025 submission (claimed) | `HmmN0Mxze7` | VERIFIED (title) / published EXTERNAL | Consensus 2026-09-12: Xiang Li et al., **Knowledge-Based Systems 2025**. Cite the journal version. Any ICLR submission history is unconfirmed. | MedMamba `qPqJH0heR0` |

## Cluster E. Clinical trials and trial informatics

| Paper | Claimed venue | Claimed ID | Status | Evidence | Link to own work |
|---|---|---|---|---|---|
| PyTrial: ML Software and Benchmark for Clinical Trial Applications | ICLR 2024 submission, withdrawn (claimed) | `5vY0HNpy9F` | VERIFIED (title) | Consensus 2026-09-12: Zifeng Wang et al., 2023, no journal (consistent with an unpublished submission); 34 algorithms, 6 tasks, 23 datasets. Companion arXiv "PyTrial: A Comprehensive Platform for AI for Drug Development". Code: github.com/RyanWangZf/PyTrial. Withdrawn status and OpenReview ID unchecked. | PyHealth 2.0 `gMLVFN9hl8`. Closest structural analogue: toolkit plus benchmark. |
| TrialDura: Hierarchical Attention Transformer for Interpretable Clinical Trial **Duration** Prediction | OpenReview (claimed) | `2xmqiebwgY` | EXTERNAL, title CORRECTED | Consensus 2026-09-12: the source summary said "Outcome"; the real paper predicts **duration**. Ling Yue et al., ACM BCB 2024. Bio-BERT embeddings over disease, drug molecules, phase, eligibility criteria; MAE 1.04 years. Code: github.com/LeoYML/TrialDura. Not ICLR. | No ICML counterpart |
| Retrieval-Reasoning LLM-Based Synthetic Clinical Trial Generation | ICLR 2025 withdrawn (claimed) | `EdAgWYEFc1` | VERIFIED (title) / published EXTERNAL | Consensus 2026-09-12: Zerui Xu et al., **ACM BCB** (16th conference). Synthetic ClinicalTrials.gov reports with success or failure labels; hybrid real plus synthetic fine-tuning of BioBERT improves trial outcome prediction. Code: github.com/XuZR3x/Retrieval_Reasoning_Clinical_Trial_Generation. Adjacent and heavily cited: TrialGPT, Jin et al., Nature Communications 2023, zero-shot patient-to-trial matching, 42.6% screening-time reduction in a user study. | SurvDiff `boeY2syj2r` (synthetic survival cohorts) |
| Training LLMs for EHR-Based Reasoning Tasks via RL (EHRMIND) | OpenReview, possibly ICLR 2026 (claimed) | `8hkf29PXCn` | VERIFIED (title) / ID CONFLICT | Consensus 2026-09-12: Jia-Cheng Lin et al., arXiv 2025. SFT warm-up then RL with verifiable rewards; tasks MEDCALC, TREC Clinical Trials patient-trial matching, EHRSHOT diagnosis. Venue unconfirmed. Sibling work also exists: EAG-RL, Yue Fang et al., arXiv 2025, expert attention guidance, +14.62% average on two EHR datasets. | Diabetes Safety testbed `kSUGLBHd0T` |

## Cluster F. Process mining plus healthcare

ICML 2026 contains zero process-mining papers. Verified by a full title scan of
all 6341 entries in `all_papers.csv` against `process mining`, `event log`,
`care pathway`, `patient flow`. This is the clearest open niche.

| Work | Venue | Status | Note |
|---|---|---|---|
| Process mining plus deep learning for COVID-19 survival in hospitalised patients | Biomedical journal, PMC9309593 | EXTERNAL | Mortality predicted in 6-hour windows over the first 72 hours, AUROC above 0.8 |
| Process mining in healthcare, tertiary study | Springer | EXTERNAL | Domain background |
| Process mining for healthcare: characteristics and challenges | ScienceDirect | EXTERNAL | Heterogeneous logs, privacy |
| Reengineering care pathways through quantitative process analytics | Journal | EXTERNAL | Process mining plus discrete-event simulation |
| PM4H workshop series | Workshop | EXTERNAL | The venue where this work actually lands |

## Cluster G. Privacy, anonymisation, synthetic data acceptance

Relevant because any product built on clinical data is judged here first.
The ICLR and AISTATS side of this cluster is not yet populated. The ICML 2026
side is populated and verified: see `ICML2026_CROSSMAP.md`.

| Work | Venue | Status | Note |
|---|---|---|---|
| AIR-Bench 2024: A Safety Benchmark Based on Risk Categories from Regulations and Policies | ICLR 2025 listing claimed | VERIFIED (title) | Consensus 2026-09-12: Yi Zeng et al., arXiv 2024 plus a separate 2025 record consistent with a conference version. 8 government regulations and 16 company policies decomposed into 314 risk categories, 5,694 prompts. Successor: AIR-BENCH Live, Naphade et al. 2026, 335 categories across seven jurisdictions. General AI safety, not biosecurity or health specific. |
| Health data anonymisation guidance for sponsors and CROs | Industry | EXTERNAL | Commercial framing, not a standard |
| EMA Policy 0070, Health Canada PRCI | Regulatory | EXTERNAL | The actual standard a clinical data release is measured against |

## Open observations

1. **Biosecurity is effectively absent** from ICLR and AISTATS as a named topic.
   What exists is generic AI safety and regulation-oriented benchmarking. Treat
   any claim of a biosecurity track at these venues as unverified.
2. **Clinical trial design is methodological, never primary** at these venues.
   Trials appear as a motivating example. The same holds at ICML 2026: a full
   title scan returns zero hits for `clinical trial`, `randomised`, `RCT`,
   `platform trial`, `dose-finding`, `phase II`, `phase III`, `interim`,
   `enrollment`, `vaccine`, `biomarker`, `sample size`.
3. **The machinery exists under other names.** Search `anytime-valid`,
   `experimental design`, `covariate balance`, `adaptive design`,
   `treatment effect`, `policy learning` instead of `clinical trial`.
