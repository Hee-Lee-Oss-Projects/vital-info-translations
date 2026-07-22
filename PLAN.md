# PLAN — vital-info-translations

> Status: Draft · Version: 0.2.0 · Last updated: 2026-06-28 · Owner: J. Carter (acting maintainer) · Lane: donated

## Executive summary

`vital-info-translations` is a Hee-Lee Oss good-deed project that translates **vetted, life-critical
public-health and public-safety guidance** (first aid, maternal/child health, vaccine
information, disaster preparedness, water/sanitation) into **low-resource languages** for which
trustworthy translated material is scarce or absent. It graduates the earlier
`health-info-translations` pilot from a single factsheet into a **standing, multi-source,
multi-language program** with explicit license discipline and qualified human review.

The work runs in the **donated lane**: a human runs their own coding agent interactively to draft
translations and supporting artifacts, then opens PRs; the Hee-Lee Oss CLI only prepares workspaces and
opens PRs. Every translation is gated by a **qualified language reviewer with health-translation
competence** (the project is **medium risk tier**) and by a **per-source license check** before it
can be marked delivered.

The defining constraint of this project is **source-license discipline**. Much high-quality
source material (notably WHO content) is **not** CC-BY: it carries the source's own reuse terms
plus a **mandatory translation disclaimer**. We therefore operate from a **per-source allow-list**
with recorded license terms and required attribution, and we **never relicense copyrighted source
material**. A translation that cannot be correctly licensed and attributed is not shipped.

Honest status note: the program is real but **no specific partner NGO or health authority is yet
secured** for first delivery. Until one is, `verifiedNeed` is recorded as `false` on tasks whose
value depends on a named beneficiary, and Definition of Shipped cannot be fully met. Securing a
first partner is the top open dependency (see Open questions and Roadmap M0).

## Problem & beneficiaries

**Who is helped.** Community health workers, frontline NGOs, and the public in regions whose
primary languages are "low-resource" — i.e., poorly served by commercial machine translation and
lacking professionally translated, authoritative health/safety material. The ultimate
beneficiaries are **readers making life-or-death decisions** (a parent treating childhood
diarrhoea, a midwife managing post-partum bleeding, a household preparing for a flood) who today
must rely on a language they do not read well, on inaccurate machine output, or on nothing.

**The need.** In many languages, authoritative guidance exists only in a handful of pivot
languages (English, French, Arabic, Spanish). Generic machine translation of medical text is
unsafe: it mistranslates dosages, negations ("do **not** induce vomiting"), and preserved terms,
and it carries no provenance or review. The gap is **accurate, attributed, reviewed** translation
that an NGO can actually distribute.

**Verified need: TO BE SECURED.** The proposal marks the need "yes (to be confirmed per
partner)." We treat that honestly: the *category* need is well-evidenced, but a **specific
requesting NGO/health authority, target language set, and priority document list are not yet
secured.** Tasks are written so the program can build reusable foundations (allow-list, glossary,
templates) without a partner, while flagging that **delivery/adoption tasks are blocked** until a
partner and target language are confirmed.

**Partner org: TO BE SECURED.** Candidate partner types: MSF field missions, national Ministries
of Health, WHO country offices, Translators without Borders / CLEAR Global, and regional refugee/
disaster-response NGOs. None is committed as of this draft.

## Goals and non-goals

**Goals**
- Stand up a **repeatable pipeline** to translate vetted public-health/safety documents into
  low-resource languages with full provenance and license compliance.
- Maintain a **per-source allow-list** that records, for each source, the exact reuse terms,
  required attribution, and any mandatory disclaimer (e.g., WHO translation disclaimer).
- Produce, per language pair, a **preserved-terminology glossary** and a **reviewer checklist**
  so quality is consistent and auditable.
- Guarantee **qualified human review** of every translation before delivery (medium risk tier).
- Deliver translation sets that a partner NGO/health authority **actually adopts and distributes**.

**Non-goals**
- **Not** a general-purpose machine-translation service or website; we do not translate arbitrary
  user-submitted text on demand.
- **Not** original medical authorship — we translate **already-vetted** guidance; we do not write
  new clinical advice. (Writing new high-stakes guidance would be **high** risk and out of scope.)
