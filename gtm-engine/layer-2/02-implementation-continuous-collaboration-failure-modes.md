# Layer 2 · Section 2 — Implementation / Continuous Collaboration Failure Modes

> **Role in the library:** Catalogues the five recurring failure modes discovered in the
> Implementation Validation / Product Validation research — the breakdowns that occur *after*
> a story is "ready for development" and *during* execution, inside the refinement boundary
> gap where practitioner pain concentrates.
>
> **Owning subtask:** DIV-52.
> **Workflow stage:** `Implementation / Continuous Collaboration` (Layer 1 CN-07; touching
> CN-01 and CN-03).
> **Source documents:** 3–5, with Documents 2 and 9 contributing the drift and
> shared-understanding framings.
> **Ids:** FM-08 … FM-12.
> **Schema:** every entry conforms to [§0](00-schema-and-organization.md).

---

## The stage in one line

This stage lives squarely inside the **refinement boundary gap** (Layer 1
[Section 5](../layer-1/05-refinement-boundary-gap.md)): the under-documented stretch between
"ready for development" and "sprint review" where product intent must be maintained during
execution. The research's key reframe (Document 5, Part 3) runs throughout: the industry is
shifting from **"prepare the backlog"** to **"continuously maintain shared understanding"** —
Continuous Collaboration (CN-07). When that continuous alignment lapses, the five failure
modes below appear.

---

## FM-08 · Implementation Drift

- **`failure_mode_id`:** `FM-08` · **`slug`:** `fm-implementation-drift`
- **`workflow_stage`:** `Implementation / Continuous Collaboration` · **`concept_nodes`:** `CN-07`, `CN-03`
- **`observable_symptoms`:**
  - "Teams make tactical implementation decisions that drift away from the product vision
    because refinement stops after Sprint Planning." (Document 9)
  - "Requirements are translated into code through many implementation decisions that are
    rarely reflected back into product artifacts." (Document 2)
  - "Subtle deviations, hidden edge cases, undocumented assumptions, technical compromises."
    (Document 2)
- **`evidence_signals`:**
  - Shipped behavior that no longer matches the story or PRD.
  - Product artifacts that are stale relative to what was actually built.
  - Engineering decisions made mid-sprint with no path back into product docs.
- **`current_workarounds`:**
  - PM validates primarily through demos after the fact.
  - Retroactively updating artifacts (when there is time).
  - Asking engineering to explain the decisions that were made.
- **`expert_best_practice`:** Document 3's practitioners (Mike Cohn, Joel Bancroft-Connors,
  Maarten Dalmijn) reframe refinement as *ongoing shared understanding* rather than a
  pre-sprint event — maintaining product intent during execution (CN-07) so tactical decisions
  stay tethered to vision.
- **`practitioner_pain`:** Refinement stops after Sprint Planning, so implementation decisions
  accumulate unchecked and the build silently diverges from intent.
- **`underserved_by_existing_tools`:** `Underserved` — no tool reflects mid-sprint
  implementation decisions back into product artifacts; the drift is invisible until a demo.
  *(Cross-stage transition view: FM-18.)*
- **`source_documents`:** ["2", "3", "9"]

## FM-09 · Skipped Refinement

- **`failure_mode_id`:** `FM-09` · **`slug`:** `fm-skipped-refinement`
- **`workflow_stage`:** `Implementation / Continuous Collaboration` · **`concept_nodes`:** `CN-01`, `CN-07`
- **`observable_symptoms`:**
  - Backlog refinement is treated as a one-time pre-sprint activity rather than an ongoing
    mechanism.
  - Shared understanding decays during implementation once refinement stops.
  - "We refined it at planning" is treated as sufficient for the whole sprint.
- **`evidence_signals`:**
  - No refinement touchpoints between Sprint Planning and Sprint Review.
  - Questions piling up mid-sprint that refinement would have caught.
  - Alignment visibly decaying as the sprint progresses.
- **`current_workarounds`:**
  - Emergency clarification meetings when understanding breaks down.
  - Engineers proceeding on their own interpretation to avoid waiting.
  - More upfront documentation to compensate for no ongoing refinement.
- **`expert_best_practice`:** Document 5 (Part 3) names the shift from "prepare the backlog"
  to "continuously maintain shared understanding" — refinement as a continuous mechanism
  (CN-01 inside CN-07), which the corpus practitioners (Cohn, Dalmijn, Bancroft-Connors)
  advocate.
- **`practitioner_pain`:** Refinement is treated as one-and-done at planning, so shared
  understanding decays with no mechanism to renew it during the sprint.
- **`underserved_by_existing_tools`:** `Underserved` — tools schedule refinement as a ceremony
  but do not maintain shared understanding continuously through execution.
- **`source_documents`:** ["3", "5"]

## FM-10 · Blocked Engineering

- **`failure_mode_id`:** `FM-10` · **`slug`:** `fm-blocked-engineering`
- **`workflow_stage`:** `Implementation / Continuous Collaboration` · **`concept_nodes`:** `CN-03`, `CN-07`
- **`observable_symptoms`:**
  - Engineering is blocked because stories are not sufficiently refined or clarified before
    implementation begins.
  - Without clear AC and shared understanding, engineers wait for clarification or make their
    own interpretations.
  - "We can't start this — it isn't clear enough yet."
