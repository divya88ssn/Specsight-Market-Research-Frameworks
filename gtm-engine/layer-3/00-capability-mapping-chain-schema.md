# Layer 3 · Section 0 — Capability Mapping Chain Schema & Cross-Referencing Contract

> **Role in the Capability Graph:** This section defines the **contract** every capability
> mapping in Layer 3 conforms to. It is the schema header of the whole layer — §1 fills
> links 1–4, §2 fills links 5–6, and §3 assesses the result against Specsight's current
> maturity. Read this first; everything else is instances of this template.
>
> **Owning subtask:** DIV-43.
> **Consumes:** Layer 2 — Failure Mode Library ([`../layer-2-failure-mode-library.md`](../layer-2-failure-mode-library.md), `FM-01…FM-25`)
> and Layer 1 — Industrial Knowledge Graph ([`../layer-1-industrial-knowledge-graph.md`](../layer-1-industrial-knowledge-graph.md), `CN-01…CN-09`).
> **Source structure:** Frameworks 2 & 3 from Document 2 (the persona/JTBD keystone) narrated
> in the brief (`.hamster/divya-gunasekarans-team/briefs/specsight-gtm-and-market-research-version2/brief.md`).
> **Out of scope here:** populating the chain with failure-mode data (§1, DIV-49), naming
> Specsight capabilities/customer value (§2, DIV-54), assessing the current-vs-missing gap
> (§3, DIV-57), and deriving buying triggers (Layer 4, DIV-35).

---

## 1. What a capability mapping is

Layer 3 connects each validated **failure mode** (Layer 2) to the **capability gap** it
represents, the workaround and alternatives teams use today, the **Specsight capability** that
addresses the gap, and the **customer value** that capability delivers. This is the brief's
Layer 3 chain:

```text
Failure Mode → Missing Capability → Current Workaround → Existing Alternatives
            → Specsight Capability → Customer Value
```

The chain exists so Specsight can articulate **exactly which capability gap it fills and why
that gap matters to the prospect** — turning pain research (Layer 2) into product positioning
without re-interpretation by downstream GTM tasks.

---

## 2. The `CapabilityMappingChain` contract (the six links)

Every capability node in §1–§2 populates every field below. This is the canonical
`CapabilityMappingChain` contract referenced by all downstream subtasks and sibling tasks.

| # | Link / field | Type | What it captures | Filled by |
| --- | --- | --- | --- | --- |
| — | **`capabilityId`** | string (`CAP-NN`) | Stable id of the capability node (see §4). **Primary key of Layer 3.** | §1 |
| — | **`failureModes`** | string[] (`FM-NN`) | The Layer 2 failure mode id(s) that manifest this capability gap. **Cross-reference key into Layer 2.** | §1 |
| 1 | **`failureMode`** | string | The validated failure mode(s), in Layer 2's practitioner terminology. | §1 |
| 2 | **`missingCapability`** | string | The gap framed as a *capability*, not a problem or a feature (Framework 2). E.g., "Persistent representation of customer intent", **not** "Poor requirements". | §1 |
| 3 | **`currentWorkaround`** | string | What teams do today to cope — from Layer 2's `current_workarounds` and Document 2's "Current Process" language. | §1 |
| 4 | **`existingAlternatives`** | string | The specific tools/ceremonies used instead of a dedicated capability (e.g., "Jira, Figma, demos, GitHub PRs, analytics"). | §1 |
| 5 | **`specsightCapability`** | string | What Specsight does (or could do) to address the gap, in validated value language (Framework 3) — never generic feature-list language. | §2 |
| 6 | **`customerValue`** | string | What the prospect gains — the terminal link, using Document 2's "Value Created" pattern. | §2 |
| — | **`workflowStage`** | enum | The Layer 1 workflow stage (§5) the gap attaches to — the Layer 2 `workflow_stage` of the member failure modes. | §1 |
| — | **`productLoop`** | enum | `Discovery/Refinement` · `Verification/Acceptance` · `Cross-loop (lifecycle-spanning)` (§5). | §1 |
| — | **`specsightConfidence`** | enum | `Validated` (established by Document 2) or `Hypothesis / roadmap candidate` (research does not establish concrete product detail — see §6). | §2 |

> **Scope discipline:** links 1–4 (§1) never name a Specsight capability; links 5–6 (§2) never
> re-catalogue a failure mode (Layer 2 owns that) or derive a buying trigger (Layer 4 owns
> that). The gap assessment (§3) reads link 5 and the maturity levels; it does not add links.

---

## 3. How the chain maps to the research frameworks (Document 2)

