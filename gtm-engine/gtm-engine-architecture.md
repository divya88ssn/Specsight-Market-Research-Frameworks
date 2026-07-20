# GTM Engine Architecture (Capstone — The Connected Six-Layer Operating Model)

> **This is the capstone document of the Specsight GTM engine.** It defines the engine as six
> connected layers with explicit inter-layer interfaces, shows how the Commercial Learning Loop
> closes the engine back into the knowledge graph, maps sibling-brief GTM tasks to the engine
> outputs they consume, traces the engine to the GTM Collaboration Proposal's four workstreams,
> and documents the repeatable methodology for extending the engine over time.
>
> **Owning parent task:** DIV-36. **Brief:** Specsight GTM and Market Research Version2.
> **Consumes:** all four delivered layers — Layer 1
> ([`layer-1-industrial-knowledge-graph.md`](layer-1-industrial-knowledge-graph.md)), Layer 2
> ([`layer-2-failure-mode-library.md`](layer-2-failure-mode-library.md)), Layer 3
> ([`layer-3-capability-graph.md`](layer-3-capability-graph.md)), Layer 4
> ([`layer-4-buying-trigger-graph.md`](layer-4-buying-trigger-graph.md)).

---

## What this document is (and is not)

This capstone is the document that turns the engine from **four delivered research artifacts**
(Layers 1–4) plus **two forward-looking layers** (Layers 5–6) into one *operable system*. It
defines the interfaces between layers so the engine can be operated, maintained, and improved as
a whole rather than as disconnected studies. It is what makes the engine **repeatable**.

It is **not** a re-statement of any layer's content. It does not rebuild the Industrial Knowledge
Graph (DIV-32), catalogue failure modes (DIV-33), map capabilities (DIV-34), derive buying
triggers (DIV-35), or produce any actual GTM asset (outreach copy, assessment questions,
messaging — those are Layer 5 sibling-brief tasks). It **cites and interconnects** the layers'
real, stable primitives (`CN-01…CN-09`, `FM-01…FM-25`, `CAP-01…CAP-07`, `BT-01…BT-05`) and
defines the connective tissue between them.

---

## The engine at a glance

```text
   9 research documents
          │
          ▼
   L1 Industrial Knowledge Graph ──► L2 Failure Mode Library ──► L3 Capability Graph
   (CN-01…CN-09)                     (FM-01…FM-25)                (CAP-01…CAP-07)
                                                                      │
                                                                      ▼
                                                             L4 Buying Trigger Graph
                                                             (BT-01…BT-05)
                                                                      │
                                                                      ▼
                                                             L5 GTM Assets
                                                             (ICP · outreach · PLG · demos ·
                                                              positioning · roadmap input)
                                                                      │
                                                                      ▼
   ┌───────────────────────────────────────────────────────► L6 Commercial Learning Loop
   │                                                          (observe → categorize → validate
   │                                                           → update → propagate)
   └──────────────────────── refinements close back to L1 ──────────────┘
```

Every layer starts from **the customer's operating model**, never from Specsight — because
buying triggers emerge from operating systems, not from demographics, company size, or job
titles.

---

## The four sections

This capstone is composed of four sections, each a self-contained file under
[`architecture/`](architecture/), owned by one subtask of DIV-36. Read them in order for the full
model.

| # | Section | File | Owning subtask | What it provides |
| --- | --- | --- | --- | --- |
| 1 | The Six Engine Layers & Inter-Layer Interfaces | [`architecture/01-six-layer-interfaces.md`](architecture/01-six-layer-interfaces.md) | DIV-37 | The `LayerInterface` contract; each layer's purpose / consumes / produces / owner; the full pipeline table & diagram |
| 2 | The Commercial Learning Loop (Layer 6 closure) | [`architecture/02-commercial-learning-loop.md`](architecture/02-commercial-learning-loop.md) | DIV-41 | Customer-interaction types; per-layer feedback paths; the refinement trigger procedure; the loop-closure diagram |
| 3 | Sibling GTM Consumption Map & Four-Workstream Trace | [`architecture/03-sibling-gtm-mapping-and-workstreams.md`](architecture/03-sibling-gtm-mapping-and-workstreams.md) | DIV-44 | Which engine output each GTM asset consumes + owning task; the four workstreams traced to layers |
| 4 | Repeatable Research Methodology | [`architecture/04-repeatable-research-methodology.md`](architecture/04-repeatable-research-methodology.md) | DIV-47 | Per-layer extension procedures; propagation rules; validation criteria; sources & process |

