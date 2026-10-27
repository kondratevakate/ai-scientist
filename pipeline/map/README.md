# ICLR / AISTATS literature map

Working catalogue of ICLR and AISTATS papers relevant to health AI, clinical
trials, survival and hazard methods, conformal prediction, process mining, and
the privacy questions that come with selling clinical ML products.

Built to be extended: new topics and context get appended to
`ICLR_AISTATS_MAP.md` under the matching cluster, using the same columns.

## Files

| File | Contents |
|---|---|
| `ICLR_AISTATS_MAP.md` | The catalogue. One row per paper, grouped by cluster. |
| `ICML2026_CROSSMAP.md` | ICML 2026 anchors verified locally, mapped to the same clusters and to already-reproduced work. |
| `VERIFICATION_QUEUE.md` | Every claim that still needs checking, plus confirmed conflicts. |
| `REGULATORY_AND_2026_FACTCHECK.md` | Claim-by-claim check of PROCOVA, FDA and EMA AI positions, digital twins, synthetic cohorts, and 2026 industry claims, with consequences for a CRO RL product. |

## Status legend

Every row carries a status. Nothing enters this map as fact without a source.

| Status | Meaning |
|---|---|
| `VERIFIED` | Title, venue, and year confirmed against a source named in the row. |
| `UNVERIFIED` | Taken from a secondary summary. Topic is plausible; venue, year, and ID are not confirmed. |
| `CONFLICT` | Two different papers were given the same identifier, or the identifier contradicts the venue. Resolve before use. |
| `EXTERNAL` | Real but not ICLR or AISTATS. Kept for context, never cited as a conference paper. |

## Why the status column exists

The source summaries that seeded this map contain at least two hard identifier
collisions (see `VERIFICATION_QUEUE.md`). A collision means the identifiers were
generated rather than looked up. Topics in such summaries are usually real;
identifiers, venues, and years are not. None of it is safe in a pitch deck, a
grant application, or a related-work section until checked.

## Verification protocol

OpenReview blocks programmatic access from this environment: both
`api.openreview.net` and `api2.openreview.net` return HTTP 403 with
`ChallengeRequiredError`, and the challenge is not to be bypassed. So verify
through one of these instead:

1. **Manual OpenReview**: open `https://openreview.net/forum?id=<ID>` in a normal
   browser. Record the exact title, the venue string, and the decision.
2. **Semantic Scholar Graph API**: `https://api.semanticscholar.org/graph/v1/paper/search`
   with `fields=title,year,venue,externalIds`. Open, no key needed, but rate
   limited to roughly one request per second without an API key.
3. **DBLP**: `https://dblp.org/search/publ/api?q=<title>&format=json`. Open, fast,
   authoritative for venue and year, weak for workshop papers and submissions.
4. **arXiv**: confirms existence and date, never confirms the venue.

Record which source was used in the `Evidence` column. A row without evidence
stays `UNVERIFIED` no matter how plausible it looks.

## Conventions

- One paper per row. If the same work exists as a submission and as a camera-ready,
  keep one row and note both in `Evidence`.
- `Cluster` is the thematic group, not the venue track.
- `Link to own work` names the local folder or paper ID this connects to, so the
  map stays usable for planning and not only for reading.
- Withdrawn and rejected submissions are kept, marked as such. They are often the
  most useful prior art, and they are also the least safe to cite.
