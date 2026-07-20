# Architecture §3 — Sibling GTM Task Consumption Map & Four-Workstream Trace

> **Owning subtask:** DIV-44. **Parent:** DIV-36 (GTM Engine Architecture). **Brief:** Specsight
> GTM and Market Research Version2.
>
> This section proves the engine is not standalone research but the **substrate feeding all GTM
> activities**. Part 1 maps each Layer 5 GTM asset to the engine-layer output it consumes and the
> sibling-brief task that owns producing it. Part 2 traces each of the original GTM Collaboration
> Proposal's four workstreams to the engine layers that operationalize it. Both parts build on the
> layer definitions and output contracts in [architecture §1](01-six-layer-interfaces.md).

---

## Part 1 — Sibling GTM Task Consumption Map

The brief lists the GTM assets the engine produces at **Layer 5**: ICP refinement, LinkedIn
outreach, website messaging, interactive workflow assessment (PLG), demo scenarios, discovery
questions, objection handling, product positioning, and product roadmap input. Each is *consumed*
(produced) by a sibling-brief GTM task that reads specific engine-layer outputs — it does not
re-derive the research.

> **Convention.** "Consumes from" names the engine layer(s) whose *output contract* the asset
> reads (per §1). The specific ids (`FM-NN`, `CAP-NN`, `BT-NN`) are the concrete data used. The
> owning task is a sibling-brief GTM task; none of these are owned by this brief's prior waves,
> so Layer 5 remains **planned / sibling-brief**.

| GTM asset (Layer 5 output) | Consumes from | Specific engine data used | Owning sibling task |
| --- | --- | --- | --- |
| **ICP refinement** | Layer 4 (primary) + Layer 3 | `BT-01…BT-05` triggers + company-level signals + the **demographic→workflow replacement** model; `CAP-NN` confidence to weight fit | ICP refinement |
| **Interactive workflow assessment (PLG)** | Layer 2 + Layer 3 + Layer 4 | `FM-01…FM-25` (self-diagnosis questions in practitioner language); `CAP-NN` links 1–2 (which gap each answer implies); `BT-NN` (which trigger the workflow state signals) | PLG workflow assessment |
| **LinkedIn outreach** | Layer 4 (primary) + Layer 2 | `BT-NN` detection method + timing (who to reach, when); `FM-NN` symptom language (what to say) | Outreach messaging |
| **Website messaging** | Layer 3 + Layer 2 | `CAP-NN` links 5–6 (Specsight capability + customer value); `FM-NN` practitioner language for the pain framing | Website positioning |
| **Demo scenarios** | Layer 3 + Layer 2 | `CAP-NN` links 5–6 mapped to the `FM-NN` pain each scenario resolves | (demo — sibling brief) |
| **Discovery questions** | Layer 4 + Layer 2 | `BT-NN` evaluation criteria & five-stage decision process (§3 of Layer 4); `FM-NN` symptoms to probe | (discovery — sibling brief) |
| **Objection handling** | Layer 3 + Layer 4 | `CAP-NN` existing-alternatives (links 3–4) and Specsight capability (link 5); `BT-NN` evaluation criteria | (objection handling — sibling brief) |
| **Product positioning** | Layer 3 + Layer 1 | `CAP-NN` customer value (link 6) anchored to the Layer 1 refinement boundary gap as the differentiated frontier | Website positioning / product positioning |
| **Product roadmap input** | Layer 3 (primary) + Layer 6 | the `CapabilityGapAssessment` (current / partial / expansion / new-area, e.g. `CAP-02` highest-value near-term, `CAP-07` new area); Layer 6 feedback re-prioritizes it | Product roadmap |

### What this demonstrates

