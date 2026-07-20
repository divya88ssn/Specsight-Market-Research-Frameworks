# Architecture §4 — Repeatable Research Methodology (Extending the Engine Over Time)

> **Owning subtask:** DIV-47. **Parent:** DIV-36 (GTM Engine Architecture). **Brief:** Specsight
> GTM and Market Research Version2.
>
> This section documents how to **extend the engine without rebuilding it**: step-by-step
> extension procedures for each of the four content layers, the propagation rules that govern how
> a change in one layer cascades downstream, the validation criteria new content must meet, and
> the research sources and process to follow. It builds on the layer contracts
> ([§1](01-six-layer-interfaces.md)), the loop's refinement procedure
> ([§2](02-commercial-learning-loop.md)), and the sibling consumption map
> ([§3](03-sibling-gtm-mapping-and-workstreams.md)).

---

## The methodology the engine was built with

The nine research documents were not a linear march to a solution — they were a series of
increasingly constrained research questions, each following the same pattern. That pattern *is*
the extension methodology:

```text
1  IDENTIFY GAP   Start from a hypothesis or gap in the current engine
                  (e.g. "does this workflow stage actually exist in industry?")
2  RESEARCH       Study industry practice — company handbooks, practitioner discussions,
                  thought-leader publications — for that specific gap
3  VALIDATE       Check findings against existing engine content and the validation criteria
4  INTEGRATE      Add to / update the relevant layer, preserving its id scheme
5  PROPAGATE      Cascade the change to downstream layers per the propagation rules
```

Every extension — whether triggered by the Layer 6 loop (a customer interaction, per §2) or by
proactive research (a new gap someone spots) — runs this loop. The id schemes (`CN-NN`, `FM-NN`,
`CAP-NN`, `BT-NN`) are append-only: ids are assigned once in reading order and never reused, so
existing cross-references never break when the engine grows.

---

## 1. Extension procedures per content layer

The four *content* layers (Layers 1–4) are extensible. Layer 5 (GTM Assets) regenerates from
them and Layer 6 (the loop) drives the changes; neither has a separate content id scheme to
extend.

### Layer 1 — add a workflow stage / concept node

1. **Identify** the candidate: a stage, artifact, role, or company-specific implementation a
   prospect described (via §2) or that appears repeatedly in research but is missing from
   `CN-01…CN-09`.
2. **Research** it against the source basis — is it recognized in mature practitioner vocabulary,
   or is it internal terminology? Confirm with the Layer 1 evidence standard (multiple
   independent organizations / practitioner sources).
3. **Validate** it does not duplicate an existing `CN` node at a different altitude (cf. the
   FM-08 / FM-18 "same phenomenon, two altitudes" precedent) and that it has real edges to
   existing nodes.
4. **Integrate** as the next id (`CN-10`, …) in Section 2 of the Layer 1 hub, with its stages,
   activities, artifacts, roles, decision points, and a company-implementation row.
5. **Propagate** — a new `CN` node triggers the full cascade (see §2 rules below): check Layer 2
   for new failure modes on the node, then Layer 3, Layer 4, Layer 5.

### Layer 2 — add a failure mode

1. **Identify** a recurring breakdown reported in practitioner language (from the loop or new
   research) not covered by `FM-01…FM-25`.
2. **Research** the practitioner evidence: where do practitioners complain about it, in what
   words, with what workaround? Capture the **exact** language — Layer 2's value is speaking the
   language of pain.
3. **Validate** against Framework-5 (below): it must be *observable operational pain*, not an
   expert best-practice restated as a problem. Assign an underserved-by-tools rating with
   evidence.
4. **Integrate** as the next id (`FM-26`, …) conforming to the `FailureModeEntry` schema, anchored
   to the `CN` node(s) it sits on, in the correct workflow-stage section.
5. **Propagate** — check Layer 3 for a new/extended `CAP` mapping, then Layer 4 for a new `BT`.

### Layer 3 — add / extend a capability mapping

1. **Identify** a failure mode (new or existing) whose missing capability is not yet mapped, or a
   `CAP` whose Specsight capability / customer value needs revision (e.g. `CAP-07` promoted from
   hypothesis after loop validation).
2. **Research** the full six-link chain: *failure mode → missing capability → current workaround
   → existing alternatives → Specsight capability → customer value.* Use only the research's
   validated value vocabulary; mark any unestablished Specsight capability a hypothesis /
   roadmap candidate rather than inventing it.
3. **Validate** the mapping against customer interactions (§2 Layer 3 feedback path) — does the
   capability claim land in demos? Confirm the `FM→CAP` partition stays total and non-overlapping
   (every `FM` maps to exactly one `CAP`).
4. **Integrate** — attach the new `FM` to an existing `CAP`, or mint the next capability id
   (`CAP-08`, …) if it is a genuinely new capability area; update the `CapabilityGapAssessment`
   category.
5. **Propagate** — check Layer 4 for a new/refined `BT`, and flag Layer 5 (roadmap input +
   positioning) that the gap assessment changed.

### Layer 4 — add / refine a buying trigger

1. **Identify** an observable workflow event that reliably precedes buying but is not in
   `BT-01…BT-05`, or a detection candidate / fit hypothesis the loop has confirmed or falsified.
