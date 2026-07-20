# Architecture §1 — The Six Engine Layers & Their Inter-Layer Interfaces

> **Owning subtask:** DIV-37. **Parent:** DIV-36 (GTM Engine Architecture). **Brief:** Specsight
> GTM and Market Research Version2.
>
> This is the **structural backbone** of the architecture document. It defines each of the six
> engine layers as a node in a connected pipeline — its purpose, what it *consumes* from the
> layer before it, what it *produces* for the layer after it, and which sibling parent task owns
> building its content. Every other architecture section (§2 loop closure, §3 sibling mapping, §4
> methodology) references the layer names and interfaces defined here.

---

## Why layers, not documents

Layers 1–4 already exist as delivered, self-contained research artifacts (see the layer hubs
linked below). Left as four documents they read as four separate studies. The engine claim is
stronger: each layer **consumes a typed output** from the layer before it and **produces a typed
output** for the layer after it. Naming those contracts is what converts four artifacts into one
operable, maintainable pipeline. This section names them.

The canonical forward pipeline (from the brief's "GTM Engine You're Actually Building" section)
is fixed and is the reference ordering for every subtask:

```text
Industrial Knowledge Graph → Failure Mode Library → Capability Graph
    → Buying Trigger Graph → GTM Assets → Commercial Learning Loop
```

The brief's fuller data-flow narration expands the same six layers into the stages they carry:

```text
Customer Decision Research → PM Workflow → Industry Operating Model → Observable Workflow Events
    → Emerging Failure Modes → Capability Gaps → Buying Triggers → ICP Refinement
    → PLG Workflow Assessment → Messaging → Demo → Product Feedback → Roadmap
```

---

## The `LayerInterface` contract

Every layer is described with the same shape so the pipeline can be read as a sequence of typed
hand-offs rather than prose. This is the shared contract referenced by all architecture
subtasks:

```text
LayerInterface {
  layerName:        string   // canonical layer name (e.g. "Failure Mode Library")
  purpose:          string   // one-paragraph statement of what the layer does in the engine
  consumes:         string   // the structured artifact received from the previous layer
  produces:         string   // the structured artifact passed to the next layer
  siblingTaskOwner: string   // the parent task that owns building this layer's content
}
```

`consumes`/`produces` are deliberately **concrete artifacts with named id schemes** (`CN-NN`,
`FM-NN`, `CAP-NN`, `BT-NN`), never vague descriptions like "workflow information". An id scheme
is what makes an interface stable: a downstream layer can attach to `FM-14` without re-reading
how `FM-14` was derived.

---

## Layer 1 — Industrial Knowledge Graph

- **`layerName`** — Industrial Knowledge Graph
- **`purpose`** — Builds a structured, referenceable understanding of how mature product
  organizations actually work: PM lifecycle stages, operating-model concepts, artifacts,
  ceremonies, roles, decision points, review mechanisms, and company-specific implementations,
  expressed in the vocabulary practitioners already recognize. It is the substrate that makes
  every downstream layer credible instead of generic. It is *not* a framework Specsight sells.
- **`consumes`** — The nine research documents (customer decision research, industry grounding,
  operating-model synthesis) narrated in the brief. This is the engine's raw intake boundary;
  Layer 1 has no upstream *engine* layer.
- **`produces`** — **Nine concept nodes `CN-01…CN-09`** (Backlog Refinement, Three Amigos, Story
  Clarification, Acceptance Criteria, Definition of Done, Product Owner Acceptance, Continuous
  Collaboration, Story Acceptance, Sprint Review) with their edges; the two-loop operating model
  and Continuous Product Alignment lens; a per-company evidence matrix; and the **refinement
  boundary gap** (Section 5), the under-documented execution middle where practitioner pain
  concentrates. Each `CN` node carries its stages, activities, artifacts, roles, and decision
  points.
- **`siblingTaskOwner`** — **DIV-32** — *Research can be consolidated into a structured
  Industrial Knowledge Graph*. Canonical output:
  [`layer-1-industrial-knowledge-graph.md`](../layer-1-industrial-knowledge-graph.md).

**Interface 1 → 2:** the Failure Mode Library consumes the `CN-01…CN-09` workflow stages —
each with its activities, artifacts, roles, and decision points — plus the refinement boundary
gap, and catalogues *where each breaks down*.

---

## Layer 2 — Failure Mode Library

- **`layerName`** — Failure Mode Library
- **`purpose`** — For every workflow stage in Layer 1, catalogues the recurring ways the
  workflow breaks down — each with observable symptoms in practitioner language, the evidence
  that appears, the workaround teams use, the Framework-5 expert-vs-practitioner separation, and
  an underserved-by-existing-tools assessment. It converts a neutral workflow map into a map of
  *pain*, in the exact words prospects use.
- **`consumes`** — From Layer 1: the concept nodes `CN-01…CN-09` (with activities, artifacts,
  roles, decision points) and the refinement boundary gap, as the stages against which failure
  modes are anchored.
- **`produces`** — **25 failure modes `FM-01…FM-25`**, each conforming to the `FailureModeEntry`
  schema and anchored to one or more `CN` nodes, organized by workflow stage. Includes the
  underserved summary (19 underserved / 6 partially served) that flags Specsight's strongest
  openings — anchored on the refinement boundary gap (`FM-14`) and the Context Reconstruction Tax
  (`FM-22…FM-25`).
- **`siblingTaskOwner`** — **DIV-33** — *A Failure Mode Library can be derived from validated
  practitioner discussions*. Canonical output:
  [`layer-2-failure-mode-library.md`](../layer-2-failure-mode-library.md).

**Interface 2 → 3:** the Capability Graph consumes the `FM-01…FM-25` ids (with their symptoms,
evidence, and workarounds) and attaches a capability mapping to each id.

---

## Layer 3 — Capability Graph

- **`layerName`** — Capability Graph
- **`purpose`** — Connects each failure mode to the capability gap it represents and to the
  Specsight capability that fills it, via the six-link chain *failure mode → missing capability →
  current workaround → existing alternatives → Specsight capability → customer value* — then
  assesses the gap between Specsight's current and missing capabilities as a roadmap input. It is
  what lets Specsight say *exactly which capability gap it fills and why that gap matters*.
- **`consumes`** — From Layer 2: the `FM-01…FM-25` ids with their symptoms, evidence, and
  workarounds. From Layer 1: the `CN` ids and workflow stages the failure modes sit on.
- **`produces`** — **Seven missing capabilities `CAP-01…CAP-07`** (a total, non-overlapping
  partition of the 25 `FM` ids), each with a complete six-link `CapabilityMappingChain`, a
  Specsight-confidence rating, and a gap category; plus the `CapabilityGapAssessment` (current /
  partial / expansion / new-area) that is the roadmap's input. Links 1–2 (failure mode + missing
  capability) feed Layer 4; links 5–6 (Specsight capability + customer value) feed Layer 5.
