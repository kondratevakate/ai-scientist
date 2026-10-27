# Fact-check: clinical-trial AI, synthetic data, digital twins, regulators

Checked 2026-09-12 against primary sources where possible. Seed material was a
set of LLM-generated research summaries on ML for trials, synthetic cohorts,
digital twins, PROCOVA, and FDA and EMA positions.

Verdicts: `CORRECT`, `CORRECT WITH CAVEAT`, `OVERSTATED`, `WRONG`, `NOT FOUND`.

---

## 1. Regulatory claims

| Claim in the summaries | Verdict | What the source actually says | Source |
|---|---|---|---|
| EMA qualified PROCOVA in 2022 for primary analysis of Phase 2 and 3 RCTs with continuous outcomes | CORRECT | Adopted by CHMP 15 September 2022, published 20 September 2022. Scope: controlled randomised trials, continuous outcomes. | EMA qualification opinion PDF, EMADOC-1700519818-907465 |
| "This is EMA's first qualification opinion on an AI methodology, true for PROCOVA" | **WRONG** | EMA called **AIM-NASH** (20 March 2025) its first qualification opinion on a methodology based on AI. The PROCOVA opinion is keyworded as statistical methodology. | EMA press release on AIM-NASH, 20 March 2025 |
| PROCOVA treatment effect is unbiased even if the digital twin is biased | CORRECT WITH CAVEAT | EMA: type I error control, unbiased estimation and CI coverage "are not dependent on the choice or performance of the prognostic model", but the estimates are **asymptotically** unbiased "with sufficiently large sample sizes". | EMA opinion, section 1 and Q&A |
| PROCOVA can reduce trial sample size | OVERSTATED | EMA: variance reduction "may in principle be taken into account to reduce sample size, if" uncertainty in the assumptions is handled and the trial stays large enough for its other purposes. Conditional, not a licence. | EMA opinion, section 1 |
| Scope limitation not mentioned in the summaries | **MISSING, material** | Binary, count, and **time-to-event** outcomes are explicitly outside the qualified scope; the applicant lists them as future work. Oncology OS and PFS endpoints are therefore not covered. | EMA opinion, applicant sections |
| "FDA конкурирует с EMA" on PROCOVA | **WRONG (mistranslation)** | CDER wrote "We **concur** with EMA that PROCOVA is a special case of ANCOVA", i.e. agrees. It "does not appear to deviate from our guidance". Future requests go product- or trial-specific to review divisions. | FDA letter quoted verbatim by Unlearn |
| FDA declined ISTAND review because PROCOVA is already covered by guidance | CORRECT | The letter of intent was not accepted into ISTAND because PROCOVA is covered by "Adjusting for Covariates in Randomized Clinical Trials for Drugs and Biological Products". | Same |
| FDA and EMA published joint Guiding Principles of Good AI Practice in Drug Development, January 2026 | CORRECT | Released 16 January 2026, 10 high-level principles, not formal guidance. | EMA and FDA documents, law-firm summaries |
| "FDA does not publish an official 7-step checklist", followed by a 7-item list | **WRONG** | The January 2025 FDA draft guidance defines an official 7-step credibility framework: (1) question of interest, (2) context of use, (3) model risk = influence × decision consequence, (4) credibility plan, (5) execute, (6) document results and deviations, (7) determine adequacy for the context of use. The list in the summary was invented. | Federal Register 2025-01-07; FDA draft guidance |
| Scope limitation not mentioned in the summaries | **MISSING, material** | The FDA draft guidance does **not** cover drug discovery, or AI for operational efficiencies that do not affect patient safety, drug quality, or study reliability. | Same |
| FDA draft guidance "Digital Twins in Clinical Development" | **NOT FOUND** | No FDA guidance with this title surfaced. Real adjacent documents: draft "Considerations for the Design and Conduct of Externally Controlled Trials" (February 2023); the January 2025 AI draft guidance; device-side AI guidance. | Search across FDA and trade press |
| Sanofi eliminated Phase 2 cohorts by replacing them with virtual patients | OVERSTATED | Sanofi's own magazine: QSP-based virtual asthma patients were used to pick doses, letting a programme go from a Phase 1b proof-of-mechanism study to Phase 2b **without a 2a dose-finding cohort**. That is dose selection, not a replaced control arm, and it is a company claim, not a regulatory document. | Sanofi magazine, "Digital Twinning" |

