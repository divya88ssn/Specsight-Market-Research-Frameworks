# Layer 3 · Section 3 — Capability Gap Assessment (Roadmap Input)

> **Role in the Capability Graph:** Closes Layer 3 by assessing each Specsight capability
> target from the complete `CapabilityMappingChain` ([§2](02-specsight-capability-and-customer-value.md))
> against what Specsight delivers today, using Document 2's three maturity levels as the
> framework. The output — the `CapabilityGapAssessment` — is the **roadmap input** identified
> in the parent task (DIV-34) scope.
>
> **Owning subtask:** DIV-57.
> **Consumes:** `CAP-01…CAP-07` with links 5–6 (§2) and Document 2's three maturity levels.
> **Out of scope here:** prioritizing roadmap items / building a prioritized roadmap (sibling
> brief task "Product roadmap can be informed by validated capability gaps"); defining
> capability targets or value (§2); buying triggers (Layer 4).

---

## 1. The assessment framework — Document 2's three maturity levels

Document 2 positions Specsight against a three-level maturity model. **Level 2 (Delivery) is
Specsight's current sweet spot;** Level 1 is not the current focus and Level 3 is the natural
expansion.

| Level | Name | Status (Document 2) | Current solutions in market | PM question |
| --- | --- | --- | --- | --- |
| **Level 1** | Planning | "Not the primary focus today." | PRDs, Jira, Figma | "What are we trying to build?" |
| **Level 2** | Delivery | **"Current sweet spot."** | Engineers, demos, GitHub PRs, release notes | "What did engineering actually build?" |
| **Level 3** | Operations | "Natural expansion." | Support, analytics, logs, incident reviews | "What is customers' current experience, and why?" |

Capabilities that fall outside all three levels represent **new capability areas**.

**Gap categories** (mutually exclusive, collectively exhaustive):

- **`current capability`** — Specsight already addresses it (squarely Level 2).
- **`partial`** — partially addressed; a Level 1→2 or Level 2→3 transition where part exists
  and part is missing.
- **`natural expansion`** — not currently addressed, but a natural extension of the current
  Level 2 → Level 3 trajectory.
- **`new capability area`** — not addressed and beyond the current trajectory; requires
  strategic capability development.

---

## 2. The `CapabilityGapAssessment` (per `CAP` node)

