---
title: "Handoff: AI Scientist / university infrastructure talk (deck planning)"
created: 2026-10-25
status: Phase 1 (outline) in progress; no slides built, no Phase 2 source pass yet
---

# Handoff: deck on AI scientists, scientific error, hidden science, and who pays

Workflow: `slide-deck-collab` skill (Phase 1 outline → Phase 2 source pass → Phase 3 per-slide
text → layout → render → Phase 4 Read/Anchor/Skip). Slide text in **English**; Kate converses in
Russian. Kate said "for now we only build the plan" — do not render slides until the outline is
approved.

## Framing decisions made by Kate (in order)

1. Topic: autoresearch / AI scientist, problems of scientific error, hidden science, informational
   complexity.
2. Must include the "open analogues vs Owkin K Pro" block (Biomni, ToolUniverse, BioMedArena,
   Murmurent; Claude Code + bio-research plugin vs K Pro Free).
3. Wants Nebius as a partner: open models paid per token, centralised open data so faculties can
   cross-pollinate. Own sensitive data on own servers; open data on Nebius.
4. **Main reframe: solve the universities' problem** — how they pay for agents now, who computes on
   Cerebras, is fast inference needed, what own/lab servers cost.
5. **"Hidden science" = what happens before the paper**: pilot experiments to choose research, who
   holds data, how trends decide who wins grants. Also: who generates the most data, how to check
   data is good, what translational research in medicine is.
6. What research a university wants to fund: breakthrough idea vs famous PI vs industry partner vs
   spinout probability.
7. **Latest emphasis:** show what people write in AI-scientist papers, what those papers cost, and
   the effect of AI scientists — more papers, and more papers about this.
8. Anecdote (Kate's colleagues): labs pay **$20/month per student for Claude** from lab funds
   (matches Claude Pro list price; Claude Code limits on Pro NOT yet checked).
9. Colleagues' paper (STEMBench, `_LAMBDA__AI4Science_paper (2).pdf`, in Kate's Downloads/Telegram
   Desktop) — Kate wants to move into this research direction.

## Current outline (draft, not yet approved)

**Open**
1. Title: *Who pays for the AI scientist?* / *Generation is cheap, verification is not*
2. Agents ≠ chat: seat subscription vs agent tokens (10^6 tokens/episode in STEMBench); anecdote
   "$20 per student from lab funds"