## 2. Evidence claims about digital twins and PROCOVA

| Claim | Verdict | Detail | Source |
|---|---|---|---|
| AWARE (tilavonemab Phase 2): correlation 0.30 to 0.39, residual variance down 9 to 15%, control arm down 17 to 26% | CORRECT WITH CAVEAT | Numbers match. They are **retrospective projections** ("could reduce ... in future AD trials"), not a trial that actually enrolled fewer patients. The summary labelled them "фактические результаты". NCT02880956, 453 patients, 96 weeks. | Wang et al., Alzheimer's & Dementia 2024; TRCI 2025 |
| Training data "29 AD trials plus ADNI", model "CRBM" | NOT VERIFIED | Not confirmed in the sources reviewed. | — |

## 3. Synthetic data claims

| Claim | Verdict | Detail | Source |
|---|---|---|---|
| JMIR SPD study: CART best vs RF, BN, CTGAN by MST, HRD, KM | CORRECT | Akiya et al., JMIR Medical Informatics 2023. MST within the real 95% CI in 88.8 to 98.0% of runs for PFS, 60.8 to 96.1% for OS; HRD concentrated near 0.9. | Consensus |
| BMJ Open: synthetic trial data reproduce conclusions, HR CIs "strongly overlap" | OVERSTATED | Azizi et al. 2021. One secondary analysis of a stage III colon cancer trial, control arm only (n = 1543). HR CI overlap **61% for OS**, 86% for DFS. Direction replicated; 61% is not strong overlap. | Consensus |
| JMIR 2026 colorectal: synthetic pretraining, domain adaptation improves AUPRC in 8 of 12, best Δ ≈ +0.15 | CORRECT WITH CAVEAT | 8 of 12 improved, **only 4 significant**; best Δ +0.1474. Several domain-adaptation settings were significantly **worse** (for example LightGBM with RUS, Δ −0.041, p < .001). The outcome is **binary 7-year overall survival** with XGBoost and LightGBM on 12 shared variables, not a censoring-aware survival model. | JMIR 2026, doi 10.2196/86087, PMC13340573 |
| SurvDiff and conditional generators are "the first generative models built specifically for survival" | **WRONG** | SurvivalGAN (Norcliffe et al., **AISTATS 2023**, PMLR v206) predates them, with three survival-specific failure modes and metrics. | DBLP, PMLR |
| "Nature Cancer 2026" review on synthetic data | **WRONG (journal)** | The review is Eckardt et al., **Nature Reviews Cancer** 2026. Content matches the summary. | Consensus, nature.com |
| npj Digital Medicine 2026 CCAIM roadmap on causal inference and digital twins | CORRECT WITH CAVEAT | Published 23 June 2026, van der Schaar Lab with pharma R&D leaders. CCAIM is funded by GSK, Boehringer Ingelheim, AstraZeneca, **Sanofi**, and QuantumBlack. Relevant when weighing the Sanofi narrative. | nature.com, vanderschaar-lab.com |
| MRCT Center 2026 resource "Deploying Digital Twins and Synthetic Data in Evidence Generation" | CORRECT | Third webinar in the series, recording dated 26 March 2026. | mrctcenter.org |
| PharmaSUG 2026 "Virtual Data, Real Standards" | NOT FOUND | Not located in PharmaSUG 2026 listings searched. | — |

## 4. Benchmarks, foundation models, RL

