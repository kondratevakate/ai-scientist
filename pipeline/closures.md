# Closure ledger

Why work stopped, and how far it got before it did.

This ledger is central on purpose. A closure record kept inside the folder that went
quiet is never read again, including by its author, which is how hidden science stays
hidden. The dead project keeps the evidence; this file keeps the reason and a pointer
to it.

## Fields

| Field | Meaning |
|---|---|
| `what` | the claim, hypothesis or target that was being tested |
| `phase` | furthest phase reached: Map, Freeze, Do, Land |
| `gate` | why it stopped, from the fixed vocabulary below |
| `evidence` | where the work and the reasoning live |
| `reopen` | what new fact would make this worth restarting |

## Gate vocabulary

| Gate | Meaning |
|---|---|
| `data` | the data cannot be obtained, or does not contain what the claim needs |
| `compute` | the run does not fit the available hardware |
| `novelty` | already done, or the contribution turns out not to be one |
| `result` | the thing is not what it was thought to be, or the effect is absent |
| `priority` | stopped in favour of something else; the record must name what won |
| `deadline` | the window closed |

`priority` without a named winner is not a reason, it is a shrug. Every `priority`
entry points at another row or another study, which makes this file a graph rather than
a drawer.

## Records

Nine records, each traced to a file in this tree. The bibliographic claims inside the
`novelty` reasons come from the novelty checks cited under `evidence` and have not been
re-verified for this ledger; run bibliography verification over them before any of this
is published.

### C1. Treatment Allocations, counterexample and repair

* `what` the Eq. (18) proof step in `9kWVQtpvJi` is wrong; propose a repair as a paper
* `phase` Map
* `gate` novelty
* `why` the proof step is genuinely wrong, but the prefix rule is Learn-then-Test fixed
  sequence testing, so the method is valid on finite grids and the repair is not new
* `evidence` `icml-repro/iclr_aistats/`, novelty check recorded 2026-09-12
* `reopen` a censored-outcome extension that is shown to differ from the known
  LTT with IPCW survival screening

### C2. PROCOVA for time to event

* `what` extend the regulator-qualified PROCOVA method to time-to-event endpoints
* `phase` Map
* `gate` novelty
* `why` done already, twice, by separate groups
* `evidence` `icml-repro/iclr_aistats/`, novelty check recorded 2026-09-12
* `reopen` nothing obvious; the lane is occupied

### C3. Cox subgroups as a trial-design paper

* `what` frame `3tlaoBZrSg` subgroup discovery as adaptive enrichment for trials
* `phase` Map
* `gate` result
* `why` the method finds regions where a Cox model fits, which is prognostic, and uses
  no treatment variable at all, so it is not enrichment; treatment-subgroup Cox work
  already exists
* `evidence` `icml-repro/iclr_aistats/HANDOFF_2026-09-15_five_ideas.md` section 2;
  proof audit in `icml-repro/cox_subgroup/repro_cox_subgroup/THEOREM_6_1_AUDIT.md`
* `reopen` the real remaining gap is that Theorem 6.1 assumes no censoring; that is a
  theory paper, not a three-week one

### C4. MNAR off-policy evaluation counterexample

* `what` a counterexample to `vpSFJoxyDz`
* `phase` Map
* `gate` result
* `why` the counterexample only hits the main-text statement; the qualified theorem
  already carries the regularity condition that blocks it
* `evidence` `icml-repro/iclr_aistats/`, novelty check recorded 2026-09-12
* `reopen` a counterexample against the qualified statement

### C5. FunCQNet, real-data claim

* `what` reproduce the UNOS and OPTN quantitative results of `wNL0qGb2MN`
* `phase` Do
* `gate` data
* `why` the registry is distributed as access-controlled STAR files under a signed data
  use agreement with an application process and a fee; there is no public version, so no
  third party can confirm the claim from public materials
* `evidence` published logbook page `claim-3-real-data-unos-optn-results-not-reproducible`
  in `icml-repro/reproductions/funcqnet/`
* `reopen` an executed data use agreement; the simulation claims 1 and 2 were reproduced
  and stand independently

### C6. GBSG2 as a benchmark cohort

* `what` use GBSG2 as one of the real survival datasets
* `phase` Do
* `gate` data
* `why` the published trial randomised 473 patients while the distributed file has 686
  rows, so the file is not the trial it is taken to be
* `evidence` recorded in the censoring-yardstick working notes, 2026-09-15
* `reopen` a provenance document reconciling the row count

### C7. CAST via PhysioNet crisdb

* `what` use CAST as an open time-to-event trial
* `phase` Freeze
* `gate` data
* `why` the public release carries RR intervals only, with no per-patient outcomes, so
  the endpoint the design needs is absent
* `evidence` recorded in the censoring-yardstick working notes, 2026-09-12
* `reopen` an outcome-level release

### C8. CCD, "ERT beats CovGap"

* `what` treat the ERT versus CovGap comparison as a contribution of our own
* `phase` Map
* `gate` novelty
* `why` it is the paper's own claim, so restating it is not a result
* `evidence` `icml-repro/iclr_aistats/HANDOFF_2026-09-15_five_ideas.md`, 2026-09-15

### C9. Open questions in healthy brain aging

* `what` a FAIR map and measurement thesis for healthy brain aging
* `phase` Freeze, protocol written and committed
* `gate` priority
* `winner` not recorded; see below
* `why` wind-down handoff committed 2026-07-18, no work since
* `evidence` `studies/brain-aging-open-questions/`, with a component-by-component
  epistemic status in `docs/STATUS-AND-VALIDITY.md` that marks which parts are
  established and which are constructions to be re-derived
* `reopen` the status file names the weak points precisely, which is an unusually good
  restart position; the licence files it says are needed were never added

## Open on this ledger

* C9 has gate `priority` with no winner named, which breaks the rule above. Resolve it
  or change the gate.
* Candidates seen in session notes but not yet traced to a file, so not recorded here:
  ORBIT dropped on in-house hospital data; the PSE9 line removed from
  patient-state-and-decisions on 2026-10-18; the no-go on clinical pilots from the same
  reset. Harvest these from their own repositories before trusting the shape of this
  ledger.
* Nine records give a distribution of three `novelty`, three `data`, two `result`, one
  `priority`. Eight of nine stopped on an external fact rather than a change of mind.
  That is the property that makes this file data and not a diary, and it is worth
  checking again once the count is past fifty.
* Five of nine stopped at Map, which is the cheapest place to stop. Worth watching: if
  that share falls over time, novelty checks are happening too late.