- **`evidence_signals`:**
  - Stories stalled in progress awaiting clarification.
  - Engineers repeatedly pinging the PM to unblock work.
  - Idle time or context-switching while waiting for answers.
- **`current_workarounds`:**
  - Engineers make their own interpretation and proceed (feeding FM-08 drift).
  - Ad hoc clarification pings and meetings to unblock.
  - Pulling in other work while blocked.
- **`expert_best_practice`:** Document 3's Story Clarification (CN-03) and Three Amigos build
  enough shared understanding *before* implementation that engineering isn't blocked;
  continuous collaboration (CN-07) keeps clarifications flowing without a stall.
- **`practitioner_pain`:** Insufficiently refined stories block engineering, forcing a choice
  between waiting (velocity loss) and guessing (drift).
- **`underserved_by_existing_tools`:** `Partially served` — Jira flags blocked status but does
  not resolve the clarification gap that caused the block.
- **`source_documents`:** ["3", "5"]

## FM-11 · Velocity Loss

- **`failure_mode_id`:** `FM-11` · **`slug`:** `fm-velocity-loss`
- **`workflow_stage`:** `Implementation / Continuous Collaboration` · **`concept_nodes`:** `CN-07`
- **`observable_symptoms`:**
  - Sprint velocity drops because of rework, clarification meetings, and stories that fail
    acceptance due to misaligned expectations.
  - PMs spend significant time "rewriting requirements, answering the same questions
    repeatedly, facilitating alignment meetings." (Document 2)
  - The team is busy but throughput falls.
- **`evidence_signals`:**
  - Declining sprint velocity trend.
  - Rising count of rework tickets and reopened stories.
  - Growing calendar load of clarification and alignment meetings.
- **`current_workarounds`:**
  - Adding buffer to estimates to absorb the rework.
  - More meetings to pre-empt misalignment (which themselves cost velocity).
  - PM absorbing the requirement-rewriting and question-answering load.
- **`expert_best_practice`:** The corpus practitioners frame continuous shared understanding
  (CN-07) as the way to avoid rework-driven velocity loss — align continuously rather than
  paying for misalignment in rework and meetings.
- **`practitioner_pain`:** Velocity is eroded by rework, repeated clarification, and failed
  acceptance — the downstream cost of misalignment during execution.
- **`underserved_by_existing_tools`:** `Partially served` — velocity charts *measure* the loss
  after the fact but nothing addresses the misalignment causing it.
- **`source_documents`:** ["2", "3"]

## FM-12 · Developers Interpreting Stories Differently

- **`failure_mode_id`:** `FM-12` · **`slug`:** `fm-developers-interpreting-stories-differently`
- **`workflow_stage`:** `Implementation / Continuous Collaboration` · **`concept_nodes`:** `CN-03`, `CN-02`
- **`observable_symptoms`:**
  - Different developers interpret the same story differently, leading to inconsistent
    implementation.
  - "Different stakeholders leave with different interpretations." (Document 2)
  - The same story produces different results depending on who picks it up.
- **`evidence_signals`:**
  - Inconsistent implementations of similar stories across the team.
  - Rework when an implementation doesn't match what the PM (or another dev) expected.
  - Recurring "I thought this meant..." conversations.
- **`current_workarounds`:**
  - More detailed written stories to pin down interpretation.
  - Manual reconciliation when interpretations diverge.
  - Asking engineering to explain the interpretation taken.
- **`expert_best_practice`:** Document 9 frames all these breakdowns as one capability:
  "maintaining shared understanding between product intent and engineering execution." Three
  Amigos (CN-02) and Story Clarification (CN-03) build that shared interpretation before build.
- **`practitioner_pain`:** Without maintained shared understanding, each developer resolves
  ambiguity independently, so the same story yields divergent implementations.
- **`underserved_by_existing_tools`:** `Underserved` — issue trackers store one story text but
  do not confirm that everyone reading it shares the same interpretation.
- **`source_documents`:** ["2", "3", "9"]

---

## Stage summary

Document 9's synthesis ties these five together: "they're all describing the same underlying
capability from different angles: maintaining shared understanding between product intent and
engineering execution. They differ in vocabulary — backlog refinement, collaboration, story
clarification, acceptance criteria — but the operating pattern is remarkably consistent." The
expert direction (Document 5, Part 3) is the shift from "prepare the backlog" to "continuously
maintain shared understanding" — "where the industry's thinking is heading, even though there
isn't yet a universally adopted name for it." This is the refinement boundary gap in
practice; the underserved assessment across these entries is consolidated in
[§5](05-framework-5-separation-and-underserved-gaps.md).

---

*Previous: [Section 1 — Acceptance Criteria / Definition of Done failure modes](01-acceptance-criteria-dod-failure-modes.md) · Next: [Section 3 — Discovery/Refinement & Verification/Acceptance loop failure modes](03-discovery-refinement-verification-failure-modes.md)*