- **Not** relicensing or "freeing" copyrighted source material; we honor each source's terms.
- **Not** legal, immigration, or financial advice; scope is health/safety guidance only.
- **Not** real-time / interpreting / emergency-hotline translation.
- **Not** building speech, OCR, or layout/DTP tooling beyond what delivery formats require.

## Success metrics (outcomes)

Outcome-based and beneficiary-centric. Baselines are ~0 because this extends a single-factsheet
pilot. The **outcome** targets below are for the first ~6 months after a partner is secured; the
**interim foundation metrics** are tracked from M0/M1 so progress is visible *before* a partner
exists.

**Outcome metrics (post-partner)**

| Metric | Baseline | Target | How measured |
|---|---|---|---|
| Reviewed translation sets **adopted by a partner** for distribution | 0 | ≥ 3 documents in ≥ 1 language | Partner written confirmation in the PR/receipt |
| Low-resource **languages covered** end-to-end (allow-list → reviewed → delivered) | 0 | ≥ 2 | Project registry |
| Translations passing **qualified reviewer sign-off on first or second pass** | n/a | ≥ 90% (**effective from M1**) | Reviewer checklist outcomes |
| **License/attribution compliance** of delivered artifacts (disclaimer + provenance present) | n/a | 100% (hard gate; **automated from M1**, manual check in M0) | License-check task / CI per deliverable |
| **Critical accuracy defects** found *after* delivery (dosage/negation/term errors) | n/a | 0 | Post-delivery feedback log |
| Partner-reported **usefulness** of delivered set (qualitative) | n/a | Positive from ≥ 1 partner | Partner feedback |

**Interim foundation metrics (M0/M1, partner-independent)**

| Metric | Baseline | Target | How measured |
|---|---|---|---|
| Sources **verified** and recorded on the allow-list | 0 | ≥ 3 by end of M0 | Allow-list entries with `verifiedBy`/`verifiedDate` |
| Glossary **terms** captured (per language pair) | 0 | ≥ 30 per pair | Glossary file entry count |
| Reviewers **qualified** (criteria met + onboarded) | 0 | ≥ 2 by end of M1 | Reviewer roster |
| **Cycle time** per factsheet (draft → reviewer sign-off → license-clear) | n/a | Tracked; trend down | Timestamps on PR/review artifacts |

**Denominator & sample rule for the "≥ 90% pass" rate.** The denominator is **every translation
deliverable that reaches qualified review** (counted once per deliverable, not per review pass); a
deliverable "passes" if it earns reviewer sign-off on its **first or second** pass. The rate is
reported **only once the denominator is ≥ 10** reviewed deliverables (minimum sample); below that we
report the raw count (e.g., "7/8 passed") rather than a percentage to avoid small-sample noise.

We explicitly **do not** count "PRs merged," "words translated," or "documents drafted" as
success — only **reviewed, correctly-licensed material adopted by a beneficiary**.

## Scope

**Definition — "low-resource language" (objective).** For this project a target language qualifies
as low-resource if it meets **at least two** of: (a) it is **absent or below a usable quality
threshold on a named MT benchmark** (we use the **FLORES-200** evaluation set as the reference; a
language not in FLORES-200, or scoring poorly there, qualifies); (b) it has a **large speaker base
relative to available authoritative health material** (we do not use a raw speaker-count cut-off
alone, but flag languages with **> ~1M speakers and little/no professionally translated health
guidance**); and (c) **professional translated public-health material is scarce or absent**.
**Reviewer availability is a hard precondition, not a qualifier**: we only schedule a language for
which a qualified reviewer can be sourced (see Risks).

**Prioritization rule.** Among qualifying languages, prioritize in this order: (1) a **secured
partner's** stated target language; (2) largest **affected/at-risk population** with the **weakest
existing material**; (3) **reviewer coverage already available**; (4) **source documents already
allow-listed** for that topic. Ties break toward the language that lets us reuse existing glossary
work.

**In scope**
- Source **allow-list** with per-source license terms, attribution strings, and disclaimers.
- Translation of **specific vetted documents** (WHO/MoH/CDC/MSF factsheets) into named target
  languages, decomposed per *document × language*.
- Per-language-pair **glossary** of preserved/medical terminology and transliteration rules.
- **Reviewer-handoff template** and **reviewer checklist**; sign-off recorded in the PR.
- **License-verification** step per source and per deliverable.
- Delivery packaging: source text, translation, glossary refs, provenance, attribution +
  disclaimer, reviewer sign-off.