- Every GTM asset traces to a **named engine output**, not to intuition. ICP refinement is not a
  demographic exercise — it consumes `BT-NN` triggers and the demographic→workflow model. The PLG
  assessment is not a feature tour — it consumes `FM-NN` failure modes as self-diagnosis
  questions (the brief's Framework 6: "assess your workflow," not "try our product").
- The engine is the **substrate**: remove it and every asset loses its source. The sibling tasks
  produce copy and tools; the engine produces the *truth* they encode.
- Layer 5 is where the forward pipeline terminates and the Layer 6 loop originates — the same
  deployed assets that consume engine outputs generate the customer interactions that refine them
  (see [§2](02-commercial-learning-loop.md)).

---

## Part 2 — Four-Workstream Relationship Trace

Document 1 (the GTM Collaboration Proposal) established four parallel workstreams and the idea
that they should be driven by a **continuous commercial learning loop** rather than run as
independent activities. The engine operationalizes exactly this. Each workstream maps to the
engine layers that execute it:

| Original workstream (Document 1) | Operationalized by | How the engine executes it |
| --- | --- | --- |
| **Customer Decision Research** | **Layers 1–4** (Industrial Knowledge Graph → Buying Trigger Graph) | The research that discovers and validates *how customers make buying decisions*: the workflow model (`CN`), where it breaks (`FM`), the capability gaps (`CAP`), and the observable buying triggers (`BT`). This is the "understand decision-making instead of optimizing messaging" mandate made concrete. |
| **Positioning** | **Layer 5** — website messaging & product positioning | Consumes Layer 3 `CAP-NN` customer value (link 6) and Layer 2 `FM-NN` language, anchored on the refinement boundary gap as the differentiated frontier. Positioning is *derived from* the capability graph, not authored in isolation. |
| **GTM Optimization** | **Layer 5** — ICP refinement, outreach, PLG assessment | Consumes Layer 4 `BT-NN` triggers/signals and the demographic→workflow model. Optimization means targeting the workflow event that precedes buying, not tuning demographics. |
| **Product Strategy** | **Layer 5 roadmap input, fed by Layer 3 + Layer 6** | Consumes the Layer 3 `CapabilityGapAssessment` and is continuously re-prioritized by Layer 6 feedback (product feedback → `CAP` validation → roadmap). This is the workstream most dependent on the loop being closed. |

### How the proposal's "continuous learning loop" is operationalized

The proposal's central idea — that GTM, positioning, product feedback, and product strategy
should all improve together through one loop rather than as separate functions — is realized by
the engine's structure, not asserted:

```text
   PROPOSAL (Document 1)                    ENGINE (Layers 1–6)
   ─────────────────────                    ───────────────────
   Customer Decision Research   ───────►    Layers 1–4  (CN → FM → CAP → BT)
   Positioning                  ───────►    Layer 5     (messaging / positioning ← CAP link 6)
   GTM Optimization             ───────►    Layer 5     (ICP / outreach / PLG ← BT + demo→wf)
   Product Strategy             ───────►    Layer 5 roadmap ← Layer 3 gap assessment
                                              ▲
   "continuous commercial       ───────►    Layer 6 Commercial Learning Loop
    learning loop"                            closes every workstream back into Layers 1–4
                                              (see §2) — no workstream runs open-loop
```

- The three *execution* workstreams (Positioning, GTM Optimization, Product Strategy) all draw
  from the same research spine (Customer Decision Research → Layers 1–4). That shared spine is
  why the proposal could call them "parallel" yet interdependent — they consume one substrate.
- The loop the proposal envisioned is **Layer 6**: every customer interaction generated by the
  execution workstreams (Layer 5 assets) feeds back through the [§2](02-commercial-learning-loop.md)
  closure mechanism into Customer Decision Research (Layers 1–4), which then re-feeds the
  execution workstreams. No workstream runs open-loop. This is the proposal's vision — "GTM,
  product feedback, and positioning driven by a continuous commercial learning loop rather than
  independent activities" — expressed as an operable architecture.

> **The engine is the proposal, executed.** Document 1 defined *what* to do (four workstreams, one
> loop) but not *how to run it every week*. The six layers are the "how": Layers 1–4 are Customer
> Decision Research as a maintained graph; Layer 5 is the three execution workstreams reading that
> graph; Layer 6 is the loop that keeps all four honest.
