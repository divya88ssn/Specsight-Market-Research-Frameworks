# Layer 2 · Section 4 — Cross-Stage Drift Taxonomy & Context Reconstruction Tax

> **Role in the library:** Catalogues the eight failure modes from Document 2 (the keystone
> persona/JTBD/ICP document) that span the *entire* delivery lifecycle rather than a single
> stage: a **four-part drift taxonomy** at each lifecycle transition, and a **four-part
> Context Reconstruction Tax** paid at each workflow stage.
>
> **Owning subtask:** DIV-58.
> **Workflow stages:** `Requirements / Backlog Refinement`, `Sprint Review`,
> `UAT / Release Readiness`, `Production Review` (the four lifecycle stages Document 2 spans).
> **Source document:** 2.
> **Ids:** FM-18 … FM-25.
> **Schema:** every entry conforms to [§0](00-schema-and-organization.md).

---

## The stage in one line

Document 2 models the delivery lifecycle as four stages — **Requirements → Sprint Review →
UAT/Release Readiness → Production** — and identifies two systematic, cross-stage failure
patterns. First, a **drift taxonomy**: at each transition, information is lost as work moves
to the next stage (Implementation, Validation, Reality, Learning drift). Second, a **Context
Reconstruction Tax**: at each stage the PM pays a recurring cost to rebuild context because
"product intent, implementation, validation, and customer reality live in disconnected
systems." Together they are the lifecycle-wide backdrop to the stage-specific failure modes in
§1–§3.

> **Cross-reference note (avoiding double-counting):** FM-18 Implementation Drift is the
> *cross-stage transition* view (Requirements → Sprint Review) of the same phenomenon that
> FM-08 catalogues at the Implementation / Continuous Collaboration stage. Layer 3 should treat
> FM-08 and FM-18 as one underlying capability gap viewed at two altitudes (stage-level vs
> lifecycle-transition-level), not two separate gaps.

---

## Part A — Cross-Stage Drift Taxonomy

Four drift types, one per lifecycle transition. Each describes information lost as work crosses
a stage boundary.

### FM-18 · Implementation Drift (Requirements → Sprint Review)

- **`failure_mode_id`:** `FM-18` · **`slug`:** `fm-implementation-drift-cross-stage`
- **`workflow_stage`:** `Requirements / Backlog Refinement` · **`concept_nodes`:** `CN-01`, `CN-07`, `CN-09`
- **`observable_symptoms`:**
  - "Requirements are translated into code through many implementation decisions that are
    rarely reflected back into product artifacts."
  - "Implementation Drift — subtle deviations, hidden edge cases, undocumented assumptions,
    technical compromises."
- **`evidence_signals`:**
  - "Engineering repeatedly explaining behavior."
  - Product artifacts stale relative to shipped behavior.
  - PM reconstructing what was built from demos rather than from artifacts.
- **`current_workarounds`:**
  - "Engineers interpret requirements and implement them. PM validates primarily through
    demos." (Document 2, current process)
  - Post-hoc artifact updates when time allows.
- **`expert_best_practice`:** Document 2 frames this drift as a symptom of the **Context
  Reconstruction Tax** — a recurring cost paid every sprint because product intent and
  implementation live in disconnected systems; the ideal reflects implementation decisions
  back into product intent continuously.
- **`practitioner_pain`:** Implementation decisions accumulate without being reflected back
  into product artifacts, so the record of intent and the reality of the build diverge.
- **`underserved_by_existing_tools`:** `Underserved` — "PMs becoming translators instead of
  strategists" is an observable signal no existing tool addresses holistically.
- **`source_documents`:** ["2"] · **related:** FM-08

### FM-19 · Validation Drift (Sprint Review → UAT)

- **`failure_mode_id`:** `FM-19` · **`slug`:** `fm-validation-drift`
- **`workflow_stage`:** `Sprint Review` · **`concept_nodes`:** `CN-08`, `CN-09`
- **`observable_symptoms`:**
  - "Test cases often focus on functional correctness instead of end-to-end customer
    outcomes."
  - "Validation Drift — QA verifies what was implemented, but may miss original business
    intent or customer workflows."
- **`evidence_signals`:**
  - QA sign-off that doesn't reflect customer workflows.
  - Test suites green while customer intent is unmet.
  - "Engineering repeatedly explaining behavior" to reconcile QA results with intent.
- **`current_workarounds`:**
  - "QA creates test cases from stories and acceptance criteria." (Document 2, current
    process)
  - Manual reconciliation of QA results against business intent.
- **`expert_best_practice`:** Document 2 frames validation that tracks end-to-end customer
  outcomes (not just functional correctness) as the ideal — part of closing the Context
  Reconstruction Tax so validation retains business intent.
- **`practitioner_pain`:** QA verifies what was implemented but loses original business intent
  and customer workflows, so "passing" validation can still miss the point.
- **`underserved_by_existing_tools`:** `Underserved` — test tools verify functionality; no tool
  connects validation back to original business intent and customer workflows.