2. **Research** the full extended Framework-4 chain: *operational event → workflow breakdown
   (`FM-NN`) → recognition of capability gap → buying trigger → evaluation criteria → decision
   process*, plus an externally observable detection signal.
3. **Validate** the trigger against customer confirmation (§2 Layer 4 feedback path — the loop's
   first-priority job) before promoting a detection candidate to "validated"; retire candidates
   that mis-fire.
4. **Integrate** as the next id (`BT-06`, …) anchored to its `FM-NN` sources, with detection
   method, company-level signals, evaluation criteria, and friction/fit assessment marked with
   the correct detection-status convention.
5. **Propagate** — check Layer 5 for a new/updated GTM asset (ICP weighting, outreach sequence,
   assessment question) driven by the trigger change.

---

## 2. Propagation rules

When any layer is updated, the downstream layers that must be checked are fixed by the pipeline
direction. A change never propagates upstream on its own — but the Layer 6 loop can *originate* a
change at any layer, after which forward propagation applies from that layer.

| A change at… | …forces a check for a new/updated entry at… |
| --- | --- |
| **Layer 1** — new workflow stage / `CN` node | Layer 2 (`FM`) → Layer 3 (`CAP`) → Layer 4 (`BT`) → Layer 5 (asset) — the **full cascade** |
| **Layer 2** — new / refined `FM` | Layer 3 (`CAP`) → Layer 4 (`BT`) → Layer 5 (asset) |
| **Layer 3** — new / refined `CAP` | Layer 4 (`BT`) → Layer 5 (asset, incl. roadmap input) |
| **Layer 4** — new / refined `BT` | Layer 5 (asset: ICP / outreach / PLG) |
| **Layer 5** — refined asset | *(terminus of forward flow)* → generates Layer 6 interactions |
| **Layer 6** — validated interaction | Originates a change at L1–L5, then forward propagation applies from that layer |

```text
  L1 ──► L2 ──► L3 ──► L4 ──► L5        (forward propagation; each arrow = "check for new/updated entry")
   ▲                            │
   └──────────── L6 ◄───────────┘        (loop can inject a change at any layer; then propagate forward)
```

A propagation check has three outcomes: **no change** (the downstream layer already covers it —
record the check and stop), **update** (an existing downstream entry needs revision), or **add**
(a new downstream entry, minting the next id). Recording "no change" checks matters — it is how
the engine proves it was maintained, not just grown.

---

## 3. Research validation criteria

New content must clear the same bar the engine was built to, before it enters any layer. These
criteria are what keep the engine credible as it grows:

- **Framework-5 separation (the primary gate).** Separate *expert best practices* from
  *observable operational pain*. New failure modes and triggers must be grounded in where
  practitioners actually complain — observable workflow behavior — **not** in a best-practice
  framework restated as a problem. "Teams should write clearer acceptance criteria" is a best
  practice; "developers interpret the same story differently and rework it mid-sprint"
  (`FM-12`) is observable pain. Only the latter qualifies.
- **Practitioner language.** Symptoms, evidence, and workarounds must be captured in the exact
  vocabulary practitioners use (the language the loop hears in prospect conversations), not
  translated into Specsight or abstract-PM terms. This is what makes downstream Layer 5 assets
  resonate.
- **Observable behavior over theory.** A candidate must correspond to something externally
  observable — a workflow event, an artifact, a company signal — not an internal abstraction.
  Layer 4 enforces this by marking anything not yet observed a **detection candidate / fit
  hypothesis** rather than a validated fact.
- **Evidence grounding.** Layer 1 stages need multiple independent organizations / practitioner
  sources; Layer 3 Specsight capabilities use only the research's validated value vocabulary, with
  anything unestablished marked a hypothesis. Nothing is invented to fill a gap — gaps are marked.
- **Id-scheme discipline.** New content takes the next id in sequence and never reuses or
  renumbers an existing id, so all cross-layer references (`CN`/`FM`/`CAP`/`BT`) remain stable.

---

## 4. Research sources & process

The sources to consult, mirroring how the engine was built:

- **Company engineering handbooks & public operating models** — Microsoft, GitLab, Atlassian,
  Stripe, GitHub, Shopify, Amazon and comparable public engineering documentation (grounds Layer
  1 stages and Layer 3 alternatives).
- **Practitioner discussions** — where practitioners describe real sprint failures, drift,
  skipped refinement, unclear acceptance criteria (the richest source for Layer 2 failure modes
  and Layer 4 triggers; the brief's methodological shift toward practitioner corpus over
  frameworks).
- **Thought-leader publications** — the curated research corpus (e.g. Cohn, Pichler, Overeem,
  Wolpers, Rachitsky, Doshi and peers), each representing one facet of the operating model —
  used to triangulate, not as sole evidence.
- **Customer interactions (via Layer 6)** — the highest-value ongoing source: every prospect
  conversation, demo, assessment, and product-feedback event is primary research that the §2 loop
  routes into these same extension procedures.

The process is the five-step loop at the top of this section — **identify gap → research →
validate → integrate → propagate** — run per extension. It is deliberately identical to both the
methodology that built the engine and the Layer 6 refinement trigger mechanism (§2 §3), so the
engine is maintained and extended by *one* repeatable procedure rather than a separate build
process. That single-procedure property is what lets the engine grow with new workflow stages,
failure modes, capabilities, and triggers **without ever rebuilding it from scratch.**
