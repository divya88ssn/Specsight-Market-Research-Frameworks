# Layer 1 — Industrial Knowledge Graph (Canonical Substrate)

> **This is the canonical Layer 1 document of the Specsight GTM engine.** It synthesizes all
> nine research documents into a single structured knowledge base of PM workflows, operating
> models, artifacts, ceremonies, roles, decision points, review mechanisms, and
> company-specific implementations. Every downstream layer (Failure Modes, Capabilities,
> Buying Triggers, GTM Assets, Commercial Learning Loop) references the structures defined
> here.
>
> **Owning parent task:** DIV-32. **Brief:** Specsight GTM and Market Research Version2.

---

## What Layer 1 is (and is not)

Layer 1 is the **industrial knowledge base** that makes every subsequent GTM layer credible
and grounded in real practitioner vocabulary rather than abstract theory. Without this
structured substrate, downstream GTM work reverts to generic pain points.

Layer 1 is **not** a Product Management framework and **not** a Product Operating System to
sell. It is a *referenceable substrate* for GTM: a structured understanding of how mature
product organizations actually work, expressed in the terminology practitioners already
recognize. The goal of the whole engine is to operationalize the GTM Collaboration Proposal
into a repeatable, evidence-driven engine — not to become Agile experts.

---

## Document structure

Layer 1 is composed of five sections, each a self-contained file. Read them in order for the
full arc, or jump to a section by its stable path (downstream layers should cite these paths).

| # | Section | File | Owning subtask | What it provides |
| --- | --- | --- | --- | --- |
| 1 | Research Progression Narrative | [`layer-1/01-research-progression-narrative.md`](layer-1/01-research-progression-narrative.md) | DIV-38 | The intellectual arc across all 9 documents; framing for everything else |
| 2 | PM Lifecycle Stages & Operating-Model Concepts | [`layer-1/02-pm-lifecycle-and-operating-concepts.md`](layer-1/02-pm-lifecycle-and-operating-concepts.md) | DIV-42 | The node-and-edge core: 9 structured concept nodes (CN-01…CN-09) + relationship map + evidence catalogue |
| 3 | Two Product Loops & Continuous Product Alignment | [`layer-1/03-two-product-loops-and-continuous-alignment.md`](layer-1/03-two-product-loops-and-continuous-alignment.md) | DIV-46 | The operating model connecting the nodes: two loops, clarification vs evolution, CPA, schools of practice, research corpus |
| 4 | Company-Specific Implementations | [`layer-1/04-company-implementations-matrix.md`](layer-1/04-company-implementations-matrix.md) | DIV-51 | Per-company profiles + cross-reference matrix grounding the concepts in real practice |
| 5 | The Refinement Boundary Gap | [`layer-1/05-refinement-boundary-gap.md`](layer-1/05-refinement-boundary-gap.md) | DIV-53 | The under-documented frontier where practitioner pain concentrates — the substrate downstream layers point at |

---

## The knowledge graph at a glance

```text
     ┌──────────────────────────────────────────────────────────────────────────┐
     │  SECTION 1 — Research Progression Narrative (why the graph exists)          │
     └──────────────────────────────────────────────────────────────────────────┘
                                        │
                                        ▼
     ┌──────────────────────────────────────────────────────────────────────────┐
     │  SECTION 2 — Concept nodes (CN-01…CN-09) + edges                            │
     │  Backlog Refinement · Three Amigos · Story Clarification · Acceptance       │
     │  Criteria · Definition of Done · Product Owner Acceptance · Continuous       │
     │  Collaboration · Story Acceptance · Sprint Review                            │
     └──────────────────────────────────────────────────────────────────────────┘
                                        │
                                        ▼
     ┌──────────────────────────────────────────────────────────────────────────┐
     │  SECTION 3 — Operating model over the nodes                                 │
     │  Discovery/Refinement loop │ boundary │ Verification/Acceptance loop         │
     │  Clarification vs Requirement Evolution · Continuous Product Alignment        │
     │  Traditional Scrum vs AI-native/Product-led · research corpus                │
     └──────────────────────────────────────────────────────────────────────────┘
                       │                                     │
                       ▼                                     ▼
     ┌───────────────────────────────┐     ┌──────────────────────────────────────┐
     │  SECTION 4 — Grounded in real  │     │  SECTION 5 — The refinement boundary   │
     │  companies (evidence base)     │     │  gap (the frontier / downstream focus) │
     └───────────────────────────────┘     └──────────────────────────────────────┘
```

---

## Concept node index (for downstream cross-referencing)

Downstream layers should attach their entries to these stable node IDs (defined in Section 2):

| Node ID | Concept | Question it answers |
| --- | --- | --- |
| **CN-01** | Backlog Refinement | What should we build (and is it ready)? |
| **CN-02** | Three Amigos | Do Product, Engineering, and QA share the same understanding? |
| **CN-03** | Story Clarification | What exactly does this story mean? |
| **CN-04** | Acceptance Criteria | What should the feature do? |
| **CN-05** | Definition of Done | Is the increment ready to ship? |
| **CN-06** | Product Owner Acceptance | Does the PO accept this as satisfying the agreed intent? |
| **CN-07** | Continuous Collaboration | How do we stay aligned throughout delivery? |
| **CN-08** | Story Acceptance | Did we build what we agreed for this story? |
| **CN-09** | Sprint Review | Is the increment ready to show and accept at stakeholder level? |

---

## Cross-reference contract for downstream layers

Sibling parents build on Layer 1 as follows. When they reference Layer 1, they should cite
the file paths above.

| Downstream layer | Parent | How it builds on Layer 1 |
| --- | --- | --- |
| **Layer 2 — Failure Mode Library** | DIV-33 | Catalogues failure modes *per concept node* (CN-01…CN-09) and *within the refinement boundary gap* (Section 5) |
| **Layer 3 — Capability Graph** | DIV-34 | Maps failure modes → missing capability → Specsight capability; anchors on the gap (Section 5) where Specsight is most differentiated |
| **Layer 4 — Buying Trigger Graph** | DIV-35 | Derives buying triggers from workflow events; the gap (Section 5) is the most likely trigger zone |
| **Architecture — Six-layer engine** | DIV-36 | Documents how all six layers connect; Layer 1 is the substrate feeding all of them |

> **Scope discipline observed in Layer 1:** this document catalogues workflows, concepts,
> operating models, companies, and the gap. It deliberately does **not** catalogue individual
> failure modes/symptoms (DIV-33), map capabilities to Specsight (DIV-34), derive buying
> triggers (DIV-35), or generate GTM assets (sibling brief tasks). Where those topics are
> touched, it is only to name a boundary or a downstream connection.

---

## Source basis

All content synthesizes the nine research documents narrated in the brief
(`.hamster/divya-gunasekarans-team/briefs/specsight-gtm-and-market-research-version2/brief.md`):
Documents 1–2 (customer decision framework), 3–7 (industry grounding and Product OS
decomposition), and 8–9 (operating-model synthesis). Company practice is reported only to the
extent the research established it; unestablished intersections are marked "not covered in
research" in Section 4.