The six links are a faithful extension of the two Document 2 frameworks that Layer 3
operationalizes, plus the persona document's four-column mapping columns.

| Chain links | Research framework (brief citation) |
| --- | --- |
| **Links 1 → 2** (failure mode → missing capability) | **Framework 2 — Failure Mode → Missing Capability.** "Instead of listing problems, it translated every failure mode into a capability that teams are missing. Not *Poor requirements* but *Missing continuous alignment capability*." (Document 2) |
| **Links 2 → 5** (missing capability → Specsight capability) | **Framework 3 — Missing Capability → Specsight Capability.** "Workflow problem ↓ Capability gap ↓ Specsight capability ↓ Customer value." (Document 2) |
| **Links 3 → 4** (workaround → alternatives) | The persona document's "Current Process" / "Current Way" columns and the three maturity levels' tool inventory. |
| **Link 6** (customer value) | The persona document's "Value Created" / "Specsight Value" columns — the terminal link Framework 3 points at. |

Framework 2 is applied at Layer 2's altitude (a validated failure mode) and lifted to a
capability statement here; Framework 3 completes the arc to Specsight and to value.

---

## 4. The `CAP-NN` id scheme (and its relationship to `FM-NN`)

Layer 3 uses **two coexisting keys**, honoring both the brief's mandate (reference failure
modes by their `FM-NN` id) and this subtask's mandate (give each mapping a stable id):

- **`FM-NN`** (Layer 2) is the **entry key** into the failure-mode-to-capability map (§1): every
  one of the 25 failure modes appears as a row, referencing the capability it rolls up to.
- **`CAP-NN`** is the **primary key of the capability node itself** (§2, §3): a *distinct
  missing capability*. One `CAP` gathers one or more `FM` ids that manifest the same gap.

```text
   FM-NN (25 failure modes, Layer 2)        CAP-NN (distinct missing capabilities, Layer 3)
   ────────────────────────────────         ──────────────────────────────────────────────
   FM-01, FM-12, FM-15, FM-22   ───────────►  CAP-0x  (one missing capability)
   FM-08, FM-18, FM-06, ...     ───────────►  CAP-0y  (one missing capability)
        (many-to-one: several failure modes can share one capability gap)
```

**Rules:** `CAP-NN` ids are assigned once, in reading order, and never reused. Every `FM-NN`
maps to exactly one `CAP-NN` (a total, non-overlapping partition of the 25 failure modes).
The **registry** of `CAP` ids, their member `FM` ids, and the partition rationale is
established in [§1](01-failure-mode-to-capability-map.md) — assigning failure modes to
capabilities is *populating* the chain (DIV-49), not defining its schema.

> **Consolidation rule (from Layer 2):** FM-08 (Implementation / Continuous Collaboration
> stage) and FM-18 (cross-stage transition) describe the same phenomenon — implementation
> drift — at two altitudes. Per the Layer 2 hub's cross-stage note, Layer 3 treats them as
> **one capability gap** (they share a `CAP`), not two.

---

## 5. `workflowStage` and `productLoop` enumerations

**`workflowStage`** values are drawn verbatim from the Layer 2 / Layer 1 stage set (so a
chain cross-references the Failure Mode Library and Industrial Knowledge Graph directly):
`Requirements / Backlog Refinement` · `Acceptance Criteria / Definition of Done` ·
`Implementation / Continuous Collaboration` · `Sprint Review` · `UAT / Release Readiness` ·
`Production Review` · `Discovery / Refinement Loop` · `Verification / Acceptance Loop`.
Document 2's four-stage maturity lifecycle (Requirements → Sprint Review → UAT/Release
Readiness → Production) is a subset of these and is the lifecycle the §3 gap assessment scores
against.

**`productLoop`** classifies which loop's question the gap most directly compromises:

| Value | Meaning |
| --- | --- |
| `Discovery/Refinement` | Compromises "What should we build?" — shared understanding before/into implementation. |
| `Verification/Acceptance` | Compromises "Did we build what we agreed?" — verification against intent. |
| `Cross-loop (lifecycle-spanning)` | Document 2's drift taxonomy / Context Reconstruction Tax entries that span the whole lifecycle (esp. Production feedback into Requirements). |

> **Documented extension:** the DIV-43 contract enumerated `productLoop` as the two loops
> only. Document 2 explicitly frames several failure modes (the drift taxonomy and Context
> Reconstruction Tax, FM-18–FM-25) as *cross-stage / lifecycle-spanning*; forcing them into a
> single loop would misrepresent the research. A third value, `Cross-loop
> (lifecycle-spanning)`, is added to preserve the contract's *intent* (loop classification)
> while representing lifecycle-spanning modes faithfully. The assignment per failure mode is
> made in [§1](01-failure-mode-to-capability-map.md).

