# Layer 2 — Failure Mode Library (Catalogue of Recurring Workflow Breakdowns)

> **This is the canonical Layer 2 document of the Specsight GTM engine.** It catalogues, from
> validated practitioner discussions and workflow analysis, the recurring ways PM workflows
> break down — organized by workflow stage, each with observable symptoms in practitioner
> language, the evidence that appears, the workaround teams use, the expert-vs-practitioner
> separation, and an underserved-by-existing-tools assessment.
>
> **Owning parent task:** DIV-33. **Brief:** Specsight GTM and Market Research Version2.
> **Consumes:** Layer 1 — Industrial Knowledge Graph
> ([`layer-1-industrial-knowledge-graph.md`](layer-1-industrial-knowledge-graph.md)).

---

## What Layer 2 is (and is not)

Layer 2 is the **failure mode library**: for every workflow stage in the Industrial Knowledge
Graph, a catalogued set of recurring failure modes — each anchored to a Layer 1 concept node
(CN-01…CN-09) and captured in the exact language practitioners use. The brief's key insight is
that **practitioners consistently discuss operational symptoms while almost nobody frames the
larger problem as a cohesive validation capability.** Speaking that language of pain — rather
than abstract product theory — is what makes Specsight's outreach, assessment, and positioning
credible.

Layer 2 is **not** a mapping of failure modes to Specsight capabilities (that is Layer 3,
DIV-34) and **not** a derivation of buying triggers (Layer 4, DIV-35). It deliberately stops at
*observing and characterizing* each failure mode. Its only outward links are to Layer 1 concept
nodes and the refinement boundary gap.

---

## Document structure

Layer 2 is composed of six sections, each a self-contained file. Section 0 defines the schema;
§1–§4 catalogue the failure modes by workflow stage; §5 is the cross-cutting synthesis.

| # | Section | File | Owning subtask | What it provides |
| --- | --- | --- | --- | --- |
| 0 | Schema & Workflow-Stage Organization | [`layer-2/00-schema-and-organization.md`](layer-2/00-schema-and-organization.md) | DIV-40 | The `FailureModeEntry` contract every entry conforms to; the `FM-NN` id scheme; the stage set |
| 1 | Acceptance Criteria / Definition of Done | [`layer-2/01-acceptance-criteria-dod-failure-modes.md`](layer-2/01-acceptance-criteria-dod-failure-modes.md) | DIV-48 | FM-01…FM-07 (Docs 6–7, +2) |
| 2 | Implementation / Continuous Collaboration | [`layer-2/02-implementation-continuous-collaboration-failure-modes.md`](layer-2/02-implementation-continuous-collaboration-failure-modes.md) | DIV-52 | FM-08…FM-12 (Docs 3–5, +2, 9) |
| 3 | Discovery/Refinement & Verification/Acceptance loops | [`layer-2/03-discovery-refinement-verification-failure-modes.md`](layer-2/03-discovery-refinement-verification-failure-modes.md) | DIV-56 | FM-13…FM-17 (Docs 8–9) |
| 4 | Cross-stage drift taxonomy & Context Reconstruction Tax | [`layer-2/04-cross-stage-drift-and-context-reconstruction-tax.md`](layer-2/04-cross-stage-drift-and-context-reconstruction-tax.md) | DIV-58 | FM-18…FM-25 (Doc 2) |
| 5 | Framework-5 separation & underserved-by-tools gaps | [`layer-2/05-framework-5-separation-and-underserved-gaps.md`](layer-2/05-framework-5-separation-and-underserved-gaps.md) | DIV-59 | Cross-cutting synthesis + next research frontier |

---

## The `FM-NN` failure-mode id scheme

Every failure mode has a **stable `FM-NN` id** (the primary cross-reference key for Layer 3 and
Layer 4) plus a human-readable slug. Ids are assigned once, in reading order, and never reused.
The full schema is in [Section 0](layer-2/00-schema-and-organization.md).

