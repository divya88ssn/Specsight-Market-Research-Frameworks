# Layer 2 · Section 3 — Discovery/Refinement & Verification/Acceptance Loop Failure Modes

> **Role in the library:** Catalogues the five recurring failure modes discovered in the
> two-loop / operating-model research. Unlike §1–§2, these are failure modes of the
> *relationships between concepts*, not individual artifacts — how the two product loops and
> the boundary between them break down.
>
> **Owning subtask:** DIV-56.
> **Workflow stages:** `Discovery / Refinement Loop` and `Verification / Acceptance Loop`
> (Layer 1 CN-01/02/03 and CN-05/06/08; the boundary between them per Layer 1
> [Section 3](../layer-1/03-two-product-loops-and-continuous-alignment.md)).
> **Source documents:** 8–9.
> **Ids:** FM-13 … FM-17.
> **Schema:** every entry conforms to [§0](00-schema-and-organization.md).

---

## The stage in one line

Documents 8–9 stepped back from individual artifacts to ask how concepts connect into an
end-to-end Product Operating Model. They separated **two loops** — Discovery/Refinement ("What
should we build?") and Verification/Acceptance ("Did we build what we agreed?") — and named
the boundary between them. The five failure modes below are what happens when the loops, the
boundary, and the shared understanding that spans them break down. The proposed operating
model that addresses them is **Continuous Product Alignment (CPA)**.

---

## FM-13 · Clarification vs Scope Creep Confusion

- **`failure_mode_id`:** `FM-13` · **`slug`:** `fm-clarification-vs-scope-creep-confusion`
- **`workflow_stage`:** `Discovery / Refinement Loop` · **`concept_nodes`:** `CN-03`
- **`observable_symptoms`:**
  - Teams cannot distinguish clarification (improving shared understanding without changing
    AC) from requirement evolution (introducing new business behavior).
  - "Two very different conversations that often get conflated." (Document 8)
  - Mid-flight questions turn into scope changes without anyone deciding they should.
- **`evidence_signals`:**
  - Scope creeping into a sprint under the guise of "just clarifying."
  - Disputes over whether a change is a clarification or new work.
  - AC quietly changing during implementation with no new backlog item.
- **`current_workarounds`:**
  - Ad hoc scope negotiation case by case.
  - Informal story splitting when a "clarification" turns out to be new work.
  - Manual alignment meetings to adjudicate the line.
- **`expert_best_practice`:** Document 8's operational rule: *clarification does not change
  Acceptance Criteria; requirement evolution creates new backlog work.* Document 9 notes that
  practitioners "who explicitly discuss where they draw that line" produce the most valuable
  insight — the boundary is the reference model.
- **`practitioner_pain`:** Teams lack a shared model for the clarification/evolution line, so
  scope creep enters disguised as clarification and AC drift without a decision.
- **`underserved_by_existing_tools`:** `Underserved` — no tool helps a team decide, in the
  moment, whether a change is clarification or new requirement.
- **`source_documents`:** ["8", "9"]

## FM-14 · Refinement Boundary Gap

- **`failure_mode_id`:** `FM-14` · **`slug`:** `fm-refinement-boundary-gap`
- **`workflow_stage`:** `Verification / Acceptance Loop` · **`concept_nodes`:** `CN-07`, `CN-08`
  *(spans the Discovery→Verification boundary; see Layer 1 [Section 5](../layer-1/05-refinement-boundary-gap.md))*
- **`observable_symptoms`:**
  - The operational layer between "Ready for Development" and "Sprint Review" is
    under-documented.
  - "The gap is not around preparing work — it is around maintaining product intent during
    execution and validating it before stakeholder review." (Document 8)
  - "Very little about the day-to-day operating model between 'developer says it's done' and
    'stakeholders see it in Sprint Review.'" (Document 8)
- **`evidence_signals`:**
  - No defined practice for what happens between "ready for dev" and Sprint Review.
  - Intent maintained (or lost) informally, in Slack and hallway conversations.
  - Validation deferred until the stakeholder review because nothing owns the middle.
- **`current_workarounds`:**
  - Informal, ad hoc alignment during execution.
  - Relying on the demo as the first real validation checkpoint.
  - Individual PMs improvising a mid-sprint check.
- **`expert_best_practice`:** Document 8 proposes **Continuous Product Alignment** as the
  operating model that connects the loops — explicitly covering "maintaining product intent
  during execution and validating it before stakeholder review," the layer frameworks skip.
- **`practitioner_pain`:** The execution middle is under-documented and unowned, so intent is
  maintained informally and validated late — this is where practitioner pain concentrates.
- **`underserved_by_existing_tools`:** `Underserved` — "most published frameworks stop at
  Discovery → PRD → Backlog → Sprint Review → Release" and, being under-documented, the layer
  is under-tooled; no tool owns the middle. *(Layer 1's primary downstream substrate.)*
- **`source_documents`:** ["8", "9"]

## FM-15 · Requirement Evolution Without Shared Understanding

- **`failure_mode_id`:** `FM-15` · **`slug`:** `fm-requirement-evolution-without-shared-understanding`
- **`workflow_stage`:** `Discovery / Refinement Loop` · **`concept_nodes`:** `CN-03`, `CN-07`
- **`observable_symptoms`:**
  - When requirements evolve during implementation, shared understanding between product and
    engineering breaks down.
  - Vocabulary differs — "backlog refinement, collaboration, story clarification, acceptance
    criteria" — but the underlying capability is "maintaining shared understanding between
    product intent and engineering execution." (Document 9)
  - Requirements move; not everyone moves with them.
- **`evidence_signals`:**
  - Engineering building to a superseded understanding of the requirement.
  - Product and engineering describing the "same" requirement differently.
  - Rework when an evolved requirement wasn't shared consistently.
- **`current_workarounds`:**
  - Manual re-communication of the evolved requirement.
  - Alignment meetings to re-sync after a requirement changes.
  - Updating docs and hoping everyone re-reads them.
- **`expert_best_practice`:** Document 9's synthesis — the consistent operating pattern across
  vocabularies is *maintaining shared understanding between product intent and engineering
  execution*; CPA (CN-07) is the operating model that keeps understanding shared as
  requirements evolve.
- **`practitioner_pain`:** Requirements evolve faster than shared understanding is maintained,
  so product intent and engineering execution silently diverge.
- **`underserved_by_existing_tools`:** `Underserved` — tools version the requirement text but
  do not maintain or verify shared *understanding* of it as it evolves.
- **`source_documents`:** ["8", "9"]

## FM-16 · Two-Loop Conflation

- **`failure_mode_id`:** `FM-16` · **`slug`:** `fm-two-loop-conflation`
- **`workflow_stage`:** `Verification / Acceptance Loop` · **`concept_nodes`:** `CN-08`, `CN-01`
- **`observable_symptoms`:**
  - Teams conflate the Discovery/Refinement Loop ("What should we build?") with the
    Verification/Acceptance Loop ("Did we build what we agreed?").
  - Document 8 "separates two loops that are often discussed together but solve fundamentally
    different problems."
  - Discovery work happens during verification, or verification is treated as further
    discovery.
- **`evidence_signals`:**
  - New scope discovered *during* acceptance / Sprint Review.
  - Acceptance reviews turning into discovery sessions.
  - Verification decisions muddied by "what should we build?" questions.
- **`current_workarounds`:**
  - Absorbing discovery into acceptance meetings.
  - Re-opening scope at review instead of feeding it back to refinement.
  - Informal separation depending on who is facilitating.
- **`expert_best_practice`:** Document 8's separation of the two loops is the reference model:
  discovery ends when a story is "ready for development"; verification checks completed work
  against what was agreed. Crossing back into discovery during acceptance signals requirement
  evolution, not verification.
- **`practitioner_pain`:** The two loops are run as one, so verification drifts into discovery
  and scope reopens at the acceptance gate.
- **`underserved_by_existing_tools`:** `Partially served` — tools model a single linear
  workflow, not two distinct loops with a boundary; the distinction lives only in team
  discipline.
- **`source_documents`:** ["8"]

## FM-17 · Schools-of-Practice Tension

- **`failure_mode_id`:** `FM-17` · **`slug`:** `fm-schools-of-practice-tension`
- **`workflow_stage`:** `Discovery / Refinement Loop` · **`concept_nodes`:** `CN-01`, `CN-03`
- **`observable_symptoms`:**
  - Traditional Scrum (heavy upfront refinement, frozen AC, limited live discovery, success
    measured by sprint predictability) conflicts with AI-native / Product-led (lightweight
    refinement, continuous validation, controlled requirement evolution, success measured by
    decision speed and customer outcomes).
  - "Two evolving operating philosophies." (Document 9)
  - Teams caught between the two approaches experience friction over how much to refine and
    freeze.
- **`evidence_signals`:**
  - Disagreement over whether AC should be frozen or allowed to evolve.
  - Friction between predictability-oriented and outcome-oriented team members.
  - Process debates that recur every sprint without resolution.
- **`current_workarounds`:**
  - Picking one philosophy informally and living with the tension.
  - Case-by-case negotiation of how much refinement is "enough."
  - Blending both approaches without an explicit model.
- **`expert_best_practice`:** Document 9 does *not* pick a winner — it proposes studying
  "where organizations draw the boundary between clarification and new requirements" (FM-13).
  The reference model is an explicit, chosen boundary rather than an unmanaged blend.
- **`practitioner_pain`:** Teams straddle two operating philosophies without an explicit
  boundary, so refinement weight and AC-freezing are contested every sprint.
- **`underserved_by_existing_tools`:** `Underserved` — no tool helps a team locate itself on
  the Traditional-Scrum ↔ Product-led spectrum or operate a chosen boundary.
- **`source_documents`:** ["9"]

---

## Stage summary

These five failure modes are the connective-tissue breakdowns of the operating model. The
research's proposed answer to all of them is **Continuous Product Alignment** as the operating
model connecting the two loops (Document 8), with the **clarification vs requirement-evolution
boundary** (FM-13) as its central operational rule. FM-14 (the refinement boundary gap) is the
zone Layer 1 Section 5 names as the frontier where practitioner pain and unmet tooling need
concentrate — the highest-value target for the whole GTM engine. The underserved assessment is
consolidated in [§5](05-framework-5-separation-and-underserved-gaps.md).

---

*Previous: [Section 2 — Implementation / Continuous Collaboration failure modes](02-implementation-continuous-collaboration-failure-modes.md) · Next: [Section 4 — Cross-stage drift taxonomy & Context Reconstruction Tax](04-cross-stage-drift-and-context-reconstruction-tax.md)*
