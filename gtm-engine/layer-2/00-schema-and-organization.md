# Layer 2 · Section 0 — Failure Mode Entry Schema & Workflow-Stage Organization

> **Role in the library:** This section defines the **contract** that every failure mode
> entry in the Failure Mode Library conforms to. It is the schema header of the whole
> library — the four cataloguing sections (§1–§4) fill it, and the cross-cutting synthesis
> (§5) validates it. Read this first; everything else is instances of this template.
>
> **Owning subtask:** DIV-40.
> **Source basis:** the field set required by parent DIV-33; workflow-stage names drawn from
> the Industrial Knowledge Graph (Layer 1, DIV-32).
> **Out of scope here:** cataloguing actual failure modes (§1–§4), applying the Framework-5
> synthesis (§5), mapping to Specsight capabilities (DIV-34), or deriving buying triggers
> (DIV-35).

---

## 1. What a failure mode entry is

A **failure mode** is a recurring way a PM workflow breaks down, catalogued in the exact
language practitioners use — not abstracted into a generic pain point. Each entry answers
four practitioner-facing questions the parent task requires for every workflow stage:

- **What commonly breaks?** (the failure mode, named in practitioner language)
- **How do practitioners describe it?** (observable symptoms)
- **What evidence appears?** (evidence signals)
- **What workaround is used?** (current workarounds)

…plus the Framework-5 separation (expert best practice vs practitioner pain) and the
underserved-by-existing-tools assessment that make the library a credible GTM basis rather
than a generic pain list.

---

## 2. The entry schema (the shared contract)

Every entry in §1–§4 MUST populate every field below. This is the `FailureModeEntry`
contract referenced by all cataloguing subtasks (DIV-48, DIV-52, DIV-56, DIV-58).

| Field | Type | Meaning |
| --- | --- | --- |
| **`failure_mode_id`** | string (`FM-NN`) | Stable numeric identifier for cross-referencing from downstream layers. **This is the primary key** Layer 3 (Capability Graph, DIV-34) and Layer 4 (Buying Trigger Graph, DIV-35) reference. Assigned once, never reused. |
| **`slug`** | string (kebab) | Human-readable alias (e.g., `fm-ambiguous-acceptance-criteria`). Convenience for prose references; the `FM-NN` id is authoritative. |
| **`failure_mode_name`** | string | Practitioner-language name — not abstracted (e.g., "Ambiguous Acceptance Criteria", not "requirements quality gap"). |
| **`workflow_stage`** | enum | The Layer 1 stage this failure mode attaches to (see §3 for the allowed set). |
| **`concept_nodes`** | string[] | The Layer 1 concept node id(s) (`CN-01`…`CN-09`) this failure mode occurs at. Anchors the entry to the knowledge graph so it is cross-referenceable. |
| **`observable_symptoms`** | string[] | Bullet list in the *exact language practitioners use*, sourced from the research documents. |
| **`evidence_signals`** | string[] | The artifacts, signals, or discussion patterns that appear when this failure mode occurs. |
| **`current_workarounds`** | string[] | What teams do today to cope. |
| **`expert_best_practice`** | string | What published frameworks, company handbooks, or thought leaders say *should* happen — the theoretical ideal (Framework-5 top half). Must reference a specific source. |
| **`practitioner_pain`** | string | What actually happens in practice — the observable operational reality (Framework-5 bottom half). |
| **`underserved_by_existing_tools`** | enum + rationale | One of `Underserved` / `Partially served` / `Served`, with the existing tools evaluated named and a one-line rationale. |
| **`source_documents`** | string[] | Which research documents (by number, "2"–"9") this entry is derived from. |

> **Framework-5 note:** `expert_best_practice` and `practitioner_pain` are deliberately two
> separate fields so the library never conflates "what frameworks say" with "what
> practitioners experience." The gap between the two is where Specsight's GTM finds real
> friction rather than theoretical gaps. The consolidated separation and the underserved
> matrix are produced in [§5](05-framework-5-separation-and-underserved-gaps.md).

---

## 3. Workflow-stage organization

The library is **organized by workflow stage**, so it cross-references directly with the
Industrial Knowledge Graph (Layer 1). Each stage contains one or more failure mode entries.
`workflow_stage` values MUST be drawn from this set (the stage names established in Layer 1):

| `workflow_stage` value | Layer 1 anchor | Catalogued in |
| --- | --- | --- |
| `Requirements / Backlog Refinement` | CN-01 | §4 (cross-stage) |
| `Acceptance Criteria / Definition of Done` | CN-04, CN-05, CN-06 | §1 |
| `Implementation / Continuous Collaboration` | CN-07 | §2 |
| `Sprint Review` | CN-09 | §4 (cross-stage) |
| `UAT / Release Readiness` | CN-05, CN-08 | §4 (cross-stage) |
| `Production Review` | (post-CN-09 feedback into CN-01) | §4 (cross-stage) |
| `Discovery / Refinement Loop` | CN-01, CN-02, CN-03 | §3 |
| `Verification / Acceptance Loop` | CN-06, CN-08, CN-05 | §3 |

