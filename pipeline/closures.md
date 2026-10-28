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

Eleven records, each traced to a file in this tree. The bibliographic claims inside the
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

### C10. ORBIT, prognostic world model on longitudinal ophthalmic data

* `what` reproduce `2234` ORBIT in the challenge
* `phase` Freeze, stopped at the data gate before any compute
* `gate` data
* `why` the paper's own Data Ethics Statement says ORBIT-LD is "derived from
  retrospective ophthalmic archives at our institution", IRB-approved with a waiver of
  informed consent. It is one hospital's own archive. The paper carries no availability
  statement for the dataset at all: not a release promise, not an on-request clause
* `evidence` the paper itself, `icml-repro/2234_ORBIT_A_Prognostic_World_.pdf`, appendix
  A.1; text extracted from the PDF, not from a summary
* `reopen` an availability statement from the authors; nothing else would change this

### C11. PSE9 as an output of the patient-state project

* `what` write the PSE9 abstract out of `patient-state-and-decisions`
* `phase` Freeze, requirements and deadline pinned, nothing drafted
* `gate` priority
* `winner` the gated execution plan in that project's own README, which replaced the
  document-driven queue on the same day
* `why` `docs/PSE9.md` carries the header "ARCHIVED 2026-10-18: superseded by the gated
  plan in README. Historical evidence only; commands and pending tasks below are not
  authorization to resume." The file's own body still reads "No abstract/manuscript
  drafted or submitted at this stage"
* `evidence` `studies/patient-state-and-decisions/docs/PSE9.md`
* `note` **This is not a closure of PSE9.** Two PSE9 abstracts were submitted on
  2026-10-23, from the verdict-audit work in `studies/icml-repro` instead. What closed is
  this project as the source of that abstract, which is a relocation, not an abandonment.
  Recording it as "PSE9 dropped" would have been wrong

## Open on this ledger

* C9 has gate `priority` with no winner named, which breaks the rule above. Resolve it
  or change the gate. It is the only record still failing its own format.
* The three candidates that were listed here unverified on 2026-10-27 have been checked
  against their own files. Two became records, C10 and C11, and the third did not
  survive: the blanket no-go on clinical pilots was itself superseded by protocol 015 in
  that project's README, so it is not a standing closure. One of three session notes was
  wrong and a second was wrong in its framing, which is the argument for the rule that
  every record names the file it came from.
* Eleven records: four `data`, three `novelty`, two `result`, two `priority`. Nine of
  eleven stopped on an external fact rather than a change of mind. That is the property
  that makes this file data and not a diary, and it is worth checking again once the
  count is past fifty.
* By phase: five stopped at Map, four at Freeze, two at Do, none later. Map is the
  cheapest place to stop and Freeze is the second cheapest, so the shape is currently
  healthy. Worth watching: if records start appearing at Do and Land, the gates upstream
  are not being checked early enough.