**I. The paper flood** (Kate's latest emphasis)
3. Stat hero: 2.0 → 18.9 → 34.4 AI-scientist papers per 10k papers (2024/2025/2026, own data);
   also same-venue view NeurIPS 2024→2025→2026 = 2 → 16 → 23
4. What they write about: categories (2026: research_step 32, benchmark 28, ai_scientist 11,
   reproduction 2)
5. Cost per paper: Sakana v1 < $15; Kosmos ~$200/run (company); STEMBench $6.69 vs $0.18/run
6. More papers, weaker signal: Kusumegi et al. Science 2025; Liang et al. 2024
7. Peer review under load: Agents4Science 2025; ICLR 2026 LLM policy
8. Bridge: if a paper costs $15, verification is the bottleneck

**II. Scientific error**
9. Divider
10. Stat hero: 75.6% of 6,627 ICML-2026 challenge papers not fully reproduced; 42.4% toy-contaminated
    (judge GLM-5.2 — caveat; source `synthesis/result-D-reproducibility-features.md`)
11. Failure modes: no public artifacts, scale mismatch, toy/proxy substitution
12. Hidden Pitfalls (arXiv 2509.08713), SoundnessBench (arXiv 2605.30329) — still tentative
13. Anecdote: CAffNet 4-arm (compaction made it worse; "toy" in all 18 v1 logbooks)
14. Method-as-lesson: keyword screen precision 0.47 vs two blind coders κ 0.87

**III. Before the paper ("hidden science")**
15. Divider
16. File drawer (Franco 2014)
17. Matthew effect (Bol 2018); novelty penalty (Wang 2017; Boudreau 2016 pending content check)
18. Who funds what: matrix (competitive grants / internal PoC funds / gap & spinout funds) + "no
    outcome data" gap
19. Who holds the data: EMBL-EBI ~123 PB
20. Is this data good: FAIR, Datasheets, STEMBench practices (checksums, withheld splits, anchors)
21. STEMBench: "science has no answer key" (12 tasks, field metric, two anchors; P6 silent failures)
22. Translational spectrum (NCATS 5 stages) — where AI scientists sit today

**IV. Informational complexity** (optional, scope not confirmed)
23. Paper as compression (description length); verification asymmetry
24. STEMBench: reasoning effort helps up to medium; variance is budget truncation

**V. Speed and compute**
25. Speed is a research variable: STEMBench wall-clock caps hit by 44% (MiMo V2.5) / 42% (DeepSeek
    V4 Pro) vs 7% (Gemini 3.7 Flash); extended budget removes the ~0.80 mode on top tagging
26. Who has fast inference in academia: EPCC Edinburgh (Cerebras CS-3), MBZUAI, Jais/Inception on
    Condor Galaxy 1
27. Own servers vs cloud: utilisation decides; hidden staff/facility costs (numbers unverified)
28. Public routes: EuroHPC AI Factories (AI for Science access mode)

**VI. Open stack and proposal**
29. Open analogues: Biomni, ToolUniverse, BioMedArena, Murmurent
30. K Pro Free vs Claude Code + bio-research (two-column)
31. Hybrid architecture: faculty servers (sensitive) / Nebius open-data store / Nebius Token
    Factory (open models per token) / fast inference for agent loops
32. Shared token pool with per-faculty quotas; cross-faculty access to open data
33. Evidence we still need: lab survey (spend, GPU utilisation, pilots, internal funding criteria)
34. Kate's entry: a STEMBench-style medical imaging task (MRI / brain-age, held-out sites, two anchors)

**Close**
35. Design rules for a trustworthy AI scientist
36. CTA (faculties + Nebius partnership; joint benchmark invite)
37. Sources

## Own data used (all in this folder / repo)

- `results/validated_summary.json`, `results/validated.csv`: 111 included of 327 candidates;
  κ 0.87; 26 disagreements adjudicated; keyword-screen precision 0.47 (45/95), recall 45/111.
- Per-year shares computed 2026-10-25 from `validated.csv` + `results/summary.json` paper totals:
  2024 2/9,895; 2025 36/19,044; 2026 73/21,246. **Caveat:** venue mix differs by year (no ICLR/ICML
  2024 in the corpus).
- `../synthesis/result-A..D-*.md`, `../synthesis/review-matrix.md` (rows marked tentative).

## Verified sources (tool-checked 2026-10-25)

Metadata via Crossref / arXiv API / bioRxiv API; content statements checked against abstract or text
unless noted.

| Claim | Source | Check |
|---|---|---|
| Sakana v1 < $15/paper | arXiv 2408.06292 | abstract |
| Sakana v2: 3 workshop submissions, 1 above avg threshold | arXiv 2504.08066 | abstract |
| Kosmos: up to 12 h, ~42k LOC, 1,500 papers/run, 79.4% statements accurate | arXiv 2511.02824 | abstract |
| Kosmos $200/run | edisonscientific.com/articles/announcing-kosmos | company page via search only |
| LLM drafting → +23.7–89.3% papers; complexity–quality reversal | Kusumegi, Yang, Ginsparg, de Vaan, Science 390:1240–1243 (2025), doi:10.1126/science.adw3000; arXiv 2601.13187 | abstract |
| LLM-modified content up to 17.5% CS, 6.3% math/Nature; 950,965 papers | Liang et al., arXiv 2404.01268 | abstract |
| Agents4Science: first conference with AI primary authors/reviewers | arXiv 2511.15534 | abstract; **315 submissions / 48 accepted NOT checked** (full text only) |
| ICLR 2026 desk-reject undisclosed heavy LLM use | blog.iclr.cc 2025/11/19 | via search snippet; Pangram "21% AI reviews" = detector-company estimate |
| File drawer: strong results +40 pp published, +60 pp written up (221 TESS studies) | Franco, Malhotra, Simonovits, Science 345:1502–1505 (2014), doi:10.1126/science.1255484 | metadata; numbers from abstract via search |
| Matthew effect in NWO funding | Bol, de Vaan, van de Rijt, PNAS 115:4887–4890 (2018), doi:10.1073/pnas.1719557115 | metadata; content via PMC/press |
| Novelty penalty in bibliometrics | Wang, Veugelers, Stephan, Research Policy 46:1416–1436 (2017), doi:10.1016/j.respol.2017.06.006 | metadata + abstract text |
| Novelty discount in grant scoring | Boudreau, Guinan, Lakhani, Riedl, Management Science 62:2765–2783 (2016), doi:10.1287/mnsc.2015.2285 | **metadata only; content from secondary quote — read abstract before use** |
| FAIR principles | Wilkinson et al., Sci Data 3:160018 (2016), doi:10.1038/sdata.2016.18 | metadata + summary |
| Datasheets for datasets | Gebru et al., CACM 64:86–92 (2021), doi:10.1145/3458723 | **metadata only** |
| NCATS spectrum: basic → preclinical → clinical → clinical implementation → public health | ncats.nih.gov/about/about-translational-science/spectrum | page fetched |
| EMBL-EBI: >16 PB deposited in 2024, ~123 PB cumulative, ENA+EGA >90% | NAR 54(D1):D10 (2026), academic.oup.com/nar/article/54/D1/D10/8322703 | via search summary; open the paper before use |
| Murmurent: open-source agentic environment for collaborative biomedical labs; Western University; posted 2026-09-29; preprint, CC BY | bioRxiv 10.64898/2026.09.24.753565 | bioRxiv API; **"runs on Claude Code" NOT in abstract** |
| Jais 13B trained on Condor Galaxy 1 (G42 + Cerebras), Inception + MBZUAI + Cerebras | arXiv 2308.16149 (exists); MBZUAI/G42 press | press releases |
| EPCC Edinburgh Cerebras CS-3 cluster | cerebras.ai press release; DCD | press |
| MBZUAI listed as Cerebras customer/collaborator | Cerebras S-1, April 2026 (sec.gov) | via search summary |
| UC Davis ChatGPT Edu $144/yr (was $240), faculty/staff | iet.ucdavis.edu technews | via search summary |
| EDUCAUSE: 94% used AI for work, 54% aware of policies | educause.edu 2026 report | secondary write-up |
| Nebius Token Factory: open models, dedicated endpoints with regional placement, post-training | nebius.com/services/token-factory | page fetched; **no per-token prices or retention policy on that page** |
| STEMBench numbers (8/12 expert anchor reached; $6.69 vs $0.18; wall-clock 44%/42%/7%; top-tagging extended budget [0.937, 0.946]) | colleagues' PDF, pp. 1–9 | read directly |

## Not verified / do not put on slides yet

- Biomni "150 tools, 59 databases"; Biomni ↔ TCGA/GTEx connection; ToolUniverse and BioMedArena
  descriptions (from Kate's pasted text).
- Cerebras per-token prices (third-party trackers only; BenchLM says only 2 pay-per-token models as
  of 2026-10-20); Cerebras faculty RFP may be closed (~585 days old).
- GPU TCO numbers (A800 ~$0.79/GPU-h vs cloud $2.82–5.64, arXiv 2503.11246; Spheron 8×H100
  $2.07/GPU-h at 24/7) — search snippets only, read the papers first.
- NIH FY25 success rate ~17%, early-career 18.5% (Science/STAT news; check NIH data).
- Nebius pricing, data retention, DPA, research-grant terms for universities.
- Claude Pro / Claude Code usage limits for the $20 anecdote.
- No study found linking university internal-fund selection criteria to spinout/licensing outcomes;
  no survey found on university spend on API tokens/agents; no systematic data on pilot experiments
  before topic choice. → motivates the lab survey.

## Cautions

- STEMBench is under double-blind review at ICLR 2027: agree with the authors before showing it with
  the lab name. Draft bug to tell them: p. 7, sentence "Second, three domains demonstrate" is cut off.
- Real health data (MRI, Burdenko GBM, CGM, fundus) must not leave faculty servers; Nebius only for
  open data, and only under a DPA.
- Kate's global rule: never state paper content from memory; any citation change → `bib-verify`
  skill.

## Open questions for Kate

1. Audience, event, length (decides whether all blocks stay).
2. Is the "informational complexity" block kept? Which theory: Kolmogorov / description length,
   computational complexity (verification vs generation), or Shannon?
3. Any draft .pptx or images to absorb (Phase 2 visual pass)? Default palette navy/cream/terracotta.
4. Where are the "13 K Pro queries" (for the optional demo slide)?
5. Make the lab survey the centrepiece? (asked, not answered)
6. Code the 111 papers for: reports cost, human evaluation, wet-lab validation? (asked, not answered)
7. "How much papers cost" — AI run cost only, or also human cost (time, APCs)?

## Next actions

1. Get outline sign-off (questions above).
2. Phase 2 source pass: close every "not verified" row; collect URLs per slide.
3. Optional own analysis: code 111 validated papers (cost / human eval / validation reported).
4. Then Phase 3, slide by slide, text first.