| Claim | Verdict | Detail | Source |
|---|---|---|---|
| PyTrial: 34 algorithms, 6 tasks, 23 datasets | CORRECT | — | Consensus |
| PyTrial is the de facto SOTA and shows Phase I to III outcome-prediction gains | **WRONG (attribution)** | The phase-level PR-AUC lifts (21.5%, 8.9%, 5.5%) belong to **SPOT**, a separate method (ACM BCB 2023). PyTrial is a benchmark library and a withdrawn ICLR 2024 submission; "SOTA" is a category error. | Consensus |
| EHRSHOT: 6,739 patients, 41.6M events, 15 tasks; CLMBR-T-base 141M parameters on 2.57M patients | CORRECT | Also 921,499 encounters. | NeurIPS 2023 Datasets and Benchmarks paper |
| CLMBR-T is "fully open" and strong SOTA | OVERSTATED | Weights and data are released under a research data use agreement via Stanford AIMI, not openly. Hegselmann et al. (npj Digital Medicine 2026) show general LLM embeddings perform on par with CLMBR-T-Base on the same 15 tasks. | Consensus |
| RL deprescribing RCT NCT06660979 shows RL already shaping clinical decisions | OVERSTATED | REINFORCE-EHR exists: cluster RCT, 70 primary care providers, 1,249 enrolled, Brigham and Women's with Atrius Health, completed 27 March 2026. **No results posted.** The RL personalises EHR nudges to clinicians; it does not choose treatments. | ClinicalTrials.gov |
| 72% of top-50 pharma use AI in clinical development | NOT VERIFIED | No primary source found. | — |

---

## 5. Consequences for a CRO RL or digital-twin product

1. **The regulator-accepted meaning of "digital twin" is narrow.** In PROCOVA it
   is a prognostic score used as one covariate in ANCOVA inside a real RCT. It
   never replaces randomised controls.
2. **Survival endpoints are outside the only qualified method.** PROCOVA covers
   continuous outcomes. Oncology OS and PFS, the core of CRO survival work,
   need a separate qualification or a trial-specific case.
3. **Operational AI may fall outside the FDA AI guidance entirely.** Site
   selection or recruitment optimisation that does not affect safety, quality,
   or study reliability is out of scope. That lowers the regulatory burden but
   also means such a tool earns no regulatory credit.
4. **Claims of synthetic-data utility need the negative results too.** The 2026
   colorectal study is honest about significant degradations; a product pitch
   quoting only "+0.15" repeats the summary's selective reading.
5. **Validate framings against company and funder interests.** Sanofi's dose
   selection story is self-reported; the CCAIM roadmap is co-funded by Sanofi.

## Sources

- EMA, Qualification opinion for PROCOVA (PDF): https://www.ema.europa.eu/en/documents/regulatory-procedural-guideline/qualification-opinion-prognostic-covariate-adjustment-procovatm_en.pdf
- EMA AIM-NASH first AI qualification (coverage): https://www.walderwyss.com/en/news/2025-03-20_ema-qualification-of-first-artificial-intelligence-tool-to-diagnose-inflammatory-liver-disease-in-biopsy-samples
- FDA comments on PROCOVA, quoted verbatim: https://www.unlearn.ai/blog/us-fda-comments-on-unlearns-procova-methodology
- FDA AI draft guidance, Federal Register: https://www.federalregister.gov/documents/2025/01/07/2024-31542/considerations-for-the-use-of-artificial-intelligence-to-support-regulatory-decision-making-for-drug
- EMA and FDA guiding principles (PDF): https://www.ema.europa.eu/en/documents/other/guiding-principles-good-ai-practice-drug-development_en.pdf
- Sanofi, Digital Twinning: https://www.sanofi.com/en/magazine/our-science/digital-twinning-clinical-trials-ai
- Wang et al., AWARE digital twin analysis: https://pmc.ncbi.nlm.nih.gov/articles/PMC11712969/
- JMIR 2026 colorectal synthetic data: https://pmc.ncbi.nlm.nih.gov/articles/PMC13340573/
- SurvivalGAN, AISTATS 2023: https://proceedings.mlr.press/v206/norcliffe23a/norcliffe23a.pdf
- Eckardt et al., Nature Reviews Cancer 2026: https://www.nature.com/articles/s41568-026-00912-4
- Causal inference and digital twins roadmap, npj Digital Medicine 2026: https://www.nature.com/articles/s41746-026-02871-4
- MRCT Center resource: https://mrctcenter.org/resource/deploying-digital-twins-and-synthetic-data-in-evidence-generation/
- EHRSHOT paper: https://proceedings.neurips.cc/paper_files/paper/2023/file/d42db1f74df54cb992b3956eb7f15a6f-Paper-Datasets_and_Benchmarks.pdf
- REINFORCE-EHR trial record: https://clinicaltrials.gov/study/NCT06660979