- **`siblingTaskOwner`** — **DIV-34** — *A Capability Graph can connect failure modes to
  Specsight capabilities*. Canonical output:
  [`layer-3-capability-graph.md`](../layer-3-capability-graph.md).

**Interface 3 → 4:** the Buying Trigger Graph consumes links 1–2 per `CAP-NN`/`FM-NN` (the
failure mode and the recognized missing capability) to derive the buying triggers that fire when
a prospect recognizes the gap.

---

## Layer 4 — Buying Trigger Graph

- **`layerName`** — Buying Trigger Graph
- **`purpose`** — Reframes buying intent away from demographics: derives buying triggers from
  observable workflow events via the chain *operational event → workflow breakdown → recognition
  of capability gap → buying trigger → evaluation criteria → decision process*, and defines a
  friction-detection & Specsight-fit model that replaces company-size / budget / industry / job
  title as ICP dimensions. It answers *when a prospect is likely to feel friction and go
  looking*.
- **`consumes`** — From Layer 2: the `FM-NN` ids as the workflow breakdowns that fire triggers
  (anchoring most on the underserved set, esp. `FM-14` and `FM-22…FM-25`). From Layer 3: links
  1–2 (failure mode + missing capability) per `CAP-NN`. From Layer 1: the concept nodes / stages
  and the refinement boundary gap as the highest-probability trigger zone.
- **`produces`** — **Five buying triggers `BT-01…BT-05`** (VP Product hire, Product Ops hire,
  engineering growth outpacing PM hiring, AI coding tool adoption, Series A funding), each with a
  full Framework-4 chain, a detection method, company-level signals, per-trigger evaluation
  criteria and a five-stage decision process, and a per-trigger friction/fit assessment; plus the
  demographic → workflow replacement table. Detection methods, signals, and fit assessments are
  explicitly marked **detection candidates / fit hypotheses** for Layer 6 to validate.