**Out of scope**
- Translating sources **not** on the allow-list, or whose license is unverified/incompatible.
- Authoring new medical/safety content or altering the meaning of source guidance.
- High-stakes content requiring **credentialed clinical sign-off to create** (vs. to review a
  translation of already-authoritative guidance).
- Audio/video, OCR of scanned PDFs, typesetting in complex scripts beyond Unicode plain text /
  simple formats unless a partner requires it (then scoped as future work).
- Hosting, a public website, or a self-serve translation portal.
- Languages where **no qualified reviewer** can be sourced (we will not ship unreviewed health
  translations — see Risks).

## Solution approach & architecture

This is primarily a **content/data pipeline** project (deliverables are translations + data
artifacts), with light tooling. It rides on existing Hee-Lee Oss donated-lane mechanics (CLI prepares
workspace, human runs agent, PR opened, human/expert review gates "done").

**Pipeline (per document × language)**
1. **Select & verify source** — confirm the document is on the allow-list; re-verify the source's
   current license terms and required disclaimer; record provenance (URL, version/date, retrieval
   date, license snapshot).
2. **Draft translation** — agent drafts the translation using the language-pair **glossary**,
   preserving dosages, units, negations, and listed medical terms verbatim/as specified.
3. **Self-check** — agent runs the reviewer checklist as a first pass and flags uncertainties.
4. **Qualified review** — a human reviewer with health-translation competence verifies accuracy
   and safety, completes the checklist, and **records sign-off in the PR**.
5. **License & attribution check** — confirm attribution string + mandatory disclaimer present and
   correct; confirm output license is compatible with the source terms.
6. **Package & deliver** — assemble the delivery bundle and hand off to the partner; record
   adoption.

**Artifacts / data model**
- `sources/allow-list.yaml` — array of source entries: `{ id, name, url, licenseName,
  licenseUrl, reuseTerms, requiresDisclaimer, disclaimerText, attributionTemplate,
  derivativesAllowed, snapshotHash, snapshotArchiveUrl, notes, verifiedBy, verifiedDate }`
  (`snapshotHash` = SHA-256 of the captured license/source text; `snapshotArchiveUrl` = web-archive
  copy where available).
- `glossaries/<src>-<tgt>.yaml` — `{ term, translation|preserve, partOfSpeech, notes }` entries
  plus transliteration/units conventions.
- `translations/<doc>/<lang>/` — `source.txt` (or reference), `translation.md`,
  `provenance.yaml`, `attribution.txt` (incl. disclaimer), `review.yaml` (checklist + sign-off).
- `templates/reviewer-checklist.md`, `templates/reviewer-handoff.md`.

**Formats.** UTF-8 throughout; Markdown/plain text as the canonical translation format; YAML for
metadata. Partner-specific export formats are added only on request.

**Content schemas & CI validation.** The Task JSON schema lives in
`packages/schema/src/schemas.ts` (AJV / JSON Schema **draft-07**). The project's **content/data
artifacts get their own JSON Schemas in the same place** — `allowListSchema`, `glossarySchema`,
`provenanceSchema`, and `reviewSchema` exported from `packages/schema/src/schemas.ts`, compiled and
exposed via `validate.ts` exactly like `taskSchema`/`registrySchema` (AJV with `ajv-formats`). YAML
artifacts (`allow-list.yaml`, `glossaries/*.yaml`, `provenance.yaml`, `review.yaml`) are parsed to
JSON and validated against these schemas by a structural-check script (`tooling-001`) wired into
`pnpm test` so **CI fails on any malformed or non-conformant content file**. The license gate
(`license-002`) builds on this by additionally cross-checking each deliverable's metadata against
its allow-list source entry. This keeps validation **agent-neutral** and in the core schema package,
not in adapters.

**Key decisions**
- **Allow-list first, license-as-data.** Licensing is encoded as structured, checkable data, not
  prose buried in a doc — so the per-deliverable license gate can be verified consistently.
- **Glossary-driven drafting** to make preserved terminology and unit handling deterministic and
  reviewable.
- **Output license follows the source**, not a blanket CC-BY. The project's *code/tooling* is MIT;
  *translated content* carries the source-compatible license + required disclaimer (see below).
