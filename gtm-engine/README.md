# Specsight GTM Engine

This directory holds the **evidence-driven GTM engine** for Specsight — a repeatable
research-and-learning system that operationalizes the GTM Collaboration Proposal. It is built
as six connected layers, grounded in real industrial operating models and practitioner
vocabulary rather than abstract product-management theory.

> **What this is not:** it is not a Product Management framework and not a Product Operating
> System that Specsight sells. It is a GTM research-and-learning engine. The Product OS
> research is the *substrate* that makes the engine credible.

## The six layers

| Layer | Name | Status | Canonical output |
| --- | --- | --- | --- |
| **1** | **Industrial Knowledge Graph** | ✅ Delivered | [`layer-1-industrial-knowledge-graph.md`](layer-1-industrial-knowledge-graph.md) (+ [`layer-1/`](layer-1/)) |
| **2** | **Failure Mode Library** | ✅ Delivered | [`layer-2-failure-mode-library.md`](layer-2-failure-mode-library.md) (+ [`layer-2/`](layer-2/)) |
| 3 | Capability Graph | Planned (DIV-34) | — |
| 4 | Buying Trigger Graph | Planned (DIV-35) | — |
| 5 | GTM Assets | Planned (sibling brief) | — |
| 6 | Commercial Learning Loop | Planned | — |

Every layer starts from **the customer's operating model**, never from Specsight — because
buying triggers emerge from operating systems, not from demographics, company size, or job
titles.

## Layer 1 — Industrial Knowledge Graph (delivered)

Layer 1 is the canonical substrate every other layer references. Start at the hub:

- **[Layer 1 hub](layer-1-industrial-knowledge-graph.md)** — overview, concept-node index,
  and the cross-reference contract for downstream layers.

Its five sections:

1. [Research Progression Narrative](layer-1/01-research-progression-narrative.md) — the arc across all 9 research documents.
2. [PM Lifecycle Stages & Operating-Model Concepts](layer-1/02-pm-lifecycle-and-operating-concepts.md) — the node-and-edge core (concept nodes CN-01…CN-09).
3. [Two Product Loops & Continuous Product Alignment](layer-1/03-two-product-loops-and-continuous-alignment.md) — the operating model over the nodes.
4. [Company-Specific Implementations](layer-1/04-company-implementations-matrix.md) — the evidence base grounding the concepts.
5. [The Refinement Boundary Gap](layer-1/05-refinement-boundary-gap.md) — the under-documented frontier downstream layers point at.

## Layer 2 — Failure Mode Library (delivered)

Layer 2 catalogues, per workflow stage, the recurring ways PM workflows break down — anchored
to the Layer 1 concept nodes. Start at the hub:

- **[Layer 2 hub](layer-2-failure-mode-library.md)** — the `FM-NN` failure-mode index, the
  entry schema, workflow-stage organization, and the cross-reference contract for Layers 3–4.

Its six sections: [schema](layer-2/00-schema-and-organization.md) ·
[AC / DoD](layer-2/01-acceptance-criteria-dod-failure-modes.md) ·
[Implementation / Continuous Collaboration](layer-2/02-implementation-continuous-collaboration-failure-modes.md) ·
[two loops](layer-2/03-discovery-refinement-verification-failure-modes.md) ·
[cross-stage drift & Context Reconstruction Tax](layer-2/04-cross-stage-drift-and-context-reconstruction-tax.md) ·
[Framework-5 & underserved gaps](layer-2/05-framework-5-separation-and-underserved-gaps.md).

### For contributors to later layers

- Cite Layer 1 by **file path** (paths above are stable) and by **concept node ID**
  (`CN-01`…`CN-09`, defined in Section 2).
- Cite Layer 2 failure modes by **`FM-NN` id** (defined in the Layer 2 hub); Layer 3 attaches a
  capability mapping to each id, Layer 4 references them as buying-trigger sources.
- The **refinement boundary gap** (Layer 1 Section 5, catalogued as failure mode `FM-14`) is the
  primary substrate for the Failure Mode Library, Capability Graph, and Buying Trigger Graph.
