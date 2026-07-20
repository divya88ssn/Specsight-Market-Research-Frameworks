# Layer 4 — Buying Trigger Graph (Workflow Events → Buying Intent)

> **This is the canonical Layer 4 document of the Specsight GTM engine.** It connects workflow
> events to buying intent through observable signals, replacing demographic-based ICP with
> workflow-based trigger detection. Every buying trigger is traced from a specific workflow event
> through to a recognizable buying-intent signal — never from a demographic attribute — and each
> is anchored to the Layer 2 failure mode (`FM-NN`) that produces it.
>
> **Owning parent task:** DIV-35. **Brief:** Specsight GTM and Market Research Version2.
> **Consumes:** Layer 1 — Industrial Knowledge Graph
> ([`layer-1-industrial-knowledge-graph.md`](layer-1-industrial-knowledge-graph.md)) and Layer 2
> — Failure Mode Library ([`layer-2-failure-mode-library.md`](layer-2-failure-mode-library.md)).

---

## What Layer 4 is (and is not)

Layer 4 is the **Buying Trigger Graph**: for every buying trigger, a structured chain from an
externally observable **operational event**, through the **workflow breakdown** it exposes (a
Layer 2 `FM-NN`), to the prospect's **recognition of a capability gap**, the **buying trigger**
behavior, and — extending Framework 4 — the **evaluation criteria** and **decision process** the
prospect runs. It is the brief's **Framework 4 (Workflow Event → Buying Trigger)** made
operational, plus the **friction-detection & Specsight-fit model** that replaces demographic ICP
dimensions.

The brief's core thesis drives the whole layer:

> **Buying triggers emerge from operating systems — not from demographics, company size, or job
> titles.**

Layer 4 is **not** a catalogue of failure modes (that is Layer 2, DIV-33) and **not** a mapping
of failure modes to Specsight capabilities (that is Layer 3, DIV-34). It references `FM-NN` ids
as the workflow breakdowns that fire triggers and references capability *gaps* at the Layer 2
underserved level, but the depth capability→Specsight mapping is Layer 3's. It also does not
build the ICP scoring model, the outreach sequences, or the PLG assessment tool — those are
Layer 5 / sibling-brief tasks that *consume* this graph.

---

## Document structure

Layer 4 is composed of four sections, each a self-contained file. Section 1 is foundational and
establishes the `BT-NN` id scheme; §2–§4 build on it.

| # | Section | File | Owning subtask | What it provides |
| --- | --- | --- | --- | --- |
| 1 | Buying Trigger Events & Detection Methods | [`layer-4/01-trigger-events-detection-methods.md`](layer-4/01-trigger-events-detection-methods.md) | DIV-39 | The full Framework-4 chain per trigger; the `BT-NN` id scheme; a detection method per trigger |
| 2 | Failure Mode → Company-Level Signals | [`layer-4/02-failure-mode-company-signals.md`](layer-4/02-failure-mode-company-signals.md) | DIV-45 | The six practitioner failure modes mapped to externally detectable company signals + correlated triggers |
| 3 | Evaluation Criteria & Decision Process | [`layer-4/03-evaluation-criteria-decision-process.md`](layer-4/03-evaluation-criteria-decision-process.md) | DIV-50 | Per-trigger evaluation criteria, five-stage decision process, decision roles, information sources |
| 4 | Friction Detection & Specsight-Fit Model | [`layer-4/04-friction-detection-specsight-fit.md`](layer-4/04-friction-detection-specsight-fit.md) | DIV-55 | Per-trigger friction detection + fit assessment; the demographic → workflow replacement table |

---

## The trigger chain (Framework 4, extended)

```text
   Operational Event ─► Workflow Breakdown ─► Recognition of ─► Buying Trigger ─► Evaluation ─► Decision
   (externally           (a Layer 2 FM-NN      Capability Gap    (search /         Criteria      Process
    observable)           fires)               ("we need …")     evaluation)       (§3)          (§3)
        │                     │                                                       │
        └── §1 detection ─────┘                                                       └── §4 friction/fit
            method                                                                        replaces demographics
```

- **§1** defines Operational Event → Workflow Breakdown → Recognition → Buying Trigger + detection.
- **§3** extends the chain with Evaluation Criteria → Decision Process.
- **§2** provides the company-level (not just event-level) detection layer.
- **§4** synthesizes all three into friction detection and the demographic→workflow replacement.

---

## The `BT-NN` buying-trigger id scheme

Every buying trigger has a **stable `BT-NN` id** (the primary cross-reference key for §2–§4 and
downstream Layers 5–6) plus a human-readable slug. Ids are assigned once, in reading order, and
never reused — mirroring the Layer 2 `FM-NN` scheme. Full definitions are in
[Section 1](layer-4/01-trigger-events-detection-methods.md).