- **No partner data ingestion** — we pull only from public, allow-listed sources, minimizing
  privacy/PII surface.

## Data, licensing & compliance

**This is the project's most important section. Be conservative; when terms are unclear, do not
translate.**

**Sources & licenses (per-source allow-list).** Only sources on the allow-list may be translated,
and each must have its terms **verified and recorded** before use:

- **WHO content** — typically governed by **WHO's own reproduction/translation terms (CC BY-NC-SA
  3.0 IGO for many publications)**, **not** generic CC-BY. WHO translations require a **mandatory
  translation disclaimer** stating WHO did not produce/endorse the translation and that the
  original is the binding edition. We **must** include this disclaimer and the WHO attribution;
  derivative/commercial restrictions must be honored. **Verify the exact license on each WHO
  document — terms vary by publication.**
- **National Ministries of Health (MoH)** — terms vary widely (Crown copyright, government open
  licenses, all-rights-reserved). **Each MoH source verified individually**; do not assume reuse
  is permitted.
- **US CDC** — most CDC-authored work is **U.S. public domain**, but CDC pages often embed
  third-party copyrighted material; verify per document and attribute.
- **MSF and other NGOs** — terms vary; many are all-rights-reserved. **Verify and, where needed,
  obtain written permission** before translating.

For **each** source we record: canonical URL, version/date, retrieval date, license name + URL, a
**snapshot of the license text**, whether derivatives/translations are permitted, the required
attribution string, and any mandatory disclaimer.

**Snapshot integrity (hash/archive-based).** The license snapshot is **not** loose prose: we store
the captured license text (and the source document) as a committed archive copy plus a recorded
**SHA-256 content hash** and, where possible, a web-archive (Wayback) URL. A **source-change
watcher** (built in M0 as a minimal manual/scripted re-fetch check, automated in M1) periodically
re-fetches each allow-listed source, recomputes the hash, and **flags any drift** in the source or
its license terms for re-verification before further translation or delivery. This moves
source-change detection out of the backlog and into the foundation milestones.

**BLOCKING prerequisite for the first translation.** Before `translate-001` may start, the
maintainer/license reviewer must have **confirmed in writing, recorded on the chosen source's
allow-list entry**: (a) that the source's terms **permit derivative works/translation**, and (b)
the **exact disclaimer wording** required (verbatim, e.g. the WHO translation disclaimer). This is a
**hard gate, not an open question** — if either is unconfirmed for the candidate document, that
document is **not** translated and the task selects a different allow-listed source that satisfies
both conditions.

**Provenance model.** Every deliverable ships a `provenance.yaml` linking it to its source
entry, version, retrieval date, glossary version, translator (agent + human), and reviewer +
sign-off. Provenance is non-optional and is part of the license gate.

**Output licensing.** Translated content is released under a license **compatible with the
source** (e.g., for WHO CC BY-NC-SA 3.0 IGO material, the translation inherits BY-NC-SA-style
terms **plus** the WHO translation disclaimer — **not** CC-BY, and **not** a more permissive
relicense). Where a source forbids derivatives or relicensing, we either obtain permission or do
not translate it. **Project tooling/code is MIT**; that does not extend to the translated content.

**Privacy / PII.** Sources are public health/safety guidance; we ingest **no personal data** and
collect no end-reader data. PII surface is minimal by design. Partner contact details are handled
out-of-band and never committed.

**Attribution requirements.** Every deliverable includes the source attribution string and any
mandatory disclaimer verbatim, in both the target language and a pivot language where the partner
requires it.

## Quality, review & risk gates

**Risk tier: medium.** Per the good-deed definition, medium = needs domain accuracy and a
**reviewer with the relevant skill** — here, a **qualified language reviewer with
health-translation competence** for the specific language pair. (Note: translating *already
authoritative* guidance is medium; *authoring* new high-stakes medical guidance would be high and
is out of scope.)

**Required review before a deed is "done"**
1. **Agent self-check** against the reviewer checklist (first pass; not sufficient alone), including
   the **uncertainty self-check** below.
2. **Qualified human reviewer** sign-off recorded in the PR (accuracy, safety, preserved terms,
   negations, dosages/units, cultural appropriateness).
