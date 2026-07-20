# Layer 2 · Section 1 — Acceptance Criteria / Definition of Done Failure Modes

> **Role in the library:** Catalogues the seven recurring failure modes discovered in the
> Product OS deep-dive research on Acceptance Criteria and Definition of Done. These are the
> breakdowns that occur where the team decides *what the feature should do* and *whether the
> increment is ready to ship*.
>
> **Owning subtask:** DIV-48.
> **Workflow stage:** `Acceptance Criteria / Definition of Done` (Layer 1 CN-04, CN-05, CN-06;
> with CN-02 and CN-09 touched where noted).
> **Source documents:** 6–7, with Document 2 (persona/JTBD) contributing to demo and
> misalignment entries.
> **Ids:** FM-01 … FM-07.
> **Schema:** every entry conforms to [§0](00-schema-and-organization.md). The Framework-5
> separation and underserved matrix are consolidated in [§5](05-framework-5-separation-and-underserved-gaps.md).

---

## The stage in one line

Document 6 established the load-bearing distinction: **Acceptance Criteria (CN-04) answer
"What should the feature do?"; Definition of Done (CN-05) answers "Is the increment ready to
ship?"; Product Owner acceptance (CN-06) is generally embedded within DoD.** Document 7 then
studied *where this workflow fails* — and found practitioners consistently discuss operational
symptoms while "almost nobody frames the larger problem as a cohesive validation capability."
The seven entries below preserve that practitioner language.

---

## FM-01 · Ambiguous Acceptance Criteria

- **`failure_mode_id`:** `FM-01` · **`slug`:** `fm-ambiguous-acceptance-criteria`
- **`workflow_stage`:** `Acceptance Criteria / Definition of Done` · **`concept_nodes`:** `CN-04`, `CN-02`
- **`observable_symptoms`:**
  - "Acceptance criteria are written ambiguously, leading to different interpretations."
  - Stories are accepted with different understandings of what "done" means.
  - Developers interpret the same story differently.
- **`evidence_signals`:**
  - Stories reopened after being marked accepted.
  - Long Sprint Review discussions reconciling what was actually meant.
  - Repeated clarification questions on the same story during implementation.
- **`current_workarounds`:**
  - Ad hoc clarification meetings during the sprint.
  - Asking engineering to explain what was actually built.
  - Manual back-and-forth to reconcile interpretations after the fact.
- **`expert_best_practice`:** Per Document 6, mature organizations (Microsoft, GitLab,
  Atlassian) write AC that answer "What should the feature do?" unambiguously and agree them
  collaboratively during refinement (Three Amigos, CN-02) — GitLab's DoD checklist and
  Atlassian's collaborative AC refinement are the reference model.
- **`practitioner_pain`:** AC are written ambiguously and agreed only nominally, so the same
  story is implemented and accepted against different mental models; the mismatch is
  discovered late, not prevented early.
- **`underserved_by_existing_tools`:** `Partially served` — Jira / Azure DevOps store AC as
  free text but neither test them for ambiguity nor confirm shared understanding.
- **`source_documents`:** ["6", "7"]

## FM-02 · Subjective Product Owner Approval

- **`failure_mode_id`:** `FM-02` · **`slug`:** `fm-subjective-po-approval`
- **`workflow_stage`:** `Acceptance Criteria / Definition of Done` · **`concept_nodes`:** `CN-06`, `CN-05`
- **`observable_symptoms`:**
  - PO acceptance rests on subjective judgment rather than agreed evidence.
  - "Product Owners don't 'trust' that the Acceptance Criteria were met — they verify them
    through evidence" (Document 6) — but in practice that evidence is often missing or
    inconsistent.
  - Acceptance decisions vary by who the PO is and what mood the review is in.
- **`evidence_signals`:**
  - Accept/reject decisions that can't be traced to a specific piece of evidence.
  - Re-litigation of "is this done?" across multiple reviews.
  - Different POs accepting comparable work to different standards.
- **`current_workarounds`:**
  - PO watches a demo and accepts on the spot.
  - Verbal reassurance from engineering substitutes for evidence.
  - Extra sign-off meetings to build confidence.
- **`expert_best_practice`:** Document 6 found mature organizations embed PO acceptance
  *within* the Definition of Done and make it evidence-based — the PO verifies AC satisfaction
  through evidence rather than trusting an assertion.