> Stage names are quoted verbatim from Layer 1
> ([`layer-1/02-pm-lifecycle-and-operating-concepts.md`](../layer-1/02-pm-lifecycle-and-operating-concepts.md)
> for the concept nodes and
> [`layer-1/03-two-product-loops-and-continuous-alignment.md`](../layer-1/03-two-product-loops-and-continuous-alignment.md)
> for the two loops). The refinement boundary gap that spans the middle of the lifecycle is
> Layer 1 [Section 5](../layer-1/05-refinement-boundary-gap.md); failure mode FM-14 catalogues
> that gap directly.

---

## 4. `FM-NN` id scheme

Every failure mode carries a stable `FM-NN` id assigned once and never reused, so Layer 3
and Layer 4 can reference a failure mode by id without depending on its wording or position.
Ids are allocated in reading order across the four cataloguing sections:

| Range | Section | Stage(s) | Source docs |
| --- | --- | --- | --- |
| **FM-01 … FM-07** | [§1](01-acceptance-criteria-dod-failure-modes.md) | Acceptance Criteria / Definition of Done | 6–7 (+2) |
| **FM-08 … FM-12** | [§2](02-implementation-continuous-collaboration-failure-modes.md) | Implementation / Continuous Collaboration | 3–5 (+2, 9) |
| **FM-13 … FM-17** | [§3](03-discovery-refinement-verification-failure-modes.md) | Discovery/Refinement & Verification/Acceptance loops | 8–9 |
| **FM-18 … FM-25** | [§4](04-cross-stage-drift-and-context-reconstruction-tax.md) | Cross-stage (drift taxonomy + Context Reconstruction Tax) | 2 |

---

## 5. Example entry (template in use)

The following is a fully-populated entry demonstrating the schema with real research content.
It is FM-01, catalogued in full in [§1](01-acceptance-criteria-dod-failure-modes.md).

### FM-01 · Ambiguous Acceptance Criteria

- **`failure_mode_id`:** `FM-01`
- **`slug`:** `fm-ambiguous-acceptance-criteria`
- **`failure_mode_name`:** Ambiguous Acceptance Criteria
- **`workflow_stage`:** `Acceptance Criteria / Definition of Done`
- **`concept_nodes`:** `CN-04` (Acceptance Criteria), `CN-02` (Three Amigos)
- **`observable_symptoms`:**
  - "Acceptance criteria are written ambiguously, leading to different interpretations."
  - Stories are accepted with different understandings of what "done" means.
  - Developers interpret the same story differently.
- **`evidence_signals`:**
  - Stories reopened after they were marked accepted.
  - Long Sprint Review discussions spent reconciling what was actually meant.
  - Repeated clarification questions on the same story during implementation.
- **`current_workarounds`:**
  - Ad hoc clarification meetings during the sprint.
  - Asking engineering to explain what was actually built.
  - Manual back-and-forth to reconcile interpretations after the fact.
- **`expert_best_practice`:** Document 6's comparison of Microsoft, GitLab, and Atlassian
  shows mature organizations write Acceptance Criteria that answer "What should the feature
  do?" unambiguously and agree them collaboratively during refinement (Three Amigos, CN-02);
  GitLab's DoD checklist and Atlassian's collaborative AC refinement are the reference model.
- **`practitioner_pain`:** In practice AC are written ambiguously and agreed only nominally,
  so the same story is implemented and accepted against different mental models — the pain is
  discovered late, not prevented early.
- **`underserved_by_existing_tools`:** `Partially served` — Jira/Azure DevOps store AC as free
  text but do not test them for ambiguity or confirm shared understanding; per Document 7,
  "almost nobody frames the larger problem as a cohesive validation capability."
- **`source_documents`:** ["6", "7"]

---

## 6. How downstream layers consume the schema

- **Layer 3 — Capability Graph (DIV-34)** will attach a *missing-capability mapping* to each
  `FM-NN` id (failure mode → missing capability → Specsight capability). That mapping is
  **out of scope for Layer 2** — this library deliberately stops at the failure mode,
  its symptoms, evidence, workarounds, and the underserved assessment. Layer 3 extends each
  entry by id; it does not require Layer 2 to pre-declare a capability field.
- **Layer 4 — Buying Trigger Graph (DIV-35)** will reference `FM-NN` ids as the workflow
  breakdowns that fire buying triggers, anchoring most heavily on the refinement boundary
  gap (FM-14) per Layer 1 Section 5.

> **Scope discipline:** every entry stops at *observing and characterizing* the failure mode.
> It does not name a Specsight capability (DIV-34) or a buying trigger (DIV-35). References to
> Layer 1 CN ids and the boundary gap are the only outward links this layer makes.

---

*Next: [Section 1 — Acceptance Criteria / Definition of Done failure modes](01-acceptance-criteria-dod-failure-modes.md) · Back to [Layer 2 hub](../layer-2-failure-mode-library.md)*