3. **License & attribution verification** (disclaimer + provenance + compatible output license).
4. **CI green** for any code/tooling and for structural checks on metadata files.
5. **Maintainer approval** of the PR.

**Reviewer independence & two-reviewer rule.** Reviewers must be **independent of the drafting
step** — the human who ran the drafting agent may **not** be the sole sign-off reviewer for that
deliverable, and each reviewer records a **conflict-of-interest declaration**. A **second
independent qualified reviewer is mandatory** for any document containing **dosage, negation, or
other directly safety-critical instructions** (single-reviewer sign-off is permitted only for
content with no such elements). For the **highest-risk documents** (those with dosages/negations),
**back-translation QA is mandatory** — an independent back-translation compared against the source
before sign-off — promoting it from a backlog "nice-to-have" to a required gate for that tier.

**Reviewer disagreement / conflict resolution.** If reviewers disagree, the deliverable **cannot be
signed off** until resolved. Resolution order: (1) reviewers attempt to reconcile against the source
and glossary, recording the rationale; (2) unresolved safety-critical disagreements are escalated to
a **third qualified reviewer or the maintainer**, whose decision is recorded; (3) when in doubt, the
**more conservative reading wins** and the disputed passage is held back rather than shipped. The
disagreement and its resolution are recorded in `review.yaml`.