- **`practitioner_pain`:** Acceptance is subjective because the agreed evidence either doesn't
  exist or isn't assembled, so signoff becomes a judgment call.
- **`underserved_by_existing_tools`:** `Underserved` — no existing tool assembles the evidence
  a PO needs to make acceptance objective; the acceptance decision lives in meetings.
- **`source_documents`:** ["6", "7"]

## FM-03 · Missing Evidence

- **`failure_mode_id`:** `FM-03` · **`slug`:** `fm-missing-evidence`
- **`workflow_stage`:** `Acceptance Criteria / Definition of Done` · **`concept_nodes`:** `CN-04`, `CN-05`
- **`observable_symptoms`:**
  - No agreed-upon evidence for different product types (consumer products, APIs,
    infrastructure, AI products).
  - Practitioners struggle to say what evidence is *sufficient* to call a story done.
  - "How do we prove this actually satisfies the AC?" recurs with no standard answer.
- **`evidence_signals`:**
  - Acceptance based on demo alone, with no captured artifacts.
  - Evidence scattered across QA tools, CI logs, and screenshots — never assembled.
  - Disagreement at acceptance over whether the proof is enough.
- **`current_workarounds`:**
  - Manually collecting screenshots, logs, and test results per story.
  - Relying on QA's word that tests passed.
  - Accepting without evidence and reopening later if problems surface.
- **`expert_best_practice`:** Document 6 catalogued the *evidence types* mature organizations
  use per product type — Microsoft, GitLab, and Atlassian tie AC/DoD satisfaction to
  product-appropriate evidence (consumer UX behavior, API contract behavior, infrastructure
  reliability, AI output quality).
- **`practitioner_pain`:** Teams lack an agreed, product-appropriate evidence standard, so
  "done" is asserted rather than demonstrated.
- **`underserved_by_existing_tools`:** `Underserved` — test-management and CI tools produce
  evidence in fragments; no tool defines or assembles the *sufficient evidence set* for
  acceptance across product types.
- **`source_documents`:** ["6"]

## FM-04 · Late Validation

- **`failure_mode_id`:** `FM-04` · **`slug`:** `fm-late-validation`
- **`workflow_stage`:** `Acceptance Criteria / Definition of Done` · **`concept_nodes`:** `CN-08`, `CN-09`
- **`observable_symptoms`:**
  - Validation happens too late — at Sprint Review or UAT rather than continuously.
  - Problems that could have been caught during implementation surface only at the review gate.
  - The first real check against intent is the demo.
- **`evidence_signals`:**
  - Defects and misunderstandings clustering at Sprint Review / UAT.
  - Stories bouncing back after the review rather than during the sprint.
  - Review meetings running long because validation is happening *in* them.
- **`current_workarounds`:**
  - Batch validation at the end of the sprint.
  - Extending Sprint Review to absorb the validation work.
  - Hotfix cycles after late discovery.
- **`expert_best_practice`:** Document 7's practitioner findings and Document 6's continuous
  evidence model point to validating *throughout* delivery — the continuous-collaboration
  practice (CN-07) rather than a single end-of-sprint gate.
- **`practitioner_pain`:** Validation is deferred to the review gate, so misalignment is
  expensive to fix by the time it is seen.
- **`underserved_by_existing_tools`:** `Partially served` — CI runs tests continuously, but
  no tool validates *implementation against product intent* before stakeholder review.
- **`source_documents`:** ["7"]

## FM-05 · Unclear Ownership

- **`failure_mode_id`:** `FM-05` · **`slug`:** `fm-unclear-ownership`
- **`workflow_stage`:** `Acceptance Criteria / Definition of Done` · **`concept_nodes`:** `CN-06`, `CN-02`
- **`observable_symptoms`:**
  - Fragmented responsibility for acceptance decisions across PM, QA, and Engineering.
  - "Whose call is it whether this is done?" has no consistent answer.
  - Acceptance falls between roles — everyone assumes someone else verified it.
- **`evidence_signals`:**
  - Acceptance decisions with no clear owner in the tool or the meeting.
  - Finger-pointing when accepted work turns out to be wrong.
  - Duplicated or skipped verification because ownership is unclear.
- **`current_workarounds`:**
  - Convening all three roles to co-own the decision by committee.
  - Informal norms about who signs off, varying by team.
  - PM absorbing the reconciliation work by default.