- **`siblingTaskOwner`** — **DIV-35** — *A Buying Trigger Graph can connect workflow events to
  buying intent*. Canonical output:
  [`layer-4-buying-trigger-graph.md`](../layer-4-buying-trigger-graph.md).

**Interface 4 → 5:** GTM Assets consume the `BT-NN` triggers, their signals and evaluation
criteria, the demographic→workflow model, and (from Layer 3) the `CAP-NN` links 5–6, to produce
concrete GTM collateral — without re-interpreting the research.

---

## Layer 5 — GTM Assets

- **`layerName`** — GTM Assets
- **`purpose`** — Generates the concrete, customer-facing GTM collateral directly from the graph:
  ICP refinement, LinkedIn outreach, website messaging, an interactive workflow assessment (PLG),
  demo scenarios, discovery questions, objection handling, product positioning, and product
  roadmap input. This is the layer where the engine's research becomes revenue-facing work.
- **`consumes`** — From Layer 4: the `BT-01…BT-05` triggers, company-level signals, evaluation
  criteria, decision process, and the demographic→workflow replacement model. From Layer 3: the
  `CAP-NN` links 5–6 (Specsight capability + customer value) and the `CapabilityGapAssessment`
  (for roadmap input). From Layer 2: the `FM-NN` practitioner language (for messaging and
  assessment questions).
- **`produces`** — Deployed GTM assets and, as a by-product of their use, the **customer
  interactions** (prospect conversations, demo feedback, assessment completions, outreach
  responses, discovery calls, product feedback) that become Layer 6's input. Layer 5 is where the
  engine touches the market and therefore where the learning loop's raw signal originates.
- **`siblingTaskOwner`** — **Sibling-brief GTM tasks** (ICP refinement, PLG workflow assessment,
  outreach messaging, website positioning, product roadmap). **No prior wave in this brief owns
  Layer 5 content** — this architecture defines its *interface* only; producing the assets
  themselves is out of scope here (see §3 for the consumption map). Status: **planned /
  sibling-brief**.

**Interface 5 → 6:** the Commercial Learning Loop consumes the customer interactions produced by
deployed GTM assets and routes each interaction back to the upstream layer it validates or
refines.

---

## Layer 6 — Commercial Learning Loop

- **`layerName`** — Commercial Learning Loop
- **`purpose`** — Closes the engine into a learning system. Every customer interaction is
  captured, categorized, validated against existing layer content, and turned into a refinement
  that propagates back through the layers — validating or refining the workflow model (Layer 1),
  failure modes (Layer 2), capability mappings (Layer 3), buying triggers (Layer 4), and GTM
  assets (Layer 5). This is what makes the engine *repeatable and self-improving* rather than a
  one-time research output; it operationalizes the original proposal's "continuous commercial
  learning loop."
- **`consumes`** — From Layer 5: customer interactions with the signal each carries. Reads the
  full upstream content — `CN-NN`, `FM-NN`, `CAP-NN`, `BT-NN` — to validate observations against
  it, paying special attention to the Layer 4 **detection candidates / fit hypotheses** it was
  explicitly asked to confirm.
- **`produces`** — Validated or refined engine content: new/updated `CN`/`FM`/`CAP`/`BT` entries
  and updated GTM assets, fed back into the owning layer. Its output is *the same artifacts the
  other layers produce* — the loop does not create a new id scheme, it maintains the existing
  ones. This closes back to Layer 1, completing the cycle.
- **`siblingTaskOwner`** — **DIV-36 (this architecture document)** — no separate sibling parent
  task owns Layer 6; its closure mechanism is defined in
  [architecture §2](02-commercial-learning-loop.md). Status: **defined-in-architecture**.

**Interface 6 → 1 (loop closure):** refinements flow back into the Industrial Knowledge Graph
and cascade forward again through the pipeline. The closure mechanism — interaction types,
per-layer feedback paths, the refinement trigger procedure, and the loop diagram — is defined in
§2. The propagation rules that govern how a change in one layer cascades to downstream layers are
in §4.

---

## Summary: the six-layer pipeline