**Agent uncertainty self-check (operationalized).** The drafting agent must, as part of step 1,
**emit explicit uncertainty flags** in a defined format — one entry per flag of the form
`UNCERTAIN: <location> | <type: term|dosage|negation|cultural|ambiguous-source> | <note>` — for any
passage it is not confident about. These flags are **copied into the `review.yaml` artifact** as an
`agentFlags` list. **No reviewer sign-off may be recorded while any flag remains unresolved**: each
flag must be marked `resolved` (with the reviewer's adjudication) or explicitly `accepted-as-is`
with reasoning. Unresolved flags **block** sign-off and therefore "done".

**Definition of Shipped (project-specific).** A translation set is *shipped* only when: acceptance
criteria met **and** qualified reviewer sign-off recorded **and** license/attribution/disclaimer
verified **and** provenance complete **and** CI green **and** the set is **delivered to and
adopted by the requesting NGO/health authority** for distribution. Merged-but-not-adopted is
**not** shipped.

## Roadmap & milestones

**M0 — Foundation & cold-start (no partner required).**
Goal: stand up the license/glossary/review machinery and prove the pipeline on one factsheet into
one language, end-to-end except final adoption.
Exit criteria: allow-list exists with ≥ 3 verified sources (with hash/archived license snapshots
and a minimal source-change re-fetch check); reviewer checklist + handoff template merged; one
language-pair glossary started; **the first translation's BLOCKING license prerequisite confirmed
and recorded** (derivative/translation permission + exact disclaimer wording on the source entry)
**before drafting begins**; **one WHO/MoH factsheet translated into one target language with
qualified reviewer sign-off and a passing license/attribution check** (delivery to a partner
deferred to M2). Status of `verifiedNeed` honestly recorded as `false` where no partner.
**License-gate note:** to keep the "100% license/attribution compliance" hard gate honest from the
start, M0 ships a **minimal automated structural check** (`tooling-001`) that fails CI if the
required attribution/disclaimer/provenance **fields are absent or malformed**; the **full
source-compatibility enforcement is automated in M1** (`license-002`). The 100% and ≥ 90% metrics
are therefore reported as **effective from M1**, with M0 verifying the first deliverable manually
plus this structural check.

**M1 — Repeatability & reviewer network.**
Goal: make the pipeline repeatable and recruit/qualify reviewers.
Exit criteria: documented reviewer-qualification criteria + ≥ 2 named qualified reviewers (or a
partner such as Translators without Borders engaged); glossary + checklist generalized to ≥ 2
language pairs; license-check step formalized as a checklist/tooling; **automated source-change
watcher (hash-diff against stored snapshots) operating**; a second factsheet translated & reviewed.
Dependency: reviewer sourcing.

**M2 — First partner delivery (needs partner).**
Goal: deliver an adopted translation set.
Exit criteria: a partner NGO/health authority secured (`verifiedNeed = true`); target language +
priority document list agreed; **≥ 1 reviewed, correctly-licensed translation set delivered and
confirmed adopted** by the partner. This is the first true "Definition of Shipped" event.
Dependency: M0/M1 + partner.

**M3 — Scale program.**
Goal: scale to multiple documents/languages with sustained quality.
Exit criteria: ≥ 3 documents across ≥ 2 languages adopted; reviewer rotation established; outcome
tracking (post-delivery defect log, partner feedback) operating; sustainability/maintenance owner
named.

## Work breakdown

The itemized, sized backlog lives in **[TASKS.md](./TASKS.md)**, organized by the milestones
above (M0–M3) plus a Backlog/future section. Each task maps to a Hee-Lee Oss Task JSON (see the schema
in `packages/schema/src/schemas.ts`) with id, type, lane, risk tier, deliverable, acceptance
criteria, and license fields. M0 tasks are partner-independent foundations; M2+ tasks are gated on
a secured partner and are marked accordingly (`verifiedNeed: false` until then).

## Governance, roles & stakeholders

- **Maintainer (Owner): J. Carter (acting)** — assigned now; accepts/sequences tasks, approves PRs,
  owns the allow-list integrity and the license gate. Acts as interim license/compliance reviewer
  until a dedicated reviewer is named.
- **Qualified reviewers (per language pair): TO BE SECURED** — health-translation-competent
  reviewers; sign-off recorded in PRs. Rotation defined in M1.
- **License/compliance reviewer** — may be the maintainer initially; verifies per-source terms and
  per-deliverable attribution/disclaimer. Escalates ambiguous licenses.
- **Steward (last-mile owner): TBD — to be named by end of M1** (the acting maintainer holds these
  duties in the interim). Owns the partner relationship and confirms **adoption** (without this,
  nothing reaches "shipped"). Naming a steward is a **prerequisite for entering M2**.
- **Partner / requestor: TO BE SECURED** — NGO/health authority defining language + document
  priorities and confirming adoption.
- **Expert reviewers** — for any item that drifts toward authoring high-stakes content, a
  credentialed clinical expert is required (and the item should likely be rejected as out of
  scope instead).

## Dependencies & integrations

- **Hee-Lee Oss donated lane**: `packages/cli` (workspace prep + PR), `packages/core`,
  `packages/schema` (Task JSON). No funded-lane / API-key execution in this project.
- **Public source sites**: WHO, national MoH portals, CDC, MSF (read-only retrieval; license
  verification per source).
- **Human reviewers / a translation NGO** (e.g., Translators without Borders / CLEAR Global) for
  qualified review — **external dependency, not yet secured**.
- **Partner NGO/health authority** for requirements + adoption — **not yet secured**.
- **Glossary/terminology references** per language (e.g., WHO/medical terminology lists), subject
  to their own licenses.

## Risks & mitigations

| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Mistranslation of safety-critical content (dosage, negation, units) causes harm | Medium | Critical | Glossary-driven drafting; mandatory qualified-reviewer sign-off; checklist explicitly targets dosages/negations/units; post-delivery defect log | Reviewers / Maintainer |
| License violation — relicensing or omitting required disclaimer (esp. WHO) | Medium | High | Per-source allow-list with recorded terms; per-deliverable license gate; output license follows source; "if unclear, don't translate" | License reviewer / Maintainer |
| No qualified reviewer available for a target language | High | High | Don't ship unreviewed; partner with translation NGO; scope only languages with reviewer coverage | Steward / Maintainer |
| No partner secured → nothing reaches "shipped" | High | High | M0/M1 build partner-independent value; **concrete outreach plan** (below) with named target types, owner, and timeline; `verifiedNeed=false` until secured; **pause/decision point if no partner** | Acting maintainer → Steward |
| Source content changes/retracted after translation | Medium | Medium | Record version + retrieval date in provenance; re-verify before delivery; note original is binding | Maintainer |
| Scope creep into authoring new medical advice (high risk) | Medium | High | Explicit non-goal; reject such tasks; require clinical expert if ever attempted | Maintainer |
| Cultural inappropriateness / loss of meaning | Medium | Medium | Native-speaker qualified review; cultural-appropriateness item in checklist | Reviewers |
| Agent overconfidence / unflagged uncertainty | Medium | High | Operationalized self-check emits `UNCERTAIN:` flags into `review.yaml`; unresolved flags **block** sign-off; reviewer treats agent output as draft only | Reviewers |

## Security & privacy

- **Threat surface** is small: public source ingestion + text artifacts in a public repo. Main
  risks are **integrity** (wrong/tampered source, mistranslation) and **license/compliance**, not
  data exfiltration.
- **No secrets** in this project's normal flow (donated lane uses the human's own agent; no API
  keys, tokens, or escrow). Per CLAUDE.md, never write secrets/tokens into logs, receipts, or
  committed files.