- **`source_documents`:** ["2"]

### FM-20 · Reality Drift (UAT → Production)

- **`failure_mode_id`:** `FM-20` · **`slug`:** `fm-reality-drift`
- **`workflow_stage`:** `UAT / Release Readiness` · **`concept_nodes`:** `CN-05`, `CN-08`
- **`observable_symptoms`:**
  - "UAT validates expected behavior, not actual customer behavior under real-world
    conditions."
  - "Reality Drift — customers behave differently than expected; production environments
    expose scenarios not covered in testing."
- **`evidence_signals`:**
  - Production incidents from scenarios not covered in testing.
  - Customer behavior diverging from UAT assumptions.
  - "Support asks Product what changed" after release.
- **`current_workarounds`:**
  - "Release is approved based on test evidence. Product monitors analytics and customer
    feedback after launch." (Document 2, current process)
  - Post-launch firefighting on uncovered scenarios.
- **`expert_best_practice`:** Document 2's framing implies validating against *actual* customer
  behavior under real-world conditions, not just expected behavior — closing the gap between
  UAT and production reality.
- **`practitioner_pain`:** UAT validates expected behavior, but real customers and production
  conditions expose scenarios testing never covered.
- **`underserved_by_existing_tools`:** `Underserved` — analytics platforms observe production
  behavior after the fact but don't connect it back to release readiness decisions.
- **`source_documents`:** ["2"]

### FM-21 · Learning Drift (Production → Requirements)

- **`failure_mode_id`:** `FM-21` · **`slug`:** `fm-learning-drift`
- **`workflow_stage`:** `Production Review` · **`concept_nodes`:** `CN-01`
- **`observable_symptoms`:**
  - "There is no persistent link between production observations and the original product
    intent."
  - "Learning Drift — customer learnings are manually synthesized into the next set of
    requirements. Valuable context is scattered across multiple systems."
- **`evidence_signals`:**
  - "Product knowledge is tribal."
  - "Slack becomes the source of truth."
  - Production learnings re-synthesized by hand each cycle, inconsistently.
- **`current_workarounds`:**
  - "PM reviews dashboards, support tickets, incidents, interviews, analytics." (Document 2,
    current process)
  - Manual synthesis of scattered learnings into the next requirements.
- **`expert_best_practice`:** Document 2 frames a persistent link between production
  observations and original product intent as the ideal — closing the loop so learning feeds
  requirements without manual re-synthesis (the Commercial Learning Loop from Document 1).
- **`practitioner_pain`:** No persistent link exists between production observations and
  original intent, so learning is manually re-synthesized from scattered systems each cycle.
- **`underserved_by_existing_tools`:** `Underserved` — customer feedback, analytics, support
  tickets, and engineering data "live in separate tools"; nothing links production learning
  back to product intent.
- **`source_documents`:** ["2"]

---

## Part B — Context Reconstruction Tax

Four entries, one per workflow stage. Each describes the recurring cost the PM pays to rebuild
context at that stage.

### FM-22 · Context Reconstruction at Requirements

- **`failure_mode_id`:** `FM-22` · **`slug`:** `fm-context-reconstruction-requirements`
- **`workflow_stage`:** `Requirements / Backlog Refinement` · **`concept_nodes`:** `CN-01`, `CN-04`
- **`observable_symptoms`:**
  - "Rewriting requirements, answering the same questions repeatedly, facilitating alignment
    meetings. Translating customer intent into language every stakeholder understands."
  - "Ambiguous or incomplete requirements, different stakeholders leave with different
    interpretations, engineering feasibility and customer intent are reconciled manually."
- **`evidence_signals`:**
  - "PMs becoming translators instead of strategists."
  - Same requirement questions asked repeatedly.
  - Alignment meetings proliferating around requirements.
- **`current_workarounds`:**
  - PM rewrites requirements and manually reconciles feasibility with intent.
  - Repeated alignment meetings to translate customer intent for stakeholders.
- **`expert_best_practice`:** Document 2 names the pattern the **Context Reconstruction Tax** —
  a recurring cost paid every sprint because intent, implementation, validation, and customer
  reality live in disconnected systems; the ideal removes the re-translation tax.
- **`practitioner_pain`:** The PM repeatedly rebuilds and re-translates requirement context by
  hand, becoming a translator rather than a strategist.
