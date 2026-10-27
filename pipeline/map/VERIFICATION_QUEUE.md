# Verification queue

Work top to bottom. Move a row to `ICLR_AISTATS_MAP.md` as `VERIFIED` only after
filling venue, year, and the source used. Protocol: see `README.md`.

## 1. Confirmed conflicts (resolve first)

Both collisions are visible in the source summaries themselves, without any
lookup. Each proves that at least one attribution in the pair is generated.

| Identifier | Claimed for paper 1 | Claimed for paper 2 | Action |
|---|---|---|---|
| `8hkf29PXCn` | Simpler Calibration for Survival Analysis, ICLR 2022 submission | Training LLMs for EHR-Based Reasoning via RL (EHRMIND) | **Partly resolved by title evidence:** EHRMIND exists (Lin et al., arXiv 2025); "Simpler Calibration for Survival Analysis" is not found anywhere. The ID most plausibly belongs to EHRMIND. Confirm on the forum page before citing either. |
| iclr.cc virtual `10006913` | LongSurv: Bridging Short-Term Data and Causal Long-Term Survival | COMPASS: Robust Feature Conformal Prediction for Medical Segmentation Metrics | Open `https://iclr.cc/virtual/2026/poster/10006913`, record the real title, then search the other by title |
| arXiv `2411.02114` | Conformalized Survival Counterfactuals Prediction (cited as its arXiv link in the first summary) | Semiparametric Conformal Prediction, AISTATS 2025 | **Resolved for paper 2**: Semantic Scholar confirms 2411.02114 is Semiparametric CP. The counterfactuals paper still has no confirmed arXiv ID. |

### Semantic Scholar pass, 2026-09-12

Title search on 16 titles. Three firm results:

- Semiparametric Conformal Prediction: AISTATS 2025, arXiv 2411.02114. Verified.
- Conformal Structured Prediction: ICLR, arXiv 2410.06296. Verified.
- Proper Scoring Rules for Survival Analysis: indexed as **ICML 2023**, arXiv 2305.00621, not as an ICLR 2023 submission. The ICLR claim may reflect an earlier submission, but it is not confirmed.

Thirteen titles returned no match. This is **not** evidence of absence: the
run hit the unauthenticated rate limit, so an empty result may be a throttled
request. The same title search for "Conformalized Survival Counterfactuals"
returned only the unrelated JRSSB 2021 paper "Conformalized Survival Analysis"
(arXiv 2103.09763).

### DBLP pass, 2026-09-12

Failed for all 19 titles, no results recorded. The first three requests returned
a non-JSON body, the fourth HTTP 429, and every later request was dropped with
the connection closed. Nothing about these titles was learned from DBLP. Retry
later at a slower rate, or verify manually in a browser.

### Consensus pass, 2026-09-12

| Claimed paper | Outcome |
|---|---|
| COMPASS | **Exists.** Cheung et al. 2025, arXiv. ICLR 2026 not confirmed. |
| PyTrial | **Exists.** Wang et al. 2023, plus companion arXiv paper and public code. ICLR 2024 withdrawal not confirmed. |
| ICALD | Exact paper not found; predecessor Sheng et al. 2025 (PMLR) exists. |
| Conformalized Survival Analysis for General Right-Censored Data | Not found under this title. Real neighbours: Candès 2021, Sesia 2024, Qin 2024. |
| Conformalized Survival Counterfactuals | Not found. Real neighbours: Sesia 2024, Yi 2025, Shin 2025. |
| Privacy-Protected Causal Survival Analysis | Not found. Real neighbours: FedPseudo (KDD 2023), Han 2023, Guo 2024. |
| Context Clues | **Exists.** Wornow et al., arXiv 2024 plus 2025 record, public code. |
| Dynamic Survival Analysis for Early Event Prediction | **Exists.** Yèche et al. 2024, arXiv. Venue unconfirmed. |
| LongSurv | Not found. Real anchors for the problem: Jackson 2016 review, survextrap 2023, Timmins 2026. |
| DySurv | **Exists.** Mesinovic et al., arXiv 2023; published in **JAMIA 2024**, not ICLR. |
| Deep Extended Hazard Models | **Exists.** Zhong et al. 2021. Venue not given. |
| Conformal Prediction Masks | **Exists.** Kutiel et al. 2023. Evaluated on generic image restoration, not on medical datasets. |
| Fair Conformal Predictors | **Exists.** Lu et al. 2021 record. AAAI 2022 unconfirmed. |
| CP for segmentation, morphological | **Exists, title was wrong.** Real title uses "Morphological Prediction Sets". Mossina et al. 2025. |
| Simpler Calibration for Survival Analysis | Not found. Real anchors: X-CAL (NeurIPS 2020), Austin 2020 ICI. |
| EHRMIND | **Exists.** Lin et al., arXiv 2025. Sibling EAG-RL (Fang et al. 2025) also exists. |
| Hierarchical Attention Transformer, trial outcome | **Exists, title was wrong.** Real paper is TrialDura, predicting trial **duration**, ACM BCB 2024, public code. |
| Retrieval-Reasoning Synthetic Clinical Trial Generation | **Exists.** Xu et al., published at ACM BCB, public code. |
| SlotSPE | **Exists.** Zhang et al., arXiv 2025. |
| Bayesian Networks for Individual Survival | Not found. Neighbour: Sheidaei 2022. Side find: SurvivalPFN (Qi et al. 2026) exists. |
| HeLoM | Not found. Neighbours: CPLLM, EHR-KnowGen; context review Wornow 2023. |
| Temporal Visiting-Monitoring | **Exists.** Li et al., published in Knowledge-Based Systems 2025, not ICLR. |
| AIR-Bench 2024 | **Exists.** Zeng et al., arXiv 2024 plus 2025 record. |

