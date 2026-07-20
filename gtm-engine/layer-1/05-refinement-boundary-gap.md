# Layer 1 · Section 5 — The Refinement Boundary Gap

> **Role in the knowledge graph:** This section names the **frontier** of the whole research
> effort — the under-documented operational layer where published frameworks stop but
> practitioner pain concentrates. It is the primary substrate that downstream layers point
> at: the Failure Mode Library (DIV-33), Capability Graph (DIV-34), and Buying Trigger Graph
> (DIV-35) all do their most valuable work *inside this gap*.
>
> **Source:** Documents 8–9.
> **Owning subtask:** DIV-53.
> **Out of scope here:** cataloguing the *specific* failure modes inside the gap (DIV-33),
> mapping gap capabilities to Specsight (DIV-34), deriving buying triggers from the gap
> (DIV-35), and the two-loop / CPA operating model itself (Section 3). This section defines
> the gap and its significance; the sibling parents populate it.

---

## 1. The gap itself (Document 9)

Document 9 observes a consistent pattern in what practitioners and thought leaders publish:

- **Nearly everyone writes about the *front* of the lifecycle:**
  `Vision → Backlog Refinement → Ready for Development`
- **Very few describe the *middle*:**
  `Ready for Development → Implementation → Product Validation → Sprint Review`

The gap is **not around preparing work** — preparation (refinement, readiness) is
well-covered. The gap is around **maintaining product intent during execution and validating
it before stakeholder review.**

```text
   WELL-DOCUMENTED (front of lifecycle)          UNDER-DOCUMENTED (the refinement boundary gap)
   ══════════════════════════════════            ═══════════════════════════════════════════════

   Vision                                         Ready for Development
     │                                                    │
     ▼                                                    ▼
   Backlog Refinement                             Implementation
     │                                                    │
     ▼                                                    ▼
   Ready for Development  ────── BOUNDARY ──────►  Product Validation
                                                          │
                                                          ▼
                                                   Sprint Review
```

Positioned against the two product loops from
[Section 3](03-two-product-loops-and-continuous-alignment.md):

```text
   DISCOVERY / REFINEMENT LOOP          │  ◄── THE GAP ──►  │      VERIFICATION / ACCEPTANCE LOOP
   "What should we build?"              │                  │      "Did we build what we agreed?"
   (well-documented)                    │  (under-documented│      (partly documented at Sprint Review)
                                        │   operational layer│
   Backlog Refinement ─► Ready for Dev ─┼─► Implementation ─► Product Validation ─┼─► Sprint Review
                                        │   maintain intent   verify vs intent    │
                                        └────────────────────────────────────────┘
                                            most published frameworks go quiet here
```

Most published frameworks stop at `Discovery → PRD → Backlog → Sprint Review → Release`; the
operational layer *connecting* these stages remains under-documented. This became the next
research direction identified in Document 9.

---

## 2. Why this gap matters

- **It is where published frameworks stop.** Guidance is abundant on preparing work and on
  the ceremonies that bookend a sprint, but sparse on the execution middle.
- **It is where practitioner pain concentrates.** Document 9's practitioner corpus surfaces
  recurring breakdowns located squarely in this middle stretch:
  - implementation drift
  - skipped refinement
  - unclear acceptance criteria
  - blocked engineering
  - velocity loss
  - developers interpreting stories differently
- **It is where existing tools are most likely underserved.** Because the layer is
  under-documented, it is also under-tooled — the most probable location of unmet need.

> The pain signals above are named here only to characterize *where* the gap concentrates.
> Cataloguing them as structured failure modes (symptoms, evidence, workarounds) is the job
> of the Failure Mode Library, **sibling parent DIV-33** — not this section.

---

## 3. What the gap contains

Based on the research, the following operational activities fall within the gap — the work
that happens between "ready for development" and "sprint review":

1. **Maintaining product intent during implementation** — keeping the build aligned with the
   agreed intent as work proceeds.
2. **Validating implementation against original intent before stakeholder review** —
   verifying the increment matches what was agreed *before* it reaches Sprint Review (CN-09).
3. **Clarification vs requirement-evolution decisions during implementation** — applying the
   operational boundary from [Section 3](03-two-product-loops-and-continuous-alignment.md#2-clarification-vs-requirement-evolution-document-8):
   is a mid-flight question a clarification (no AC change) or a new requirement (new backlog
   work)?
4. **Continuous collaboration between "ready for development" and "sprint review"** — the
   ongoing PO/Engineering/QA alignment (CN-07) that occurs across execution, not just at
   handoffs.
5. **Evidence-gathering and verification before formal acceptance** — assembling the evidence
   (per the [evidence-type catalogue](02-pm-lifecycle-and-operating-concepts.md#evidence-type-catalogue-document-6))
   that Story Acceptance (CN-08) and Product Owner Acceptance (CN-06) will depend on.

These are precisely the activities that Continuous Product Alignment (Section 3) describes as
observable manifestations — which is why the gap is the natural home of CPA in practice.

---

## 4. Research implications — how the gap connects downstream

This gap is the connective tissue between Layer 1 and the rest of the GTM engine:

- **Failure Mode Library (DIV-33):** the gap is the focus area for failure-mode
  cataloguing — the breakdowns in §2 are the raw material.
- **Buying Trigger Graph (DIV-35):** the gap is the **most likely zone for buying triggers to
  fire**, because buying intent originates in *workflow breakdown during execution* (per
  Document 2's Workflow Event → Buying Trigger framework), and execution is exactly where
  this gap lives.
- **Capability Graph (DIV-34):** the gap is where **Specsight's continuous-alignment
  capability is most differentiated** — an under-tooled layer is where a capability that
  maintains intent through execution has the clearest fit.
- **Next research frontier:** Document 9 explicitly names this layer as the next direction
  for research — enriching the workflow map and buying-trigger model precisely here.

```text
        THE REFINEMENT BOUNDARY GAP
        (under-documented, under-tooled, pain concentrates here)
                        │
        ┌───────────────┼───────────────┬──────────────────────┐
        ▼               ▼               ▼                      ▼
  Failure Mode      Buying Trigger    Capability Graph      Next research
  Library (DIV-33)  Graph (DIV-35)    (DIV-34)              frontier (Doc 9)
  cataloguing       triggers fire     Specsight most
  focus area        here most         differentiated here
```

---

*Previous: [Section 4 — Company-Specific Implementations](04-company-implementations-matrix.md) · Back to [Layer 1 hub](../layer-1-industrial-knowledge-graph.md)*
