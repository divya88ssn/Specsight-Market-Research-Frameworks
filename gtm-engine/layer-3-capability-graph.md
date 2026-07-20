# Layer 3 — Capability Graph (Failure Mode → Missing Capability → Specsight Capability → Customer Value)

> **This is the canonical Layer 3 document of the Specsight GTM engine.** It connects every
> validated failure mode to the capability gap it represents, the workaround and alternatives
> teams use today, the Specsight capability that fills the gap, and the customer value that
> capability delivers — then assesses the gap between Specsight's current capabilities and the
> validated missing capabilities as a roadmap input.
>
> **Owning parent task:** DIV-34. **Brief:** Specsight GTM and Market Research Version2.
> **Consumes:** Layer 2 — Failure Mode Library ([`layer-2-failure-mode-library.md`](layer-2-failure-mode-library.md), `FM-01…FM-25`)
> and Layer 1 — Industrial Knowledge Graph ([`layer-1-industrial-knowledge-graph.md`](layer-1-industrial-knowledge-graph.md), `CN-01…CN-09`).

---

## What Layer 3 is (and is not)

Layer 3 is the **Capability Graph**: the brief's Framework 2 and Framework 3 applied to every
failure mode in the library, expressed as a six-link chain —

```text
Failure Mode → Missing Capability → Current Workaround → Existing Alternatives
            → Specsight Capability → Customer Value
```

— so Specsight can articulate **exactly which capability gap it fills and why that gap matters
to the prospect.** Without this layer, Specsight knows where practitioners hurt (Layer 2) but
cannot connect that pain to a specific capability it provides.

Layer 3 is **not** a re-catalogue of failure modes (Layer 2, DIV-33, owns their symptoms,
evidence, and workarounds) and **not** a derivation of buying triggers (Layer 4, DIV-35). It
maps capabilities and stops. Its outward links are `FM-NN` ids (up to Layer 2), `CN` ids and
workflow stages (up to Layer 1), and `CAP-NN` ids (down to Layer 4 and the GTM-asset tasks).

---

## Document structure

Layer 3 is composed of four sections, each a self-contained file. Section 0 defines the
schema; §1–§2 populate the six-link chain; §3 assesses the gap as a roadmap input.

| # | Section | File | Owning subtask | What it provides |
| --- | --- | --- | --- | --- |
| 0 | Capability Mapping Chain Schema & Cross-Referencing Contract | [`layer-3/00-capability-mapping-chain-schema.md`](layer-3/00-capability-mapping-chain-schema.md) | DIV-43 | The `CapabilityMappingChain` contract; the `CAP-NN` id scheme; Framework 2/3 mapping; the worked example |
| 1 | Failure-Mode-to-Capability Map (links 1–4) | [`layer-3/01-failure-mode-to-capability-map.md`](layer-3/01-failure-mode-to-capability-map.md) | DIV-49 | The `CAP-01…CAP-07` registry; failure mode → missing capability → workaround → alternatives for all 25 `FM` ids |
| 2 | Specsight Capability & Customer Value (links 5–6) | [`layer-3/02-specsight-capability-and-customer-value.md`](layer-3/02-specsight-capability-and-customer-value.md) | DIV-54 | Specsight capability + customer value per `CAP`; the complete six-link chain |
| 3 | Capability Gap Assessment (roadmap input) | [`layer-3/03-capability-gap-assessment.md`](layer-3/03-capability-gap-assessment.md) | DIV-57 | `CapabilityGapAssessment` — current vs missing against the three maturity levels |

---

## The `CAP-NN` capability id scheme

The 25 failure modes collapse into **seven distinct missing capabilities**, each with a stable
`CAP-NN` id (the primary key of Layer 3). Every `FM-NN` maps to exactly one `CAP` (a total,
non-overlapping partition); many failure modes can share one capability gap. The four
capabilities Document 2 already validated (persona A/B/C/D) are `CAP-01/03/05/06`; `CAP-02`,
`CAP-04`, and `CAP-07` extend them to cover all 25 failure modes.