---

## 6. `specsightConfidence` — validated vs hypothesis

The brief instructs: *where the research does not establish a concrete Specsight capability,
mark it as a hypothesis / roadmap candidate rather than inventing product detail.* Every
capability node therefore carries a `specsightConfidence` marker:

- **`Validated`** — the Specsight capability and its value are established in Document 2 (the
  persona document's "What Specsight Could Do" / "Value Created" columns, or the trigger
  table's "Specsight Value" column). These use the research's validated vocabulary:
  *persistent behavioral model, implementation-aware behavioral summary, traceable behavioral
  validation, behavioral traceability, persistent product knowledge, a single behavioral
  view.*
- **`Hypothesis / roadmap candidate`** — the missing capability is validated (it comes from a
  Layer 2 failure mode) but the research does **not** establish a concrete Specsight capability
  that addresses it. §2 frames what Specsight *could* do in the same value language and §3
  categorizes it as a new capability area; no product detail is invented.

---

## 7. Cross-referencing structure

Each capability node is cross-referenced in four directions so it is consumable without
re-interpretation:

| Direction | Reference | Via |
| --- | --- | --- |
| **↑ to Layer 1** | `workflowStage` + the concept nodes (`CN-01…CN-09`) of the member failure modes | the Layer 2 entry's `concept_nodes`; cite Layer 1 by file path + `CN` id |
| **↑ to Layer 2** | `failureModes` (`FM-NN[]`) | the `FM-NN` primary key; every failure mode's symptoms/evidence/workaround stay owned by Layer 2 |
| **↓ to Layer 4 (Buying Trigger Graph, DIV-35)** | reads links 1–2 (failure mode + missing capability) to derive triggers | `CAP-NN` and `FM-NN` ids |
| **↓ to Layer 5 (GTM Assets, sibling brief)** | reads links 5–6 (Specsight capability + customer value) for ICP scoring, assessment design, outreach, positioning | `CAP-NN` id |

> Layer 3 declares no buying-trigger field and no messaging copy. It stops at capability and
> value; Layer 4 and the GTM-asset tasks extend by `CAP-NN`/`FM-NN` id.

---

## 8. Worked example — the persona mapping extended to six links

The persona document already contains a validated four-column mapping (Trigger → Why It
Happens → Missing Capability → Specsight Value). The six-link chain **extends** it by inserting
`currentWorkaround` and `existingAlternatives` and adding the terminal `customerValue`. Using
the Sprint Review mapping the DIV-43 acceptance criteria name:

| Chain link | Value (worked example) |
| --- | --- |
| `capabilityId` | `CAP-03` *(illustrative; the registry is defined in §1)* |
| `failureModes` | `FM-23` (Context Reconstruction @ Sprint Review); shares the node with `FM-04`, `FM-06`, `FM-08`, `FM-18` |
| **1 · failureMode** | "Release meetings run long; the PM reconstructs what was built from demos, Jira, and engineering explanations." (persona trigger "Sprint Reviews are long") |
| **2 · missingCapability** | **Continuous understanding of implemented behavior** — automatic comparison of intent vs implemented behavior. *(Framework 2: a capability, not "better demos".)* |
| **3 · currentWorkaround** | "Watches demos and accepts work"; post-demo Q&A with engineering to reconstruct what changed; manually diffing implementation against requirements. (Document 2 "Current Process") |
| **4 · existingAlternatives** | Demos / screenshare, Jira, GitHub PRs, release notes, engineering walkthroughs. |
| **5 · specsightCapability** | "Behavioral summaries and workflow impact derived from the repository" — an implementation-aware behavioral summary that shows what changed, impacted workflows, edge cases, and differences from expected behavior. *(Framework 3; validated persona "Specsight Value".)* |
| **6 · customerValue** | "PM reviews behavior instead of reverse-engineering implementation; engineering spends less time translating code into business language." (persona "Value Created") |
| `workflowStage` | `Sprint Review` |
| `productLoop` | `Verification/Acceptance` |
| `specsightConfidence` | `Validated` |

The example traces cleanly through all six links using only Document 2 data, and the structure
generalizes to **every** failure mode in the Failure Mode Library — not just the six used in
the PLG assessment. §1 populates links 1–4 for all 25 `FM` ids; §2 completes links 5–6 for
every `CAP`.

---

*Next: [Section 1 — Failure-Mode-to-Capability Map (links 1–4)](01-failure-mode-to-capability-map.md) · Back to [Layer 3 hub](../layer-3-capability-graph.md)*
