# Competitive & Improvement Analysis — `vital-info-translations`

> Analyst review of PLAN.md v0.2.0 (2026-06-28), grounded with web research. Scope: the
> cross-domain umbrella project that translates vetted, life-critical public-interest information
> (health, safety, and adjacent civic/legal/disaster guidance) into under-served languages with
> qualified human review. HIGH-STAKES: wrong vital info causes harm.

---

## 1. Correctness & completeness review of PLAN.md

The plan is unusually strong for a draft. It correctly identifies **source-license discipline** and
**qualified human review** as the two load-bearing constraints, and operationalizes both as hard
gates rather than aspirations. Findings below are ordered roughly by importance.

**What the plan gets right (verified against external evidence):**

- **License-as-data, source-following output license.** The plan's treatment of WHO content is
  accurate and conservative. WHO has published under **CC BY-NC-SA 3.0 IGO since 12 Nov 2016**, the
  license *does* permit translations, but it imposes (a) **ShareAlike** (the translation must carry
  the same/compatible license — so the plan's "never relicense to CC-BY" rule is correct), and (b) a
  **mandatory translation disclaimer** with near-verbatim wording: *"This translation was not created
  by WHO. WHO is not responsible for the content or accuracy of this translation,"* plus a statement
  that the original English edition is the **binding and authentic** edition. The plan captures all
  three (ShareAlike, disclaimer, binding-original) correctly. (who.int/about/policies/publishing/copyright)
- **Per-source verification, not blanket assumptions.** Correctly flags CDC as *mostly* US public
  domain *but* with embedded third-party material requiring per-page checks, and MoH/MSF as "verify
  individually." This matches reality.
- **High-stakes QA layering.** The escalation is well-designed: agent self-check (with structured
  `UNCERTAIN:` flags that *block* sign-off) → independent qualified reviewer → **mandatory second
  reviewer + back-translation** for dosage/negation content → conflict resolution where the
  conservative reading wins. Back-translation as a *required gate for the highest-risk tier* aligns
  with the **ISPOR linguistic-validation** standard and ISO 17100/18587, which treat back-translation
  + reconciliation as the methodological norm for safety-critical text.
- **Reviewer independence + COI** and the "drafting human may not be sole reviewer" rule are present —
  a frequently-missing control.
- **Honest cold-start.** `verifiedNeed=false` until a partner is secured, with an explicit
  **pause/go/pivot/hold decision point** at end of M1, is intellectually honest and avoids the
  "translate things nobody adopts" failure mode.

**Gaps / corrections (recommended fixes):**

1. **Native-speaker reviewing is implied but under-specified vs. the harm evidence.** The plan
   requires a "qualified language reviewer with health-translation competence" and adds a
   cultural-appropriateness checklist item, but does not *hard-require* a **native/near-native target-
   language reviewer** in the reviewer-qualification criteria text itself (it appears in
   `reviewers-001` AC as "native/near-native"). Make native-speaker-of-target a **non-waivable**
   criterion, and add **cognitive-debriefing / in-target reader comprehension testing** (ISPOR
   recommends 5–8 readers; WHO guidance ~10) as an optional-but-recommended step for the highest-value
   documents. Right now comprehension is only checked by reviewers, not by *actual target readers*.
2. **"Medium risk tier" is correct for *translation of authoritative content*, but the umbrella scope
   creates tier-drift risk.** As soon as siblings pull in **legal-rights / know-your-rights** or
   **clinical dosage tables**, the effective risk rises. Recommend the plan state an explicit
   **risk-tier-by-domain matrix**: health-factsheet-translation = medium; anything with dosages,
   legal advice, or "what to do in an emergency" decision trees = **medium-high → requires the
   second-reviewer + back-translation tier by default**, and credentialed domain (clinical/legal)
   sign-off where the source itself is advice-giving. The plan gestures at this but should make it a
   table, because the umbrella *will* attract higher-stakes siblings.
3. **"Not medical/legal advice" disclaimer is asserted in non-goals but not in the deliverable
   template.** The Definition of Shipped requires attribution + WHO disclaimer, but there is **no
   required "this is a translation of [source]; it is not a substitute for professional advice; the
   original is binding"** reader-facing notice baked into `attribution.txt`/delivery bundle for
   *non-WHO* sources. Add a standard **scope/limits notice** to the delivery template for every
   deliverable, in target language + pivot.
4. **Currency / source-update handling is good but one-directional.** The hash-diff source-change
   watcher detects upstream drift, but there is no defined **SLA for re-review/withdrawal** once drift
   is flagged, and no **"translation staleness" surfacing to the partner/end reader** (e.g., a
   `sourceVersion` + `lastVerified` stamp visible in the delivered artifact). Provenance captures it
   internally; expose it externally.
5. **Umbrella vs. siblings governance is undefined.** PLAN.md never explicitly states how
   `vital-info-translations` (umbrella) relates to **`ewing-info-translations` / oncology-glossary-
   multilingual / emergency-phrasebooks** as *sibling repos*. This is the single biggest structural
   gap: the license allow-list, glossary schema, reviewer roster, `provenance.yaml`/`review.yaml`
   schemas, and the QA pipeline are all **shared infrastructure** that the siblings will duplicate
   unless the umbrella is declared the **canonical home of the shared high-stakes-translation
   pipeline** (see §7). Decide: is this the umbrella program *and* the shared-infra owner, or just one
   content stream?
6. **Attribution edge cases.** ShareAlike chaining isn't addressed: if a translation is itself adapted
   downstream by a partner, the BY-NC-SA obligation propagates. Add a one-line downstream-obligations
   note to the partner handoff.
7. **Low-resource reviewer sourcing is the acknowledged top risk (High/High) but the mitigation is
   thin.** "Partner with a translation NGO" is named but not costed; for genuinely low-resource
   languages, qualified *health*-translation reviewers may not exist at all. The plan should add a
   concrete **fallback ladder** (TWB/CLEAR Global community → diaspora health-worker networks →
   partner-supplied reviewer → *do not ship*) and accept that some target languages will be
   **structurally blocked**, which is fine and honest.
8. **FLORES-200 "low-resource" definition is reasonable** but note FLORES-200 itself is a moving
   target; pin the version. Minor.

Overall: the plan is **correct and conservative** on the two things that matter most (licensing,
high-stakes QA). The principal weaknesses are **(a) the umbrella↔sibling / shared-infra relationship
is unspecified**, and **(b) native-reviewer + reader-comprehension testing + the "not advice" reader
notice + risk-tier-by-domain are slightly under-operationalized given how high the harm ceiling is.**

---

## 2. Competitive landscape

No existing actor occupies the exact niche of **open, license-clean, human-quality-reviewed, version-
provenanced translation of vital information into low-resource languages as a reusable commons.** The
nearest players each cover part of it:

**Translators without Borders / CLEAR Global** — the closest mission match. Runs the **Kató** language
platform and the **Gamayun** language-equality initiative (Microsoft/Cisco-funded), aiming to bring
~20 under-served languages "online" over a decade, including building MT models and multilingual
chatbots for health info.
- *Strengths:* deep humanitarian credibility, real low-resource language data/models, established NGO
  partnerships, professional + community translator pools — the **obvious reviewer/partner** for Hee-Lee Oss.
- *Weaknesses:* organization-centric (their platform, their projects) rather than a public **commons of
  reusable, individually-licensed, provenanced documents**; MT-model emphasis; not a per-document open
  artifact library with attached license/review metadata.
- Sources: https://translatorswithoutborders.org/gamayun/ , https://clearglobal.org/resources/gamayun/

**WHO (and PAHO)** — the **canonical source**, not a competitor. Authoritative content under
CC BY-NC-SA 3.0 IGO with translation permitted under ShareAlike + disclaimer.
- *Strengths:* authority; license explicitly allows translation; binding-original model.
- *Weaknesses:* WHO does not itself produce or vouch for low-resource translations (hence the
  disclaimer); coverage in long-tail languages is sparse. This *is the gap Hee-Lee Oss fills downstream.*
- Source: https://www.who.int/about/policies/publishing/copyright

**Hesperian Health Guides** — *"Where There Is No Doctor,"* described by WHO as possibly the world's
most-used public-health manual; **80–85+ languages**, an explicit **Open Copyright** policy, and a
translation fund seeding local translation/adaptation.
- *Strengths:* the gold standard for **openly-licensed, adaptable, community-health content**; proven
  multi-language reach; permissive reuse.
- *Weaknesses:* book/manual-centric and slow-moving; not a continuously-updated, provenance-stamped,
  per-document pipeline; not focused on the long tail of *brand-new* outbreak/disaster guidance.
- Sources: https://en.wikipedia.org/wiki/Hesperian_Health_Guides , https://hesperian.org/about/

**Tarjimly** — 65,000+ volunteer bilinguals across **200+ languages**, matched in minutes for **live
interpretation** and document help (medical 18% of sessions).
- *Strengths:* massive multilingual volunteer base (a potential reviewer pool), real-time human reach.
- *Weaknesses:* **synchronous, person-to-person interpretation**, not a curated, reviewed, reusable
  *document* commons; quality is session-level, not back-translation-gated artifacts.
- Sources: https://www.tarjimly.org/ , https://solve.mit.edu/solutions/60179

**Google Translate (cautionary baseline, not a competitor — the thing we must beat).** Independent
clinical studies show why raw MT is unsafe for vital info: an ED-discharge study found **~92% accuracy
Spanish / ~81% Chinese, with ~2% (Spanish) and ~8% (Chinese) of translations carrying potential for
clinically significant harm**; a later 26-language study still found a ~5% error rate, **highly
language-dependent and worst for non-European / low-resource languages.**
- Sources: https://pmc.ncbi.nlm.nih.gov/articles/PMC8606479/ ,
  https://pubmed.ncbi.nlm.nih.gov/41129839/

**Refugee Phrasebook** — community-built, **CC0**, 28+ languages of basic medical/legal/everyday
*phrases*.
- *Strengths:* truly open (CC0), collaborative, print-and-go, award-winning reach.
- *Weaknesses:* short phrases, not reviewed factsheets; no provenance/QA gating; not authoritative
  guidance. Complementary to (overlaps) the `emergency-phrasebooks` sibling.
- Source: https://en.wikipedia.org/wiki/Refugee_Phrasebook

**Meedan (Health Desk / Digital Health Lab)** — open-source tooling + a network of public-health
scientists for **health misinformation fact-checking and translation/annotation** across languages.
- *Strengths:* expert network, infodemic/misinformation framing, open tools, multilingual.
- *Weaknesses:* fact-checking/journalism-facing, not a beneficiary-facing translated-document library.
- Source: https://meedan.org/programs/digital-health-lab

**Government / agency multilingual portals (US CDC, ECDC, national MoHs, IFRC/Red Cross).** CDC offers
free, mostly-public-domain translated factsheets/toolkits searchable by language/topic; ECDC and MoHs
publish in some languages; Red Cross movement produces first-aid/disaster guidance.
- *Strengths:* authoritative, often reusable (esp. CDC public domain), professionally produced.
- *Weaknesses:* coverage concentrated in **high-resource languages**; long-tail languages barely
  served; no unified open commons; update cadence and license terms vary by document.
- Source: https://www.cdc.gov/other/other-languages/index.html

**Net:** the field splits into (a) **authoritative sources with thin low-resource coverage** (WHO,
CDC, ECDC, MoH), (b) **open content libraries** (Hesperian, Refugee Phrasebook), (c) **human-network
translation/interpretation services** (TWB/CLEAR Global, Tarjimly), and (d) **fact-checking infra**
(Meedan). **Nobody offers a license-clean, provenance-stamped, back-translation-gated, openly-
published commons of vital-info documents for the long tail of languages.** That is the open lane.

---

## 3. Gaps we can fill

1. **A reviewed, provenanced, license-clean commons** — every artifact ships with `provenance.yaml`,
   exact source version + retrieval date, glossary version, translator (agent + human), reviewer
   sign-off, license, and disclaimer. Nobody publishes vital-info translations with this audit trail.
2. **The long tail of low-resource languages** that WHO/CDC/MoH portals don't reach but where harm
   from bad MT is highest (FLORES-200-poor, >1M-speaker, low existing material).
3. **Per-document license rigor as a public good** — an allow-list that records, per source, whether
   derivatives/translation are permitted, with hashed snapshots and drift-watching. This *de-risks
   reuse for every downstream NGO*, which is itself a deliverable.
4. **High-stakes QA as a gate, not a footnote** — back-translation + two-reviewer + uncertainty-flag
   blocking for dosage/negation content, beating both raw MT (5–8%+ harm) and ad-hoc volunteer work.
5. **Currency** — source-change watching + re-review SLA so translations don't silently go stale (the
   thing static PDF libraries can't do).
6. **Cross-domain umbrella** — one pipeline serving health *and* safety/disaster/civic/legal-rights,
   so glossary/reviewer/license infrastructure is amortized across domains (see siblings, §7).
7. **Machine-readable artifacts** — YAML/Markdown + JSON-Schema-validated metadata that other tools
   (and the siblings) can consume, unlike PDF-first libraries.

---

## 4. Differentiators to win

- **Provenance + license-as-data, enforced in CI.** Every deliverable is *verifiably* correctly
  licensed and attributed (structural check in M0, full source-compatibility enforcement in M1). This
  is the moat: trust + reusability that PDFs and chat sessions can't match.
- **Refuse-to-ship-unreviewed.** Hard human-review gate with back-translation for the riskiest tier —
  the explicit antithesis of Google Translate's documented harm rate.
- **Outcome-based "shipped" = adopted by a beneficiary**, not "merged." Aligns incentives with real
  distribution.
- **Open, forkable commons** under source-compatible licenses — anyone (TWB, MSF, a MoH) can reuse
  with the audit trail intact.
- **Umbrella shared pipeline** that the cancer/Ewing, oncology-glossary, and emergency-phrasebook
  siblings ride on — compounding returns per reviewer/glossary/license hour.
- **Honest cold-start governance** (verifiedNeed, pause/pivot decision point) — credibility with
  serious partners who distrust vaporware.

---

## 5. Claude API leverage (and where Claude must NOT decide)

**Where Claude (donated-lane agent, or funded post-editing) adds leverage:**

1. **First-draft translation + glossary-constrained drafting** — Claude drafts using the language-pair
   glossary, preserving dosages/units/negations/preserved terms verbatim. Draft only — never shipped
   as-is.
2. **Back-translation QA assistant** — Claude produces an *independent back-translation* of the
   reviewed target text for the reviewer to diff against the source; research shows back-translation
   surfaces critical errors. Claude flags divergences; the human adjudicates.
3. **Structured uncertainty self-check** — Claude emits the `UNCERTAIN: <loc> | <type> | <note>` flags
   (term/dosage/negation/cultural/ambiguous-source) that block sign-off until resolved.
4. **Glossary / translation-memory mining** — extract candidate term pairs, detect inconsistent term
   use across documents, propose TM entries for human confirmation (feeds `translation-memory-commons`).
5. **Readability / reading-level adaptation** — adjust register to the target audience while a human
   verifies meaning is preserved (LLM register-leveling is a demonstrated, *low-risk-when-reviewed* use).
6. **License triage assistant** — read a source's terms page and *propose* an allow-list entry
   (derivatives? disclaimer text? attribution string?) for the **human license reviewer to verify** —
   never auto-approve.
7. **Source-drift summarization** — when the watcher flags a hash change, Claude summarizes *what*
   changed to speed human re-verification.

**Where Claude must NOT be the decision-maker (hard rules):**

- **Raw MT/LLM output is never shipped.** Independent evidence: GPT-4 medical translation studies found
  **~34% of translations omitted ≥1 clinically relevant fact and ~6% contained a clinically
  significant inaccuracy**; raw Google Translate carries documented harm potential. Every deliverable
  requires native + domain human review by risk tier.
- **No final sign-off by Claude** on accuracy/safety — that is the qualified (and, for
  dosage/negation, *second + back-translation*) reviewer's call; for advice-giving sources,
  credentialed clinical/legal review by tier.
- **No license self-approval.** Claude may draft an allow-list entry; a human **verifies derivative/
  translation permission and the exact disclaimer wording** before `license-000` passes.
- **No fabricated or "improved" content.** Claude must not add, omit, soften, or invent clinical/legal
  substance; it translates already-vetted guidance verbatim in meaning.
- **No "this is advice" framing.** Claude must preserve the source's authority boundary and the
  "not a substitute for professional advice / original is binding" notice.

(For exact current model IDs / pricing / caching to budget any funded post-editing, consult the
`claude-api` skill rather than hardcoding from memory.)

---

## 6. Ten concrete optimizations

1. **Declare the umbrella as the canonical owner of the shared high-stakes-translation pipeline**
   (schemas, allow-list, glossary, reviewer roster, QA gates) and have siblings depend on it (§7).
   This is the highest-leverage single change.
2. **Add a `risk-tier-by-domain` matrix** to PLAN: factsheet-translation=medium; dosage/negation,
   legal-rights, emergency decision-trees → default to second-reviewer + back-translation; advice-
   giving sources → credentialed domain sign-off.
3. **Bake a "not advice / original is binding / source version + lastVerified" reader notice** into the
   delivery template for *every* deliverable, in target + pivot language.
4. **Make native/near-native target-language reviewer non-waivable** in `reviewers-001`, and add
   **optional in-target reader cognitive debriefing** (ISPOR ~5–8 readers) for flagship documents.
5. **Define a drift→re-review SLA + withdrawal workflow** (e.g., flagged source = freeze new
   deliveries, re-verify within N days, or withdraw + notify partner) — close the watcher's loop.
6. **Publish a machine-readable license/eligibility matrix** (`derivativesAllowed`, `disclaimerText`,
   `attributionTemplate` per source) as a reusable public artifact other NGOs can consume.
7. **Stand up `translation-memory-commons` / glossary as shared, versioned, openly-licensed data**
   from M1, fed by Claude term-mining + human confirmation — amortized across all siblings.
8. **Engage TWB/CLEAR Global early as the reviewer-partner** (named in plan) and Tarjimly's volunteer
   pool as a *secondary* reviewer source — turn the High/High reviewer-sourcing risk into a partnership.
9. **Add an automated negation/dosage/units linter** to CI: flag if numbers, units, or negation tokens
   in source have no corresponding tokens in target (a cheap mechanical safety net before human review).
10. **Bundle a "reuse kit" per deliverable** (source-compatible license text, attribution string,
    disclaimer, provenance, downstream ShareAlike obligation note) so partner adoption is frictionless
    — directly serving the outcome metric (adoption, not merges).

---

## 7. Parallel & perpendicular spin-offs

**Shared infrastructure (the big idea): a `high-stakes-translation` pipeline as Hee-Lee Oss infra.** The
allow-list + license-as-data schema, glossary/TM schema, `provenance.yaml`/`review.yaml` schemas,
the uncertainty-flag protocol, the second-reviewer/back-translation gate, and the CI license/negation
linters are **domain-agnostic**. They should be factored into core Hee-Lee Oss infra so every translation
sibling inherits the same guarantees rather than re-implementing them. `vital-info-translations` is the
natural reference implementation and pipeline owner.

**Parallel spin-offs (same pipeline, different content streams):**
- **`ewing-info-translations`** (and cancer info generally) — oncology patient guidance into under-
  served languages; *higher* clinical stakes → defaults to the second-reviewer + back-translation tier
  and may need credentialed oncology review.
- **`oncology-glossary-multilingual`** — the terminology backbone for the above; should *be* (or feed)
  the shared glossary/TM commons, not a silo.
- **`emergency-phrasebooks`** — short-phrase, fast-turnaround safety/disaster phrases (overlaps Refugee
  Phrasebook; differentiate by provenance + review + license rigor).
- **`first-aid-open`** — translate openly-licensed first-aid guidance (Red Cross / IFRC partnership
  candidate); decision-tree content → higher tier.

**Perpendicular spin-offs (adjacent domains, reuse the QA + license machinery):**
- **`know-your-rights`** — legal-rights / civic info; **raises risk tier** (legal advice) → requires
  credentialed legal review and a strong "not legal advice" notice; reuses the license/provenance infra.
- **`translation-memory-commons`** — the openly-licensed, versioned TM/glossary store that every
  sibling reads/writes; Claude-mined + human-confirmed.
- **`localization-for-good`** — generalize beyond vital info to software/UI strings for nonprofit tools,
  reusing the reviewer network and TM (lower stakes; good reviewer-onboarding funnel).

**Partnership spin-offs:** TWB/CLEAR Global (reviewer-partner + low-resource MT data), IFRC/Red Cross
(first-aid/disaster sources + distribution), Hesperian (Open Copyright content to translate), MSF
field missions and WHO country offices (named partner candidates), Tarjimly volunteer pool (secondary
reviewers), Meedan (misinformation-resilience review for civic content).

---

## 8. Open questions

1. **Umbrella vs. siblings & infra ownership** — is `vital-info-translations` the program *and* the
   home of the shared high-stakes-translation pipeline, or just one content stream? (Highest-impact
   unresolved decision; everything in §7 depends on it.)
2. **First partner** — which NGO/health authority, target language(s), priority documents?
   (`verifiedNeed=true` and M2 blocked on this; the plan's pause/pivot point at end of M1 is sound.)
3. **Reviewer sourcing for genuinely low-resource languages** — when no qualified *health*-translation
   reviewer exists, what is the accepted fallback ladder, and which languages are structurally blocked?
4. **Output license per non-WHO source family** — confirm exact compatible license + disclaimer wording
   for CDC (public domain) vs. MoH (varies). (WHO is settled: CC BY-NC-SA 3.0 IGO + ShareAlike +
   disclaimer.)
5. **Risk-tier escalation triggers** — exact rule for when a document/sibling crosses from medium to
   the credentialed-domain-review tier (proposed matrix in §6.2).
6. **Reader comprehension testing** — do we adopt ISPOR-style cognitive debriefing for flagship docs,
   and who recruits in-target readers?
7. **Delivery formats / complex scripts** — what do partners actually need (plain Markdown vs. print
   layout vs. RTL/complex-script rendering)?
8. **Funded lane for surge** — ever meter Claude post-editing under escrow for outbreak/disaster surge
   demand, within hard budget caps? (Plan defers; revisit if a partner has a time-critical event.)
9. **Migration of the `health-info-translations` pilot** — fold its factsheet/glossary into the
   umbrella, or reference it?

---

### Key sources
- WHO copyright/translation policy (CC BY-NC-SA 3.0 IGO, disclaimer): https://www.who.int/about/policies/publishing/copyright
- CC BY-NC-SA 3.0 IGO deed: https://creativecommons.org/licenses/by-nc-sa/3.0/igo/deed.en
- Google Translate ED-instructions harm study (JGIM/PMC): https://pmc.ncbi.nlm.nih.gov/articles/PMC8606479/
- ED discharge accuracy across 26 languages (2025): https://pubmed.ncbi.nlm.nih.gov/41129839/
- GPT-4 medical translation omission/inaccuracy evidence (MedCOD): https://arxiv.org/pdf/2509.00934
- TWB/CLEAR Global Gamayun + Kató: https://translatorswithoutborders.org/gamayun/ , https://clearglobal.org/resources/gamayun/
- Hesperian Health Guides (Open Copyright, 80+ languages): https://en.wikipedia.org/wiki/Hesperian_Health_Guides , https://hesperian.org/about/
- Tarjimly (volunteer interpretation): https://www.tarjimly.org/ , https://solve.mit.edu/solutions/60179
- Refugee Phrasebook (CC0): https://en.wikipedia.org/wiki/Refugee_Phrasebook
- Meedan Health Desk / Digital Health Lab: https://meedan.org/programs/digital-health-lab
- CDC multilingual resources: https://www.cdc.gov/other/other-languages/index.html
- Back-translation / ISPOR linguistic validation, ISO 17100/18587: https://www.rapporttranslations.com/blog/back-translations
