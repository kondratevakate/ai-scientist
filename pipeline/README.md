# The pipeline

Five phases. Each one has a single output. A study has not left a phase until that
output exists as a file someone else could read.

Input to the pipeline: a problem and the current context.
Output: a measurable, reproducible result, or a closure record saying why there is none.

Both endings are valid. A pipeline whose only exit is a paper misdescribes how research
works, and hides exactly the part this project studies.

| Phase | Covers | Output |
|---|---|---|
| **Map** | field map, white spots, idea, novelty check | a question worth asking |
| **Freeze** | hypothesis, protocol, ethics, data access | a protocol that cannot be edited afterwards |
| **Do** | data, systematic review, experiments, reproduction | numbers with provenance |
| **Land** | text, submission, reviewer response, DOI, talks | a citable object |
| **Close** | negative result, errata, replication by others | a closure record |

## Map

Input: a problem, and whatever is already known locally.
Output: a question stated so that a reader can say whether it has been answered.

Done when the novelty check is written down, with sources, and says what is already
taken. A question that fails the novelty check does not proceed; it goes to `Close`
with gate `novelty`.

## Freeze

Output: a protocol file whose numbers are not edited after the run. Changes after the
run go into a deviations section with a reason, never into the original statement.

This phase also holds the gates that can stop a study before any compute is spent:
ethics approval and consent, data use agreements, and whether the data can be obtained
at all. A study that fails the data gate goes to `Close` with gate `data`.

The protocol is frozen before the first number is computed. The git commit is the
provenance; the freeze is worthless if it is not committed before the run.

## Do

Output: numbers that someone else can recompute, each traceable to a source file with a
recorded hash.

Data obey the shared contract: canonical paths from the registry, `data_path()` instead
of hardcoded roots, a SHA-256 manifest per acquisition, and a registry entry recording
license and access separately from local content. See `../obligations/` for why access
and license are recorded apart.

## Land

Output: something with a stable identifier that a stranger can cite. A preprint, a
paper, a published logbook, a web artifact with a DOI.

A result that exists only in a local folder has not landed.

## Close

Output: a closure record in `closures.md`.

Every study ends here eventually, including the ones that landed. For a study that
stopped early, the record is the only trace that the work happened at all, which is
why it lives in this repository and not in the folder that went quiet.

## Instruments

Instruments are not phases. They are called from several phases, sometimes many times
in one study. Numbering them would make the number lie about when they run.

| Instrument | Called from |
|---|---|
| bibliography verification | Do (screening), Land (writing) |
| blind coding with adjudication | Do, and Map when screening a field |
| data contract: registry, manifest, lock | Freeze (access), Do (acquisition) |
| logbook judge | Do (reproduction), Close (verdict on own work) |
| writing pass | Land |
| novelty check | Map, and again before Freeze |

## Obligations

Obligations are not actions. They are properties that must hold at every phase
boundary, and they are checked on the way out of each phase, not at the end.

* License, recorded separately for code, data and third party material included here.
* Ethics, consent and data protection.
* Authorship and contribution.
* Funding acknowledgement.
* A persistent identifier for anything that left the machine.