- **`expert_best_practice`:** Document 6 found mature organizations embed acceptance ownership
  in the DoD (PO acceptance embedded within Definition of Done) with the Three Amigos (CN-02)
  giving Product, Engineering, and QA a shared, role-clear verification practice.
- **`practitioner_pain`:** Responsibility for the acceptance decision is fragmented across
  three roles, so verification is inconsistent and accountability is diffuse.
- **`underserved_by_existing_tools`:** `Partially served` — workflow tools model assignee and
  status but not *acceptance ownership* across the PM/QA/Engineering boundary.
- **`source_documents`:** ["7"]

## FM-06 · Demo Difficulties

- **`failure_mode_id`:** `FM-06` · **`slug`:** `fm-demo-difficulties`
- **`workflow_stage`:** `Acceptance Criteria / Definition of Done` · **`concept_nodes`:** `CN-09`
- **`observable_symptoms`:**
  - "Demos show happy paths but hide edge cases and implementation nuances." (Document 2)
  - "PM depends on engineering to explain what was actually built." (Document 2)
  - The demo looks fine; the actual behavior under real conditions is unknown.
- **`evidence_signals`:**
  - Edge-case defects appearing after a demo that "passed."
  - PM asking engineering post-demo "so what actually changed?"
  - Acceptance granted on a happy-path demo, reopened when edge cases surface.
- **`current_workarounds`:**
  - PM watches the demo and accepts work on that basis.
  - Post-demo Q&A with engineering to reconstruct what was built.
  - Manually probing edge cases the demo skipped.
- **`expert_best_practice`:** Document 6's evidence-based acceptance would demonstrate AC
  satisfaction with product-appropriate evidence rather than a happy-path demo, so edge cases
  and implementation nuances are visible, not hidden.
- **`practitioner_pain`:** The demo is a happy-path performance; it hides edge cases and forces
  the PM to depend on engineering to explain the real behavior.
- **`underserved_by_existing_tools`:** `Underserved` — demo/screenshare tools show the happy
  path; nothing surfaces the edge cases and implementation nuances a demo omits.
- **`source_documents`:** ["2", "7"]

## FM-07 · QA–Product–Engineering Misalignment

- **`failure_mode_id`:** `FM-07` · **`slug`:** `fm-qa-product-engineering-misalignment`
- **`workflow_stage`:** `Acceptance Criteria / Definition of Done` · **`concept_nodes`:** `CN-02`, `CN-08`
- **`observable_symptoms`:**
  - QA verifies functional correctness, Product verifies business intent, Engineering
    implements — and the three perspectives are not aligned.
  - "Tests verify functionality but lose business context." (Document 2)
  - QA reports that don't match the business intent the PM had in mind.
- **`evidence_signals`:**
  - QA sign-off that doesn't satisfy the PM's acceptance, or vice versa.
  - Test cases focused on functional correctness rather than customer outcomes.
  - Long reconciliation discussions between QA, Product, and Engineering at acceptance.
- **`current_workarounds`:**
  - Manual reconciliation of QA results against business intent.
  - Extra alignment meetings to reconcile the three views.
  - PM re-checking QA-passed work against original intent by hand.
- **`expert_best_practice`:** Document 6/7 and the Three Amigos practice (CN-02) call for
  Product, Engineering, and QA to build shared understanding *before* build and verify against
  the same agreed intent — aligning the three perspectives rather than running them separately.
- **`practitioner_pain`:** The three roles verify different things against different mental
  models, so functionally "passing" work can still miss business intent.
- **`underserved_by_existing_tools`:** `Underserved` — test tools verify functionality and
  Jira tracks status, but no tool aligns QA's functional check with Product's intent check.
- **`source_documents`:** ["2", "7"]

---

## Stage summary

All seven entries share one root cause in Document 7's pivotal observation: practitioners
describe vivid operational symptoms (ambiguous AC, subjective approval, missing evidence, late
validation, unclear ownership, happy-path demos, three-role misalignment) but **nobody frames
the larger problem as a cohesive validation capability.** That is precisely the framing gap
that makes these failure modes a credible GTM basis rather than a generic pain list — analysed
across the whole library in [§5](05-framework-5-separation-and-underserved-gaps.md).

---

*Previous: [Section 0 — Schema & Organization](00-schema-and-organization.md) · Next: [Section 2 — Implementation / Continuous Collaboration failure modes](02-implementation-continuous-collaboration-failure-modes.md)*
