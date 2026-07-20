# Architecture §2 — The Commercial Learning Loop (Layer 6, Closure Mechanism)

> **Owning subtask:** DIV-41. **Parent:** DIV-36 (GTM Engine Architecture). **Brief:** Specsight
> GTM and Market Research Version2.
>
> This section defines **Layer 6** — the mechanism that closes the engine into a learning
> system. It builds directly on the layer definitions in
> [architecture §1](01-six-layer-interfaces.md): it enumerates the customer-interaction events
> that feed the loop, defines a feedback path from those interactions back to each of the five
> upstream layers, specifies the refinement trigger mechanism as a repeatable procedure, and
> draws the loop-closure diagram from Layer 6 back to Layer 1.

---

## Why the loop is the point

The brief is explicit that the destination "has never changed" since Document 1: build a *GTM
research and learning engine* whose defining property is that **every customer interaction
improves both GTM and product strategy**. Layers 1–5 are a forward pipeline; without Layer 6
they produce a one-time snapshot that decays as the market moves. Layer 6 is what makes the
engine *repeatable* — it turns each prospect conversation into a maintenance event on the graph.

The brief states the loop shape directly:

```text
Customer interactions
    ↓  Refine workflow model      (→ Layer 1)
    ↓  Refine buying triggers     (→ Layer 4)
    ↓  Improve messaging          (→ Layer 5)
    ↓  Improve demos              (→ Layer 5)
    ↓  Improve product positioning(→ Layer 5)
    ↓  Inform roadmap             (→ Layer 3 gap assessment → Layer 5 roadmap input)
```

This section makes that shape concrete: *which* interaction feeds *which* layer, and *how* a
refinement is actually triggered and propagated.

> **Layer 4 explicitly handed work to this loop.** The Layer 4 hub marks its detection methods,
> company-level signals, likelihood indicators, evaluation criteria, and Specsight-fit
> assessments as **detection candidates / fit hypotheses** — validated *thesis*, unvalidated
> *operational tuning* — to be confirmed through this loop. Validating those markers is the loop's
> first-priority job (see the Layer 4 feedback path below).

---

## 1. What constitutes a "customer interaction"

A customer interaction is any prospect- or customer-originated event that carries signal about
the workflow, the pain, the capability, the trigger, or the asset. Six types feed the loop; each
is produced as a by-product of a deployed Layer 5 asset (see [§1](01-six-layer-interfaces.md),
Interface 5 → 6).

| Interaction type | Originating Layer 5 asset | Signal it carries |
| --- | --- | --- |
| **Prospect conversation** | Outreach, discovery | How the prospect *describes* their workflow and pain in their own words — validates Layer 1 vocabulary and Layer 2 symptoms |
| **Discovery call** | Discovery questions | Structured confirmation/denial of specific workflow stages, failure modes, and trigger conditions |
| **Demo feedback** | Demo scenarios | Which capability claims land or fall flat — validates Layer 3 capability→value mappings |
| **Assessment completion** | PLG workflow assessment | Self-reported workflow state at scale — validates failure-mode prevalence and trigger detection signals |
| **Outreach response** | LinkedIn outreach, messaging | Whether the messaging (and the trigger it targeted) resonated — validates Layer 4 triggers and Layer 5 copy |
| **Product feedback** | Product usage, roadmap conversations | Whether shipped capability delivers the promised value — validates Layer 3 and informs the roadmap |