- **PII**: none ingested; partner contacts kept out-of-band and uncommitted.
- **Abuse/misuse prevention**: refusal guardrails apply — refuse tasks that would inject
  misinformation, target/deceive people, give unqualified high-stakes advice, primarily benefit a
  for-profit, or violate a source license/privacy. Source integrity verification (correct,
  current, authoritative source) is part of every translation task.
- **Supply-chain**: pin source URLs + version/date; **hash/archive the license + source snapshot**
  and run a source-change watcher (hash-diff) to detect later changes (M0 minimal, M1 automated).

## Sustainability & maintenance

- **After delivery**, the maintainer + steward keep the allow-list and glossaries current and
  re-verify sources when upstream documents change. Reviewer rotation (M1/M3) avoids single-person
  dependence.
- **Outcome tracking** continues post-delivery: a defect/feedback log per delivered set, and
  periodic partner check-ins to confirm continued use and capture errors. Outcomes (adoption,
  defects, usefulness) — not merge counts — are the maintained metrics.
- **Decommissioning**: if a source's license changes to forbid reuse, affected deliverables are
  flagged and, if required, withdrawn; provenance makes impact assessment possible.

## Open questions

1. **Partner**: which NGO/health authority is the first requestor, and what are their target
   language(s) and priority documents? (Blocks M2 and `verifiedNeed=true`.) **Partner-sourcing plan
   (now concrete, not just "top priority"):**
   - **Outreach target types (named):** Translators without Borders / CLEAR Global (also the
     reviewer-partner candidate), MSF field missions, WHO country offices, national Ministries of
     Health, and regional refugee/disaster-response NGOs.
   - **Owner:** the **acting maintainer** runs outreach until a Steward is named (by end of M1),
     who then takes it over.
   - **Timeline:** begin outreach in parallel with M0; aim for **≥ 3 serious conversations by end
     of M1** and a **signed/agreed first partner during M2 sourcing** (`partner-001`).
   - **Pause/decision point:** if **no partner is secured by the end of M1** (M0/M1 foundations
     complete), the program **pauses new translation work** and the maintainer makes an explicit
     **go / pivot / hold** decision (e.g., pivot to a pure open-distribution model, or hold until a
     partner appears) rather than drafting more translations no one has committed to adopt.
2. **Reviewer sourcing**: do we recruit individual qualified reviewers or partner with a
   translation NGO (e.g., Translators without Borders/CLEAR Global)? What are the formal
   qualification criteria?
3. **Output license per source family**: confirm the exact compatible output license + disclaimer
   wording for **CDC (public domain) vs. MoH (varies)**. (The WHO derivative/translation permission
   and **exact disclaimer wording** are no longer an open question — they are now a **blocking
   prerequisite** of the first translate task; see Data, licensing & compliance.)
4. **Delivery formats**: what formats/scripts do partners actually need (plain Markdown vs. print
   layout, complex-script rendering)?
5. **Relationship to `health-info-translations` pilot**: migrate its factsheet/glossary in, or
   keep separate and reference?
6. **Funded lane?** Proposal says donated; do we ever want metered drafting under escrow for
   surge demand? (Out of scope for v0.1.)

## References

- `C:\code\hee-lee-oss\CLAUDE.md` — Hee-Lee Oss work rules, lanes, quality bar, refusal guardrails.
- `C:\code\hee-lee-oss\docs\good-deed-definition.md` — good-deed criteria and risk tiers.
- `C:\code\hee-lee-oss\packages\schema\src\schemas.ts` — Task JSON schema.
- `C:\code\hee-lee-oss\governance\proposals\vital-info-translations.md` — originating proposal.
- WHO permissions & licensing / translation policy (verify current terms per publication).
- CDC content-use / public-domain notice (verify per page for embedded third-party content).
- Translators without Borders / CLEAR Global (candidate reviewer partner).