```text
┌────────────────────────────────────────────────────────────────────────────────────────┐
│  L1 Industrial Knowledge Graph   [DIV-32 ✓]                                              │
│    consumes: 9 research documents                                                        │
│    produces: CN-01…CN-09 stages + edges + operating model + refinement boundary gap      │
└───────────────────────────────┬──────────────────────────────────────────────────────── ┘
        CN-01…CN-09 (+ activities/artifacts/roles/decision points), boundary gap
                                 ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│  L2 Failure Mode Library         [DIV-33 ✓]                                              │
│    consumes: CN-01…CN-09 workflow stages                                                 │
│    produces: FM-01…FM-25 (symptoms, evidence, workaround, underserved rating)            │
└───────────────────────────────┬──────────────────────────────────────────────────────── ┘
        FM-01…FM-25 (with symptoms / evidence / workarounds)
                                 ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│  L3 Capability Graph             [DIV-34 ✓]                                              │
│    consumes: FM-01…FM-25                                                                  │
│    produces: CAP-01…CAP-07 (6-link chain) + CapabilityGapAssessment                      │
└───────────────────────────────┬──────────────────────────────────────────────────────── ┘
        CAP-NN links 1–2 (failure mode + missing capability)      │ links 5–6 → L5
                                 ▼                                 │  CapabilityGapAssessment → L5 roadmap
┌────────────────────────────────────────────────────────────────────────────────────────┐
│  L4 Buying Trigger Graph         [DIV-35 ✓]                                              │
│    consumes: FM-NN + CAP-NN links 1–2                                                     │
│    produces: BT-01…BT-05 (chain, detection, eval/decision, friction/fit) + demo→wf table │
└───────────────────────────────┬──────────────────────────────────────────────────────── ┘
        BT-01…BT-05 + signals + evaluation criteria + demographic→workflow model
                                 ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│  L5 GTM Assets                   [sibling brief — planned]                                │
│    consumes: BT-NN + CAP-NN links 5–6 + FM-NN language                                    │
│    produces: ICP, outreach, messaging, PLG assessment, demos, positioning, roadmap input │
│              → and the customer interactions those assets generate                        │
└───────────────────────────────┬──────────────────────────────────────────────────────── ┘
        customer interactions (conversations, demo feedback, assessments, responses, product feedback)
                                 ▼
┌────────────────────────────────────────────────────────────────────────────────────────┐
│  L6 Commercial Learning Loop     [DIV-36 — defined here]                                  │
│    consumes: customer interactions; reads CN/FM/CAP/BT                                     │
│    produces: validated / refined CN·FM·CAP·BT + updated GTM assets                        │
└───────────────────────────────┬──────────────────────────────────────────────────────── ┘
        refinements
        └────────────────────────────────────────────────────────────────►  back to L1  (loop closes — see §2)
```

### Pipeline table

| Layer | Name | Consumes | Produces | Owner | Status |
| --- | --- | --- | --- | --- | --- |
| **1** | Industrial Knowledge Graph | 9 research documents | `CN-01…CN-09` + operating model + boundary gap | DIV-32 | ✅ delivered |
| **2** | Failure Mode Library | `CN-01…CN-09` stages | `FM-01…FM-25` (symptoms/evidence/workaround) | DIV-33 | ✅ delivered |
| **3** | Capability Graph | `FM-01…FM-25` | `CAP-01…CAP-07` six-link chains + gap assessment | DIV-34 | ✅ delivered |
| **4** | Buying Trigger Graph | `FM-NN` + `CAP-NN` links 1–2 | `BT-01…BT-05` + friction/fit + demo→wf table | DIV-35 | ✅ delivered |
| **5** | GTM Assets | `BT-NN` + `CAP-NN` links 5–6 + `FM-NN` language | ICP / outreach / messaging / PLG / demos / positioning / roadmap input + customer interactions | sibling brief | planned |
| **6** | Commercial Learning Loop | customer interactions; `CN`/`FM`/`CAP`/`BT` | refined `CN`·`FM`·`CAP`·`BT` + updated assets → back to L1 | DIV-36 (this doc) | defined here |

> **Reading guarantee.** Someone unfamiliar with the research can read this table top to bottom
> and see, for each layer, what data enters, what data leaves, who owns it, and where it goes
> next — without opening a single layer document. The layer documents supply the *content*; this
> section supplies the *contracts*.