Each interaction is logged with: the asset that produced it, the interaction type, the raw
observation (in the customer's words wherever possible), and the layer entity ids it appears to
touch (`CN`/`FM`/`CAP`/`BT`).

---

## 2. Feedback path per upstream layer

For each of the five upstream layers, the loop defines *what customer data flows back* and *what
refinement it triggers*. Refinements are one of three verdicts: **validate** (evidence confirms
existing content — raise confidence), **refine** (evidence adjusts existing content — edit the
entry), or **add** (evidence reveals content the engine is missing — create a new entry, keeping
the id scheme).

### → Layer 1 — Industrial Knowledge Graph

- **Data flowing back:** customer descriptions of their own workflow — stages, artifacts,
  ceremonies, roles, decision points, and company-specific implementations.
- **Refinement triggered:** *validate* an existing concept node (`CN-01…CN-09`) when a prospect
  describes it in recognizable terms; *refine* a node's activities/artifacts when the description
  diverges; *add* a new concept node (`CN-10`, …) or a new company-implementation row when a
  prospect describes a stage the graph does not yet contain. Because Layer 1 is the substrate, a
  Layer 1 change is the highest-impact refinement — it triggers the full downstream propagation
  cascade (see §4).

### → Layer 2 — Failure Mode Library

- **Data flowing back:** customer descriptions of pain — the symptoms, evidence, and workarounds
  they report, in their own language.
- **Refinement triggered:** *validate* an existing `FM-NN` when a prospect reports its symptoms;
  *refine* an entry's symptom/evidence/workaround language toward the exact practitioner wording
  heard; *add* a new failure mode (`FM-26`, …) anchored to a `CN` node when a prospect reports a
  breakdown not yet catalogued; *re-rate* the underserved assessment when repeated interactions
  show a gap is (or is not) served by an incumbent tool.

### → Layer 3 — Capability Graph

- **Data flowing back:** customer reactions to Specsight's capability claims — which claims
  resonate, which are dismissed, what workaround/alternative they name, and what value language
  they use.
- **Refinement triggered:** *validate* a `CAP-NN` chain's Specsight-confidence rating when a demo
  lands; *refine* links 3–6 (workaround, alternatives, Specsight capability, customer value)
  toward the language customers actually use; *promote* a hypothesis capability (notably `CAP-07`,
  flagged a roadmap candidate) to validated when customers confirm a concrete Specsight
  capability, or *adjust* the `CapabilityGapAssessment` category when evidence changes.

### → Layer 4 — Buying Trigger Graph

- **Data flowing back:** customer confirmation or denial of trigger conditions and detection
  signals — did the trigger the outreach assumed actually precede their search? did the detection
  candidate correctly identify them?
- **Refinement triggered:** this is the loop's **first-priority path**, because Layer 4 shipped
  the largest set of *detection candidates / fit hypotheses*. *Validate* a `BT-NN` when
  confirmed; *refine* a detection method / company-level signal / evaluation criterion when the
  candidate mis-fires; *add* a new trigger (`BT-06`, …) when a prospect reports a workflow event
  that reliably precedes buying but is not in `BT-01…BT-05`; and convert each detection candidate
  from "hypothesis" to "validated" (or retire it) as evidence accumulates.

### → Layer 5 — GTM Assets

- **Data flowing back:** response rates, demo win/loss, assessment drop-off, objection patterns —
  the direct performance of the assets themselves.
- **Refinement triggered:** *refine* the specific asset — reword messaging toward `FM-NN`
  language that resonated, re-sequence outreach against the `BT-NN` that converted, add an
  objection-handling entry for a recurring objection, adjust assessment questions. Layer 5
  refinements are owned by the sibling-brief tasks that produce the assets; the loop supplies the
  evidence and the trigger, not the copy.

---

## 3. The refinement trigger mechanism (repeatable procedure)

A customer interaction becomes an engine change through a fixed five-step procedure. This is what
makes the loop a *process* rather than an aspiration — anyone can run it.

```text
Step 1  OBSERVE     Capture the raw interaction: asset, type, verbatim observation,
                    and the candidate layer entity ids it appears to touch (CN/FM/CAP/BT).

Step 2  CATEGORIZE  Route the observation to the layer it concerns (§2 feedback paths).
                    One observation may touch several layers — split it and route each part.

Step 3  VALIDATE    Compare against existing layer content:
                      • matches an existing entry            → verdict = VALIDATE
                      • conflicts / extends an existing entry → verdict = REFINE
                      • has no existing entry                 → verdict = ADD
                    Apply the layer's own validation criteria (Framework-5 separation,
                    practitioner language, observable behavior — see §4).

Step 4  UPDATE      Apply the verdict to the owning layer, preserving the id scheme:
                      • VALIDATE → raise the entry's confidence / evidence count
                      • REFINE   → edit the entry (keep its id)
                      • ADD      → mint the next id in sequence (CN-10, FM-26, CAP-08, BT-06)

Step 5  PROPAGATE   Run the downstream propagation rules (§4) for the layer just changed:
                    a Layer 1 change cascades furthest; a Layer 4 change reaches only Layer 5.
                    Record which downstream layers were checked and what changed.
```

A single validated interaction that adds a failure mode, for example, does not stop at Layer 2:
Step 5 forces a check for a new `CAP` mapping in Layer 3, then a new `BT` in Layer 4, then a new
asset in Layer 5 — which is exactly the extension methodology documented in
[§4](04-repeatable-research-methodology.md).

> **Batching vs. real-time.** VALIDATE verdicts (confidence bumps) can accumulate and be applied
> in periodic review; REFINE and ADD verdicts should be applied promptly because they change what
> downstream assets say. The loop does not require a single interaction to rewrite the engine —
> it requires that *repeated* interactions reliably drive the entry toward the truth.

---

## 4. Loop closure diagram

The forward pipeline is §1's concern; this diagram shows the **return paths** that complete the
circuit from Layer 6 back to each upstream layer, closing to Layer 1.

```text
        FORWARD  (see §1)                         FEEDBACK  (this section)
        ───────────────►                          ◄───────────────

   ┌── L1 Industrial Knowledge Graph ◄──────────────────────────────────────────┐
   │        │  CN-01…CN-09                    validate/refine/add CN              │
   │        ▼                                 (workflow descriptions)             │
   │   L2 Failure Mode Library ◄──────────────────────────────────┐              │
   │        │  FM-01…FM-25                validate/refine/add FM   │              │
   │        ▼                             (pain descriptions)      │              │
   │   L3 Capability Graph ◄───────────────────────────┐          │              │
   │        │  CAP-01…CAP-07          validate/refine   │          │              │
   │        ▼                         CAP (demo         │          │              │
   │   L4 Buying Trigger Graph ◄──────────┐  reactions) │          │              │
   │        │  BT-01…BT-05    validate/   │             │          │              │
   │        ▼                 refine BT   │             │          │              │
   │   L5 GTM Assets ─────────────────────┼─────────────┼──────────┼──────────────┤
   │        │  deploy                     │  confirm    │  demo    │  workflow    │
   │        ▼                             │  triggers   │  reacts  │  descriptions│
   │   ┌─────────────────────────────┐    │             │          │              │
   └──►│ L6 COMMERCIAL LEARNING LOOP  │────┴─────────────┴──────────┴──────────────┘
       │  observe → categorize →      │  outreach/demo/assessment responses feed
       │  validate → update →         │  every upstream layer; refinements
       │  propagate                   │  propagate forward again (§4 rules)
       └─────────────────────────────┘
```

| Feedback path | Interaction source | Verdict types | Owning layer / task |
| --- | --- | --- | --- |
| L6 → **L1** | Prospect conversation, discovery call | validate / refine / add `CN` | DIV-32 |
| L6 → **L2** | Prospect conversation, assessment completion | validate / refine / add `FM` | DIV-33 |
| L6 → **L3** | Demo feedback, product feedback | validate / refine / promote `CAP` | DIV-34 |
| L6 → **L4** | Outreach response, discovery call *(first priority — validates detection candidates)* | validate / refine / add `BT` | DIV-35 |
| L6 → **L5** | Outreach response, demo feedback, assessment drop-off | refine asset | sibling brief |

The loop is closed: an outreach response (L5 asset output) can, in one pass of the §3 procedure,
confirm a `BT` (L4), sharpen an `FM`'s wording (L2), and reveal a missing `CN` (L1) — after which
the §4 propagation rules push those refinements forward through the pipeline again. That is the
"continuous commercial learning loop" the original proposal envisioned, made operational.