| `CAP` | Missing capability | Member `FM` ids | Specsight confidence | Gap category (§3) |
| --- | --- | --- | --- | --- |
| **CAP-01** | Persistent representation of customer intent | FM-01, FM-12, FM-15, FM-22 | Validated (persona A) | partial |
| **CAP-02** | Continuously maintained shared understanding during execution | FM-09, FM-10, FM-11, FM-14 | Validated | partial *(highest-value near-term)* |
| **CAP-03** | Automatic comparison of intent vs implemented behavior | FM-04, FM-06, FM-08, FM-18, FM-23 | Validated (persona B) | **current capability** |
| **CAP-04** | Shared behavioral understanding across Product, QA & Engineering | FM-05, FM-07 | Validated | partial |
| **CAP-05** | Traceable behavioral validation (AC → validated behaviors) | FM-02, FM-03, FM-19, FM-20, FM-24 | Validated (persona C) | natural expansion |
| **CAP-06** | Continuous traceability intent → implementation → validation → customer outcomes | FM-21, FM-25 | Validated (persona D) | natural expansion |
| **CAP-07** | Operational clarification-vs-requirement-evolution boundary | FM-13, FM-16, FM-17 | Hypothesis / roadmap candidate | new capability area |

> **Consolidation note (from Layer 2):** FM-08 and FM-18 describe implementation drift at two
> altitudes and are treated here as **one** capability gap (`CAP-03`), per the Layer 2 hub's
> cross-stage note.

---

## Coverage at a glance

- **All 25 failure modes** (`FM-01…FM-25`) have a complete six-link capability mapping.
- **Framework 2** (links 1–2) frames every gap as a *capability*, not a problem or a feature.
- **Framework 3** (links 2–5) completes each to a Specsight capability and customer value in
  the research's validated value vocabulary; one node (`CAP-07`) is flagged a hypothesis
  because the research does not establish a concrete Specsight capability for it.
- **Roadmap input:** 1 capability deliverable now (`CAP-03`), 3 partial and close to delivery
  (`CAP-01/02/04`, `CAP-02` first), 2 natural expansions (`CAP-05/06`), 1 new capability area
  (`CAP-07`).

---

## Cross-reference contract for downstream layers

| Downstream layer | Parent | How it builds on Layer 3 |
| --- | --- | --- |
| **Layer 4 — Buying Trigger Graph** | DIV-35 | Reads links 1–2 (failure mode + missing capability) per `CAP-NN`/`FM-NN` to derive buying triggers; anchors most on the underserved set (esp. FM-14 in `CAP-02` and FM-22…FM-25). |
| **Layer 5 — GTM Assets** | sibling brief | Reads links 5–6 (Specsight capability + customer value) per `CAP-NN` for ICP scoring, assessment design, outreach, and positioning — without re-interpreting the research. |
| **Product roadmap** | sibling brief | Consumes the §3 `CapabilityGapAssessment` as its input (this layer produces the input, not the prioritized roadmap). |

> **Scope discipline observed in Layer 3:** this layer maps capabilities and assesses the
> current-vs-missing gap. It deliberately does **not** re-catalogue failure modes (DIV-33),
> derive buying triggers (DIV-35), prioritize the roadmap (sibling brief), or write
> messaging/positioning copy (sibling brief). Where those are touched, it is only to name a
> downstream connection.

---

## Source basis

All content derives from the nine research documents narrated in the brief
(`.hamster/divya-gunasekarans-team/briefs/specsight-gtm-and-market-research-version2/brief.md`),
with **Document 2 (the persona/JTBD/ICP keystone)** as the primary source for Frameworks 2 & 3,
the four validated capability mappings, the trigger-table "Specsight Value" language, and the
three maturity levels. Missing capabilities are sourced from the Layer 2 failure modes; Specsight
capabilities use only the research's validated value vocabulary, and any capability the research
does not establish is marked a hypothesis / roadmap candidate rather than invented.

---

*Sections: [§0 Schema](layer-3/00-capability-mapping-chain-schema.md) · [§1 Failure-mode-to-capability map](layer-3/01-failure-mode-to-capability-map.md) · [§2 Specsight capability & value](layer-3/02-specsight-capability-and-customer-value.md) · [§3 Gap assessment](layer-3/03-capability-gap-assessment.md)*