| BT | Buying trigger | Identifier | Detection method (candidate) | Anchoring `FM-NN` |
| --- | --- | --- | --- | --- |
| **BT-01** | VP Product / Head of Product hire | `vp_product_hire` | LinkedIn new-hire & job-change alerts (VP/Head of Product) | FM-22, FM-25, FM-18, FM-21, FM-14 |
| **BT-02** | Product Ops / Product Operations hire | `product_ops_hire` | LinkedIn job-posting keyword analysis ("Product Ops") | FM-05, FM-24, FM-22, FM-23 |
| **BT-03** | Engineering growth outpacing PM hiring | `engineering_growth` | LinkedIn employee-count tracking; eng-vs-PM req volume | FM-12, FM-08, FM-09, FM-10, FM-01, FM-14 |
| **BT-04** | AI coding tool adoption | `ai_coding_adoption` | GitHub public-repo analysis; eng-blog & job-post signals | FM-08, FM-12, FM-15, FM-04, FM-19, FM-17, FM-14 |
| **BT-05** | Series A funding | `series_a_funding` | Crunchbase funding alerts + headcount-growth signal | FM-14, FM-09, FM-05, FM-22, FM-01 |

> **Highest-probability trigger zone.** Per Layer 1 [Section 5](layer-1/05-refinement-boundary-gap.md),
> the **refinement boundary gap** (anchored on `FM-14`) is where buying triggers are most likely
> to fire — BT-03 and BT-04 sit squarely there, and BT-01/BT-02/BT-05 each anchor on the
> underserved Context Reconstruction Tax and boundary-gap clusters.

---

## Grounding in Layers 1 and 2 (the cross-reference contract)

| Upstream layer | How Layer 4 builds on it |
| --- | --- |
| **Layer 1 — Industrial Knowledge Graph** (DIV-32) | Triggers are located at Layer 1 stages and concept nodes (`CN-01…CN-09`); the refinement boundary gap (Layer 1 §5) is the highest-probability trigger zone. |
| **Layer 2 — Failure Mode Library** (DIV-33) | Every trigger's *workflow breakdown* is a Layer 2 `FM-NN`. Triggers anchor most heavily on the underserved set (esp. `FM-14` and the Context Reconstruction Tax `FM-22…FM-25`) per Layer 2 §5. |

> **Detection-status convention (used throughout Layer 4).** The triggers, the six practitioner
> failure modes, and the practitioner-language quotes are *validated* from the research
> (Documents 2–9, Layers 1–2). The **detection methods, company-level signals, likelihood
> indicators, evaluation criteria, and Specsight-fit assessments** are GTM operational proposals —
> **detection candidates / fit hypotheses** to be validated and tuned through the Layer 6
> Commercial Learning Loop. They are marked as such in-line. Concrete Specsight product details
> are deferred to Layer 3 (DIV-34); Layer 4 references capability *gaps* only.

---

## Cross-reference contract for downstream layers

| Downstream layer | Parent | How it builds on Layer 4 |
| --- | --- | --- |
| **Layer 5 — GTM Assets** | sibling brief | Consumes `BT-NN` triggers, signals, evaluation criteria, and the demographic→workflow model to generate ICP refinement, outreach sequencing, and the PLG workflow assessment — without re-interpretation. |
| **Layer 6 — Commercial Learning Loop** | Planned | Every prospect interaction validates or refines the `BT-NN` triggers, detection candidates, and fit hypotheses defined here. |

> **Scope discipline observed in Layer 4:** this graph derives buying triggers, detection
> methods, evaluation/decision process, and the friction/fit model. It deliberately does **not**
> re-catalogue failure modes (DIV-33), map capabilities to Specsight in depth (Layer 3 / DIV-34),
> or build ICP/outreach/PLG assets (Layer 5). Where those are touched, it is only to name a
> boundary or a downstream connection.

---

## How the demographic reframing lands

The parent task's defining requirement — replacing company size, budget, and industry with
workflow events — is delivered in [Section 4](layer-4/04-friction-detection-specsight-fit.md)'s
demographic→workflow replacement table:

| Dimension | Replaced by (workflow-based) |
| --- | --- |
| Company size | Workflow complexity signals (PM-to-engineer ratio, number of product teams, engineering-growth rate) |
| Budget | Trigger-event urgency (active workflow breakdown creating acute pain now) |
| Industry | Workflow-model adoption (Agile/ceremony maturity, DoD/evidence documentation) |
| Job title | Role-in-workflow-pain (who is experiencing the breakdown, not who holds the title) |

---

## Source basis

All content derives from the nine research documents narrated in the brief
(`.hamster/divya-gunasekarans-team/briefs/specsight-gtm-and-market-research-version2/brief.md`) —
principally **Framework 4** (Workflow Event → Buying Trigger), **Framework 5** (study where
practitioners complain), and **Framework 6** (PLG through workflow assessment) from Document 2 —
grounded in Layer 1 (concept nodes, stages, the refinement boundary gap) and Layer 2 (`FM-NN`
failure modes). Where the research does not establish a concrete detection signal or Specsight
product detail, it is marked as a detection candidate / fit hypothesis rather than invented.