---

## The `LayerInterface` contract

Every layer in §1 is described with the same shape, so the pipeline reads as a sequence of typed
hand-offs. This is the canonical contract shared across all architecture sections:

```text
LayerInterface {
  layerName:        string   // canonical layer name
  purpose:          string   // what the layer does in the engine
  consumes:         string   // the structured artifact received from the previous layer
  produces:         string   // the structured artifact passed to the next layer
  siblingTaskOwner: string   // the parent task that owns building this layer's content
}
```

`consumes` / `produces` are concrete artifacts with named id schemes, never vague descriptions —
that is what makes each interface stable enough to operate against. Full definitions:
[architecture §1](architecture/01-six-layer-interfaces.md).

---

## The six layers (summary)

| Layer | Name | Consumes | Produces | Owner | Status |
| --- | --- | --- | --- | --- | --- |
| **1** | Industrial Knowledge Graph | 9 research documents | `CN-01…CN-09` + operating model + refinement boundary gap | DIV-32 | ✅ delivered |
| **2** | Failure Mode Library | `CN-01…CN-09` stages | `FM-01…FM-25` (symptoms / evidence / workaround) | DIV-33 | ✅ delivered |
| **3** | Capability Graph | `FM-01…FM-25` | `CAP-01…CAP-07` six-link chains + `CapabilityGapAssessment` | DIV-34 | ✅ delivered |
| **4** | Buying Trigger Graph | `FM-NN` + `CAP-NN` links 1–2 | `BT-01…BT-05` + friction/fit + demographic→workflow table | DIV-35 | ✅ delivered |
| **5** | GTM Assets | `BT-NN` + `CAP-NN` links 5–6 + `FM-NN` language | ICP · outreach · messaging · PLG · demos · positioning · roadmap input · customer interactions | sibling brief | planned |
| **6** | Commercial Learning Loop | customer interactions; `CN`/`FM`/`CAP`/`BT` | refined `CN`·`FM`·`CAP`·`BT` + updated assets → back to L1 | DIV-36 (this doc) | defined here |

---

## Relationship to the original four workstreams

The engine operationalizes the GTM Collaboration Proposal (Document 1). Full trace in
[architecture §3](architecture/03-sibling-gtm-mapping-and-workstreams.md):

| Original workstream | Operationalized by |
| --- | --- |
| Customer Decision Research | Layers 1–4 (`CN` → `FM` → `CAP` → `BT`) |
| Positioning | Layer 5 (messaging / positioning ← `CAP` link 6) |
| GTM Optimization | Layer 5 (ICP / outreach / PLG ← `BT` + demographic→workflow model) |
| Product Strategy | Layer 5 roadmap input ← Layer 3 gap assessment, re-prioritized by Layer 6 |
| *"continuous commercial learning loop"* | Layer 6 — closes every workstream back into Layers 1–4 |

---

## How to extend the engine

The engine is append-only and extended by one repeatable procedure — **identify gap → research →
validate → integrate → propagate** — run per layer, preserving the `CN`/`FM`/`CAP`/`BT` id
schemes. This is the same procedure the Layer 6 loop runs on each customer interaction. Full
methodology, per-layer extension steps, propagation rules, and validation criteria:
[architecture §4](architecture/04-repeatable-research-methodology.md).

---

## Source basis

This capstone synthesizes the four delivered layer documents and the brief
(`.hamster/divya-gunasekarans-team/briefs/specsight-gtm-and-market-research-version2/brief.md`) —
specifically the brief's "GTM Engine You're Actually Building" six-layer model, the Commercial
Learning Loop diagram, and the four-workstream framing from the original proposal. It defines
architecture, interfaces, loop closure, sibling mapping, and methodology only; it produces no
layer content and no GTM assets.

---

*Sections: [§1 Six-layer interfaces](architecture/01-six-layer-interfaces.md) · [§2 Commercial Learning Loop](architecture/02-commercial-learning-loop.md) · [§3 Sibling GTM mapping & workstreams](architecture/03-sibling-gtm-mapping-and-workstreams.md) · [§4 Repeatable methodology](architecture/04-repeatable-research-methodology.md)*