| FM | Failure mode | Workflow stage | Layer 1 node(s) | Underserved? | §, Docs |
| --- | --- | --- | --- | --- | --- |
| **FM-01** | Ambiguous Acceptance Criteria | Acceptance Criteria / Definition of Done | CN-04, CN-02 | Partially | §1 · 6–7 |
| **FM-02** | Subjective Product Owner Approval | Acceptance Criteria / Definition of Done | CN-06, CN-05 | Underserved | §1 · 6–7 |
| **FM-03** | Missing Evidence | Acceptance Criteria / Definition of Done | CN-04, CN-05 | Underserved | §1 · 6 |
| **FM-04** | Late Validation | Acceptance Criteria / Definition of Done | CN-08, CN-09 | Partially | §1 · 7 |
| **FM-05** | Unclear Ownership | Acceptance Criteria / Definition of Done | CN-06, CN-02 | Partially | §1 · 7 |
| **FM-06** | Demo Difficulties | Acceptance Criteria / Definition of Done | CN-09 | Underserved | §1 · 2, 7 |
| **FM-07** | QA–Product–Engineering Misalignment | Acceptance Criteria / Definition of Done | CN-02, CN-08 | Underserved | §1 · 2, 7 |
| **FM-08** | Implementation Drift | Implementation / Continuous Collaboration | CN-07, CN-03 | Underserved | §2 · 2, 3, 9 |
| **FM-09** | Skipped Refinement | Implementation / Continuous Collaboration | CN-01, CN-07 | Underserved | §2 · 3, 5 |
| **FM-10** | Blocked Engineering | Implementation / Continuous Collaboration | CN-03, CN-07 | Partially | §2 · 3, 5 |
| **FM-11** | Velocity Loss | Implementation / Continuous Collaboration | CN-07 | Partially | §2 · 2, 3 |
| **FM-12** | Developers Interpreting Stories Differently | Implementation / Continuous Collaboration | CN-03, CN-02 | Underserved | §2 · 2, 3, 9 |
| **FM-13** | Clarification vs Scope Creep Confusion | Discovery / Refinement Loop | CN-03 | Underserved | §3 · 8, 9 |
| **FM-14** | Refinement Boundary Gap | Verification / Acceptance Loop | CN-07, CN-08 | Underserved | §3 · 8, 9 |
| **FM-15** | Requirement Evolution Without Shared Understanding | Discovery / Refinement Loop | CN-03, CN-07 | Underserved | §3 · 8, 9 |
| **FM-16** | Two-Loop Conflation | Verification / Acceptance Loop | CN-08, CN-01 | Partially | §3 · 8 |
| **FM-17** | Schools-of-Practice Tension | Discovery / Refinement Loop | CN-01, CN-03 | Underserved | §3 · 9 |
| **FM-18** | Implementation Drift (cross-stage) | Requirements / Backlog Refinement | CN-01, CN-07, CN-09 | Underserved | §4 · 2 |
| **FM-19** | Validation Drift | Sprint Review | CN-08, CN-09 | Underserved | §4 · 2 |
| **FM-20** | Reality Drift | UAT / Release Readiness | CN-05, CN-08 | Underserved | §4 · 2 |
| **FM-21** | Learning Drift | Production Review | CN-01 | Underserved | §4 · 2 |
| **FM-22** | Context Reconstruction @ Requirements | Requirements / Backlog Refinement | CN-01, CN-04 | Underserved | §4 · 2 |
| **FM-23** | Context Reconstruction @ Sprint Review | Sprint Review | CN-09, CN-06 | Underserved | §4 · 2 |
| **FM-24** | Context Reconstruction @ UAT / Release Readiness | UAT / Release Readiness | CN-05, CN-08 | Underserved | §4 · 2 |
| **FM-25** | Context Reconstruction @ Production | Production Review | CN-01 | Underserved | §4 · 2 |

> **Cross-stage note:** FM-08 (Implementation / Continuous Collaboration stage) and FM-18
> (cross-stage transition, Requirements → Sprint Review) describe the same phenomenon —
> implementation drift — at two altitudes. Layer 3 should treat them as one capability gap. See
> [Section 4](layer-2/04-cross-stage-drift-and-context-reconstruction-tax.md).

---

## Organization by workflow stage (Layer 1 cross-reference)

The library is organized by the Layer 1 stages so it cross-references directly with the
Industrial Knowledge Graph:

| Workflow stage | Layer 1 anchor | Failure modes |
| --- | --- | --- |
| Requirements / Backlog Refinement | CN-01 | FM-18, FM-22 |
| Acceptance Criteria / Definition of Done | CN-04, CN-05, CN-06 | FM-01 … FM-07 |
| Implementation / Continuous Collaboration | CN-07 | FM-08 … FM-12 |
| Discovery / Refinement Loop | CN-01/02/03 | FM-13, FM-15, FM-17 |
| Verification / Acceptance Loop | CN-05/06/08 | FM-14, FM-16 |
| Sprint Review | CN-09 | FM-19, FM-23 |
| UAT / Release Readiness | CN-05, CN-08 | FM-20, FM-24 |
| Production Review | (feedback into CN-01) | FM-21, FM-25 |

The **refinement boundary gap** (Layer 1 [Section 5](layer-1/05-refinement-boundary-gap.md)) —
the under-documented execution middle where practitioner pain concentrates — is catalogued
directly as **FM-14** and is the home of the FM-08…FM-17 cluster.

---

## Cross-reference contract for downstream layers

| Downstream layer | Parent | How it builds on Layer 2 |
| --- | --- | --- |
| **Layer 3 — Capability Graph** | DIV-34 | Attaches, per `FM-NN` id, the mapping *failure mode → missing capability → Specsight capability → customer value*. Layer 2 declares no capability field; Layer 3 extends by id. |
| **Layer 4 — Buying Trigger Graph** | DIV-35 | References `FM-NN` ids as the workflow breakdowns that fire buying triggers, anchoring most on the underserved set (esp. FM-14 and FM-22…FM-25). |
| **Architecture — Six-layer engine** | DIV-36 | Documents Layer 2 as the second layer; the Failure Mode Library feeds Layers 3–4. |

> **Scope discipline observed in Layer 2:** this library catalogues failure modes and their
> symptoms/evidence/workarounds, applies Framework-5 separation, and assesses underserved-tool
> gaps. It deliberately does **not** map failure modes to Specsight capabilities (DIV-34) or
> derive buying triggers (DIV-35). Where those are touched, it is only to name a downstream
> connection.

---

## Underserved summary (the GTM opening)

Across the 25 failure modes: **19 Underserved, 6 Partially served, 0 Served.** The underserved
set — anchored on the refinement boundary gap (FM-14) and the Context Reconstruction Tax
(FM-22…FM-25) — is Specsight's strongest opening and the next research frontier. Full analysis:
[Section 5](layer-2/05-framework-5-separation-and-underserved-gaps.md).

---

## Source basis

All content is derived from the nine research documents narrated in the brief
(`.hamster/divya-gunasekarans-team/briefs/specsight-gtm-and-market-research-version2/brief.md`),
partitioned by document range as: Documents 6–7 (§1), Documents 3–5 (§2), Documents 8–9 (§3),
and Document 2 (§4), with Framework 5 (Document 2) applied across all entries in §5. Observable
symptoms preserve the exact practitioner language from the research; where a quote is used it is
attributed to its source document.