Reading, after all 26 titles:

- 18 papers exist; 8 were not found under the claimed title.
- Only **2** have a confirmed ICLR or AISTATS venue.
- **5** exist but are published elsewhere (ICML, JAMIA, ACM BCB twice, Knowledge-Based Systems). The source summaries relabelled them as ICLR.
- 2 titles were materially wrong, changing what the paper does (outcome vs duration prediction).
- Named tools and benchmarks with public code check out reliably. The failures concentrate in conformal and causal survival titles attributed to ICLR 2025 and 2026, exactly the cluster most relevant to current work.

Remaining work is manual only: open the OpenReview forum pages for the 8
not-found rows and the 11 venue-unconfirmed rows.

## 2. Programmatic access status

| Source | Status on 2026-09-12 | Note |
|---|---|---|
| `api2.openreview.net` | Blocked, HTTP 403 `ChallengeRequiredError` | Do not bypass. Verify manually in a browser. |
| `api.openreview.net` | Blocked, HTTP 403 `ChallengeRequiredError` | Same |
| `openreview.net/forum` | HTTP 307, client-rendered page | Needs a real browser |
| In-app browser on `openreview.net/forum` | Stops at "Verifying your browser, complete the check below" | Interactive bot check. Not completed by design. Manual human visit only. |
| Consensus MCP search | Works, 3 results per query on the free tier | Best available route. Confirms existence and authors, often not the conference. |
| Semantic Scholar Graph API | Reachable, heavily rate limited without a key | 16 titles searched: 3 firm results, 13 empty and possibly throttled |
| DBLP | Rate limited, then connections dropped | 19 titles attempted, 0 results. Retry slower or later. |

## 3. Identifier checks, by priority

Priority reflects how directly the paper feeds current work, not its quality.

| Priority | Identifier | Claimed title | Claimed venue |
|---|---|---|---|
| P0 | `JQtuCumAFD` | Conformalized Survival Analysis for General Right-Censored Data | ICLR 2025 poster |
| P0 | `1j0ormf8uI` | Conformalized Survival Counterfactuals Prediction | ICLR 2026 poster |
| P0 | `aTxnsFFO7t` | Privacy-Protected Causal Survival Analysis Under Distribution Shift | ICLR 2026 poster |
| P0 | `5vY0HNpy9F` | PyTrial | ICLR 2024 withdrawn |
| P0 | — | COMPASS | ICLR 2026 poster, see conflict above |
| P1 | `frv3s3AtUD` | ICALD | ICLR 2026 submission |
| P1 | `Xj9V-stmIcO` | Proper Scoring Rules for Survival Analysis | ICLR 2023 submission |
| P1 | arXiv 2411.02114 | Semiparametric Conformal Prediction | AISTATS 2025 |
| P1 | `2ATD8a8P3C` | Conformal Structured Prediction | ICLR 2025 poster |
| P1 | `zg3ec1TdAP` | Context Clues (EHRSHOT) | ICLR 2025 poster |
| P1 | — | Dynamic Survival Analysis for Early Event Prediction | ICLR 2024 or 2025, year ambiguous |
| P2 | `J4QatK02Qc` | Conformal Prediction Masks | ICLR 2023 TML4H workshop |
| P2 | `kDbD2GkLfy` | DySurv | venue not stated |
| P2 | `GUD7rNkaWKr` | Deep Extended Hazard Models | venue not stated |
| P2 | `5kinne2hCb` | LongSurv | venue not stated, see conflict above |
| P2 | `WqCRSn2WAY` | SlotSPE | venue not stated |
| P2 | `UAM4Kvab4z` | Bayesian Networks for Individual Survival | venue not stated |
| P2 | `2xmqiebwgY` | Hierarchical Attention Transformer for Trial Outcome | venue not stated |
| P2 | `EdAgWYEFc1` | Retrieval-Reasoning Synthetic Clinical Trial Generation | ICLR 2025 withdrawn |
| P2 | `VBMdD2owBe` | HeLoM | ICLR 2026 withdrawn |
| P2 | `HmmN0Mxze7` | Temporal Visiting-Monitoring Feature Interaction | ICLR 2025 submission |

## 4. Coverage gaps to fill with new searches

These clusters are thin because the source summaries were thin, not because
the venues are empty. Search them directly rather than trusting absence.

- AISTATS 2022 to 2026: `survival`, `hazard`, `censor`, `conformal`, `treatment effect`, `clinical`
- ICLR 2022 to 2026 workshops: TML4H, TS4H, and any time-series-for-health workshop
- ICLR and AISTATS on privacy-preserving synthetic tabular data and membership inference
- ICLR and AISTATS on off-policy evaluation and dynamic treatment regimes with clinical data
- ICLR and AISTATS on adaptive experimental design, anytime-valid inference, response-adaptive randomisation