- **`underserved_by_existing_tools`:** `Underserved` — this is an observable signal ("PMs
  becoming translators") that no existing tool addresses holistically.
- **`source_documents`:** ["2"]

### FM-23 · Context Reconstruction at Sprint Review

- **`failure_mode_id`:** `FM-23` · **`slug`:** `fm-context-reconstruction-sprint-review`
- **`workflow_stage`:** `Sprint Review` · **`concept_nodes`:** `CN-09`, `CN-06`
- **`observable_symptoms`:**
  - "Asking 'What actually changed?', comparing implementation to requirements manually,
    documenting follow-ups. Reconstructing implementation from demos, Jira, and engineering
    explanations."
  - "PM depends on engineering to explain what was actually built, difficult to compare
    implementation against original intent, demos show happy paths but hide edge cases and
    implementation nuances."
- **`evidence_signals`:**
  - "Engineering repeatedly explaining behavior."
  - "Release meetings getting longer."
  - PM manually diffing implementation against requirements.
- **`current_workarounds`:**
  - "Watches demos and accepts work." (Document 2, current process)
  - Reconstructing what changed from demos, Jira, and engineering explanations.
- **`expert_best_practice`:** Document 2's Context Reconstruction Tax framing — the ideal makes
  "what actually changed" directly comparable to original intent without depending on
  engineering to narrate it.
- **`practitioner_pain`:** At every review the PM reconstructs what was built from demos, Jira,
  and engineering explanations, unable to compare implementation to intent directly.
- **`underserved_by_existing_tools`:** `Underserved` — "Release meetings getting longer" and
  "Engineering repeatedly explaining behavior" are observable signals no tool addresses.
- **`source_documents`:** ["2"]

### FM-24 · Context Reconstruction at UAT / Release Readiness

- **`failure_mode_id`:** `FM-24` · **`slug`:** `fm-context-reconstruction-uat`
- **`workflow_stage`:** `UAT / Release Readiness` · **`concept_nodes`:** `CN-05`, `CN-08`
- **`observable_symptoms`:**
  - "Chasing test results, validating customer journeys, coordinating Go/No-Go meetings.
    Reassembling evidence from QA, Engineering, and Operations to make a release decision."
  - "Business acceptance requires combining information from many systems, hard to know whether
    all customer workflows were validated, Go/No-Go decisions rely heavily on meetings and
    manual communication."
- **`evidence_signals`:**
  - "Release meetings getting longer."
  - Go/No-Go decisions driven by meetings and manual communication.
  - Evidence chased across QA, Engineering, and Operations.
- **`current_workarounds`:**
  - "Reviews QA and release status." (Document 2, current process)
  - Reassembling evidence from many systems to make the release call.
- **`expert_best_practice`:** Document 2's Context Reconstruction Tax framing — the ideal
  assembles release evidence and customer-workflow coverage without chasing it across systems.
- **`practitioner_pain`:** Every release requires reassembling scattered evidence to make a
  Go/No-Go call, with no way to know all customer workflows were validated.
- **`underserved_by_existing_tools`:** `Underserved` — business acceptance "requires combining
  information from many systems"; no tool assembles the release-readiness picture.
- **`source_documents`:** ["2"]

### FM-25 · Context Reconstruction at Production

- **`failure_mode_id`:** `FM-25` · **`slug`:** `fm-context-reconstruction-production`
- **`workflow_stage`:** `Production Review` · **`concept_nodes`:** `CN-01`
- **`observable_symptoms`:**
  - "Triaging issues, asking Engineering for explanations, correlating releases with customer
    behavior, reprioritizing backlog. Rebuilding customer context across analytics, support
    tickets, incidents, and releases."
  - "Difficult to connect customer issues to specific implementation changes, customer
    feedback/analytics/support tickets/engineering data live in separate tools, root cause
    investigations repeatedly rebuild context from scratch."
- **`evidence_signals`:**
  - "Support asks Product what changed."
  - "Product knowledge is tribal."
  - Root-cause investigations rebuilding context from scratch each time.
- **`current_workarounds`:**
  - "Looks at dashboards and support tickets." (Document 2, current process)
  - Manually correlating releases with customer behavior across separate tools.
- **`expert_best_practice`:** Document 2's Context Reconstruction Tax framing — the ideal
  connects customer issues to specific implementation changes so root-cause work doesn't
  rebuild context from scratch.
- **`practitioner_pain`:** Customer, analytics, support, and engineering data live in separate
  tools, so every production investigation rebuilds context from scratch.
- **`underserved_by_existing_tools`:** `Underserved` — data "live in separate tools"; no tool
  connects customer issues to the implementation changes that caused them.
- **`source_documents`:** ["2"]

---

## Stage summary

Document 2 frames these eight together as the **Context Reconstruction Tax**: a recurring cost
paid every sprint because product intent, implementation, validation, and customer reality live
in disconnected systems. The four drift types describe *what is lost at each transition*; the
four tax entries describe *what the PM pays to rebuild it at each stage*. Crucially, the
research surfaces these as **observable signals** — "PMs becoming translators instead of
strategists," "Engineering repeatedly explaining behavior," "Release meetings getting longer,"
"Support asks Product what changed," "Product knowledge is tribal," "Slack becomes the source
of truth" — that no existing tool addresses holistically. That observability is what makes them
strong GTM material; the consolidated underserved assessment is in
[§5](05-framework-5-separation-and-underserved-gaps.md).

---

*Previous: [Section 3 — Discovery/Refinement & Verification/Acceptance loop failure modes](03-discovery-refinement-verification-failure-modes.md) · Next: [Section 5 — Framework-5 separation & underserved-by-tools gaps](05-framework-5-separation-and-underserved-gaps.md)*