| `CAP` · Missing capability | Current Specsight level | Gap description (what exists vs what's missing) | Specsight capability target (link 5) | Customer value (link 6) | Gap category |
| --- | --- | --- | --- | --- | --- |
| **CAP-03** · Automatic comparison of intent vs implemented behavior | **Level 2 (Delivery)** | Specsight already derives an implementation-aware behavioral summary from the repository — this *is* the Level 2 "what did engineering actually build?" question. Little missing at the core. | Implementation-aware behavioral summary from the repository (what changed, impacted workflows, edge cases, deviations) | PM reviews behavior instead of reverse-engineering; engineering translates less code into business language | **current capability** |
| **CAP-01** · Persistent representation of customer intent | **Level 2 (Delivery)**, partial into Level 1 | The behavioral model derived from the repository exists (Level 2); persistently representing and continuously linking *customer intent from requirements* (Level 1 Planning — "not the primary focus today") is the partial piece. | Persistent behavioral model from requirements, continuously linked to implementation | Everyone starts from the same behavioral understanding; fewer clarification meetings and less interpretation drift | **partial** |
| **CAP-02** · Continuously maintained shared understanding during execution | **Level 2 (Delivery)** | Behavioral summaries at points in the build exist (Level 2); continuously *maintaining* shared understanding through the execution middle (the refinement boundary gap) is the differentiated but not-yet-complete piece. **Highest-value near-term target** — Layer 1 §5 names this the frontier where Specsight is most differentiated. | Continuously link the behavioral model to implementation as work proceeds | Intent stays aligned through execution; fewer blocked stories, less rework, fewer emergency meetings | **partial** |
| **CAP-04** · Shared behavioral understanding across Product, QA & Engineering | **Level 2 (Delivery)**, partial into Level 3 | A behavioral view usable by Product and Engineering exists (Level 2); making it a single shared view across QA, **Support, and Leadership** reaches toward Level 3 Operations audiences. | One behavioral view accessible to Product, QA, Support, and Leadership | Three roles verify against one understanding; QA and intent checks align; ownership becomes legible | **partial** |
| **CAP-05** · Traceable behavioral validation (AC → validated behaviors) | **Level 2 → Level 3** | Comparison of build vs intent exists (Level 2); *tracing* validated behaviors back to AC and customer workflows and surfacing validated/partial/unverified with assembled evidence is a release-readiness capability at the Level 2→3 boundary — beyond the current sweet spot but on-trajectory. | Trace validated behaviors to AC and customer workflows; surface validated/partial/unverified | Go/No-Go becomes evidence-based; confidence the right behaviors — not just tests — were validated | **natural expansion** |
| **CAP-06** · Continuous traceability intent → implementation → validation → customer outcomes | **Level 3 (Operations)** | Not the current focus; Level 3 Operations ("what is customers' current experience, and why?") is Document 2's named "natural expansion." Requires connecting production behavior/customer observations back to implementation and intent. | Connect production behavior to implemented features and original intent; connect customer observations to behavioral/implementation history | Faster understanding of customer impact; better prioritization; less dependence on Engineering per investigation | **natural expansion** |
| **CAP-07** · Operational clarification-vs-requirement-evolution boundary | **none** (outside Levels 1–3) | Not addressed and beyond the behavioral-model trajectory. The decision/governance capability (clarification vs requirement evolution, loop separation, locating a team on the Scrum↔Product-led spectrum) is not established in the research — a `Hypothesis / roadmap candidate` (§2.8). | *Hypothesis:* flag when a change alters intended behavior (evolution) vs clarifies it; decision/governance not established | *Hypothesis:* distinguish continuous alignment from scope creep against a shared record | **new capability area** |

---

## 3. Roadmap-input synthesis — trajectory vs strategic investment

The key roadmap signal the parent task asks for: **which capability gaps are close to delivery
vs. which require strategic investment.**

```text
  CLOSE TO DELIVERY (current Level 2 trajectory)          REQUIRES INVESTMENT (Level 3 / new)
  ═══════════════════════════════════════════           ═══════════════════════════════════════

  current capability   →  CAP-03  (ready now)             natural expansion  →  CAP-05, CAP-06
  partial (Level 2)    →  CAP-01, CAP-02, CAP-04           new capability area →  CAP-07
                            ▲ CAP-02 = highest-value                              ▲ hypothesis /
                              near-term target (frontier)                          roadmap candidate
```

- **Address now — 1 capability.** `CAP-03` (automatic comparison of intent vs implemented
  behavior) is squarely Specsight's Level 2 sweet spot: deliverable today and the anchor of
  the current value story.
- **Close to delivery, partial — 3 capabilities.** `CAP-01`, `CAP-02`, `CAP-04` are Level 2
  with a missing edge (requirements-intent linkage; continuous execution-middle maintenance;
  multi-role/Support-Leadership reach). **`CAP-02` is the highest-value near-term target** —
  Layer 1 §5 names the refinement boundary gap as where Specsight is most differentiated and
  where the underserved failure modes (FM-14 anchor) concentrate.
- **Natural expansion — 2 capabilities.** `CAP-05` (traceable behavioral validation at release
  readiness) and `CAP-06` (production→intent traceability) are the Level 2→3 → Level 3
  trajectory Document 2 already anticipates; on-roadmap but requiring development.
- **New capability area — 1 capability.** `CAP-07` (clarification/evolution boundary and loop
  separation) is outside the behavioral-model trajectory and unvalidated as a Specsight
  capability — strategic investment only, flagged as a hypothesis, not committed scope.

This distribution is the roadmap input: it says **what Specsight can lead with today (CAP-03),
what is one increment away (CAP-01/02/04, CAP-02 first), what is the natural next horizon
(CAP-05/06), and what would be a new bet (CAP-07)** — without prioritizing them (that is the
sibling brief's roadmap task).

---

## 4. Coverage check (DIV-57 acceptance)

- **Every capability target assessed.** CAP-01…CAP-07 (and thereby all 25 failure modes via
  §1's partition) each have a gap-assessment row.
- **Maturity level assigned per the framework.** Each row cites Level 1 Planning / Level 2
  Delivery / Level 3 Operations / none, consistent with Document 2 (Level 2 = Specsight's
  current sweet spot = the Delivery stage — CAP-03).
- **Gap description present.** Each row states what exists vs what's missing.
- **Gap categories are MECE.** Exactly one of `current capability` / `partial` /
  `natural expansion` / `new capability area` per row; counts: 1 / 3 / 2 / 1 = 7.
- **The four persona capabilities are assessed, not dropped.** CAP-01 (A), CAP-03 (B),
  CAP-05 (C), CAP-06 (D) all appear.
- **Roadmap signal is clear.** §3 separates close-to-delivery (CAP-03 now; CAP-01/02/04
  partial) from requires-investment (CAP-05/06 expansion; CAP-07 new area).

---

*Previous: [Section 2 — Specsight Capability & Customer Value (links 5–6)](02-specsight-capability-and-customer-value.md) · Back to [Layer 3 hub](../layer-3-capability-graph.md)*
