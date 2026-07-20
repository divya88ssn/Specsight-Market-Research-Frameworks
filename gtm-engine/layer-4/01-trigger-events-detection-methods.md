# Layer 4 · Section 1 — Buying Trigger Events & Detection Methods

> **Role in the graph:** This is the **foundational section** of the Buying Trigger Graph. It
> enumerates every buying trigger, traces each through the full Framework-4 chain (Operational
> Event → Workflow Breakdown → Recognition of Capability Gap → Buying Trigger), assigns each a
> stable `BT-NN` id, and defines a concrete, externally observable **detection method** for
> each. Sections 2–4 (failure-mode signals, evaluation criteria, friction/fit) all reference
> the `BT-NN` ids defined here.
>
> **Owning subtask:** DIV-39. **Parent:** DIV-35.
> **Consumes:** Layer 1 — Industrial Knowledge Graph (concept nodes `CN-01…CN-09`, stages, the
> refinement boundary gap) and Layer 2 — Failure Mode Library (`FM-01…FM-25`).
> **Out of scope here:** failure-mode→company-signal mapping (§2), evaluation criteria &
> decision process (§3), friction detection & Specsight-fit (§4), cataloguing failure modes
> (Layer 2), mapping capabilities (Layer 3).

---

## 1. The trigger chain (Framework 4, extended)

Document 2's **Framework 4** reframed buying intent away from demographics and toward workflow
events. The parent task (DIV-35) extends that chain with the two downstream links the brief's
Layer 4 description adds (`… → Evaluation Criteria → Decision Process`):

```text
   Operational Event ─► Workflow Breakdown ─► Recognition of ─► Buying Trigger ─► Evaluation ─► Decision
   (observable in the    (a Layer 2 FM-NN     Capability Gap    (search /         Criteria      Process
    org, externally       fires during         ("we need a       evaluation        (§3)          (§3)
    detectable)           execution)           way to …")        behaviour)
```

- The **Operational Event → Workflow Breakdown → Recognition → Buying Trigger** links are
  defined per trigger in this section.
- Each **Workflow Breakdown** is anchored to one or more Layer 2 failure modes by `FM-NN` id —
  a trigger is credible only if it traces back to a catalogued workflow breakdown.
- **Evaluation Criteria** and **Decision Process** are documented in [§3](03-evaluation-criteria-decision-process.md).

> **The reframing (Framework 4).** Buying intent does **not** come from company size, budget,
> industry, or job title. It comes from an *operational event* that produces a *workflow
> breakdown* the prospect *recognizes as a capability gap*. This section makes that chain
> operational and, crucially, **externally detectable** — a GTM team can observe the trigger
> firing without access to the prospect's internal tools.

---

## 2. The `BT-NN` buying-trigger id scheme

Every buying trigger has a **stable `BT-NN` id** (the primary cross-reference key for §2–§4 and
for downstream Layers 5–6) plus a human-readable slug. Ids are assigned once, in reading order,
and never reused. This mirrors the Layer 2 `FM-NN` scheme so the two graphs cross-reference
cleanly.

| BT | Buying trigger | Slug | Primary trigger zone | Anchoring `FM-NN` (workflow breakdown) |
| --- | --- | --- | --- | --- |
| **BT-01** | VP Product / Head of Product hire | `bt-vp-product-hire` | Whole lifecycle (leader inherits fragmented context) | FM-22, FM-25, FM-18, FM-21, FM-14 |
| **BT-02** | Product Ops / Product Operations hire | `bt-product-ops-hire` | Cross-stage systematization | FM-05, FM-24, FM-22, FM-23 |
| **BT-03** | Engineering growth outpacing PM hiring | `bt-engineering-growth` | Refinement boundary gap (execution middle) | FM-12, FM-08, FM-09, FM-10, FM-01, FM-14 |
| **BT-04** | AI coding tool adoption | `bt-ai-coding-adoption` | Refinement boundary gap (accelerated) | FM-08, FM-12, FM-15, FM-04, FM-19, FM-17, FM-14 |
| **BT-05** | Series A funding | `bt-series-a-funding` | Informal→formal process transition | FM-14, FM-09, FM-05, FM-22, FM-01 |

> **Trigger identifiers (contract):** `vp_product_hire`, `product_ops_hire`,
> `engineering_growth`, `ai_coding_adoption`, `series_a_funding`. These map 1:1 to BT-01…BT-05.

> **Detection-status convention.** The five triggers and their anchoring failure modes are
> *validated* from the research (Documents 2–9, Layers 1–2). The **detection methods** below are
> GTM operational proposals — **detection candidates** to be validated and tuned through the
> Layer 6 Commercial Learning Loop. Where the research does not establish that a signal reliably
> indicates the trigger, it is marked *(detection candidate)*. No detection method is a
> demographic filter; every one is a workflow-event or capability-gap signal.

---

## 3. Buying triggers (full chain + detection method)

### BT-01 · VP Product / Head of Product hire

- **`buying_trigger_id`:** `BT-01` · **`slug`:** `bt-vp-product-hire`
- **Operational Event:** A company hires (or promotes into) a VP Product / Head of Product,
  often after operating without one for an extended period.
- **Workflow Breakdown:** The new leader inherits fragmented product context — intent,
  implementation, validation, and customer reality living in disconnected systems. This is the
  **Context Reconstruction Tax** (FM-22 at Requirements, FM-25 at Production) and cross-stage
  drift (FM-18 Implementation Drift, FM-21 Learning Drift), concentrated in the refinement
  boundary gap (FM-14).
- **Recognition of Capability Gap:** "We have no shared, current picture of what we've built,
  why, and how it's performing" — the leader recognizes the org lacks a way to *maintain and
  reconstruct product context* without manual, tribal effort.
- **Buying Trigger:** Search/evaluation for product operations, product alignment, and
  workflow-visibility tooling in the leader's first 30–90 days ("first-90-days" mandate).
- **Detection method:** LinkedIn new-hire announcements and job-change alerts for
  *VP Product / Head of Product / Chief Product Officer* titles; LinkedIn job posts for those
  titles (open req → imminent hire). *(detection candidate: correlate hire date with a >6-month
  prior vacancy for a stronger signal — see [§4](04-friction-detection-specsight-fit.md).)*
- **Associated stages (Layer 1 / Doc-2 lifecycle):** `requirements`, `production` (whole
  lifecycle); Layer 1 nodes `CN-01`, `CN-07`.
- **Associated failure modes:** FM-22, FM-25, FM-18, FM-21, FM-14.

### BT-02 · Product Ops / Product Operations hire

- **`buying_trigger_id`:** `BT-02` · **`slug`:** `bt-product-ops-hire`
- **Operational Event:** A company opens or fills a *Product Ops / Product Operations* role —
  an org deciding it needs a function dedicated to systematizing how product work runs.
- **Workflow Breakdown:** The role exists because responsibility for acceptance, evidence, and
  release readiness is fragmented across PM/QA/Engineering (FM-05 Unclear Ownership) and because
  the PM organization is paying a recurring Context Reconstruction Tax at requirements, review,
  and release (FM-22, FM-23, FM-24). Manual reporting and inconsistent metrics are the symptom.
- **Recognition of Capability Gap:** "We need a systematic, repeatable way to run product
  operations — consistent acceptance, assembled release evidence, comparable metrics — instead
  of every PM reinventing it."
- **Buying Trigger:** The Product Ops hire is *chartered* to evaluate tooling that standardizes
  workflow operations; evaluation behavior begins almost immediately.
- **Detection method:** LinkedIn job postings and keyword analysis for
  *"Product Ops" / "Product Operations"* role titles; job-description keyword analysis for
  "standardize," "reporting," "process," "tooling." *(detection candidate.)*
- **Associated stages:** `requirements`, `uat_release_readiness`; Layer 1 nodes `CN-06`,
  `CN-07`.
- **Associated failure modes:** FM-05, FM-24, FM-22, FM-23.

### BT-03 · Engineering growth outpacing PM hiring

- **`buying_trigger_id`:** `BT-03` · **`slug`:** `bt-engineering-growth`
- **Operational Event:** Engineering headcount grows materially faster than PM headcount; the
  PM-to-engineer ratio widens (e.g., past ~1:8).
- **Workflow Breakdown:** With fewer PMs per engineer, shared understanding cannot be
  maintained by conversation alone. This lands squarely in the **refinement boundary gap**:
  developers interpret the same story differently (FM-12), the build drifts from intent (FM-08),
  refinement is skipped under load (FM-09), stories block on under-refinement (FM-10), and AC
  are agreed only nominally (FM-01). FM-14 is the anchor gap.
- **Recognition of Capability Gap:** "We can't keep engineering aligned to product intent as we
  scale — PM can't keep up with what engineering is building."
- **Buying Trigger:** Search for continuous-alignment / requirements-clarity / workflow tooling
  to preserve alignment at scale.
- **Detection method:** LinkedIn employee-count tracking (engineering vs product headcount
  trend); job-posting volume analysis comparing open *engineering* reqs to open *PM* reqs over
  time. *(detection candidate: ratio thresholds require calibration via the Commercial Learning
  Loop.)*
- **Associated stages:** `implementation` (Implementation / Continuous Collaboration),
  `sprint_review`; Layer 1 nodes `CN-07`, `CN-03`, `CN-02`.
- **Associated failure modes:** FM-12, FM-08, FM-09, FM-10, FM-01, FM-14.

### BT-04 · AI coding tool adoption

- **`buying_trigger_id`:** `BT-04` · **`slug`:** `bt-ai-coding-adoption`
- **Operational Event:** The engineering team adopts AI coding assistants (Copilot, Cursor, and
  similar), materially increasing code-generation velocity.
- **Workflow Breakdown:** Code is produced faster than shared understanding of intent can be
  maintained, so implementation drift (FM-08 / FM-18) and divergent interpretation (FM-12)
  accelerate; requirements evolve faster than understanding (FM-15); validation lags behind
  generation (FM-04) and loses business intent (FM-19). This sharpens the Traditional-Scrum vs
  AI-native/Product-led tension (FM-17). The refinement boundary gap (FM-14) widens because the
  execution middle now moves at machine speed.
- **Recognition of Capability Gap:** "We're shipping faster but rework/bugs are up — we've lost
  the ability to keep what's generated aligned with what we actually intended."
- **Buying Trigger:** Search for a way to maintain product intent and validate output when
  code-generation velocity outpaces human review.
- **Detection method:** GitHub public-repo analysis for Copilot/Cursor usage patterns;
  engineering blog posts mentioning AI coding tools; job postings mentioning AI-assisted
  development. *(detection candidate: velocity-up-but-rework-up is inferred in
  [§4](04-friction-detection-specsight-fit.md), not directly observable externally.)*
- **Associated stages:** `implementation`, `sprint_review`; Layer 1 nodes `CN-07`, `CN-03`.
- **Associated failure modes:** FM-08, FM-12, FM-15, FM-04, FM-19, FM-17, FM-14.

### BT-05 · Series A funding

- **`buying_trigger_id`:** `BT-05` · **`slug`:** `bt-series-a-funding`
- **Operational Event:** A company raises a Series A and begins scaling engineering from a small
  team (e.g., <10) toward a larger one (>20).
- **Workflow Breakdown:** Informal product processes that worked at founder scale start to
  break down: the refinement boundary gap opens (FM-14), refinement gets skipped under growth
  pressure (FM-09), acceptance ownership blurs as roles are added (FM-05), the Context
  Reconstruction Tax at requirements begins (FM-22), and AC ambiguity surfaces as more people
  read the same story (FM-01).
- **Recognition of Capability Gap:** "The informal way we stayed aligned doesn't scale — we
  need a repeatable way to keep product and engineering aligned as we grow."
- **Buying Trigger:** Post-raise tooling and process investment; search for product/workflow
  infrastructure as headcount scales.
- **Detection method:** Crunchbase funding alerts (Series A events); press-release / funding-news
  monitoring; paired with LinkedIn engineering-headcount growth post-raise. *(detection
  candidate: funding alone is a precondition; pair with a scaling signal — see
  [§4](04-friction-detection-specsight-fit.md).)*
- **Associated stages:** `requirements`, `implementation`; Layer 1 nodes `CN-01`, `CN-07`.
- **Associated failure modes:** FM-14, FM-09, FM-05, FM-22, FM-01.

---

## 4. Summary table (all six fields populated)

| Buying Trigger | Operational Event | Workflow Breakdown | Capability Gap | Detection Method | Associated Stage / Failure Mode |
| --- | --- | --- | --- | --- | --- |
| **BT-01** VP Product hire | VP Product / Head of Product joins (often after a long vacancy) | Leader inherits fragmented product context; Context Reconstruction Tax + cross-stage drift | "No shared, current picture of what we built and why; no way to maintain/reconstruct context" | LinkedIn new-hire & job-change alerts for VP/Head of Product titles | `requirements`, `production`; FM-22, FM-25, FM-18, FM-21, FM-14 |
| **BT-02** Product Ops hire | Company opens/fills a Product Ops role | Fragmented acceptance ownership + recurring reconstruction tax across stages | "Need a systematic, repeatable way to run product operations" | LinkedIn job-posting keyword analysis for "Product Ops"/"Product Operations" | `requirements`, `uat_release_readiness`; FM-05, FM-24, FM-22, FM-23 |
| **BT-03** Engineering growth | Eng headcount grows faster than PM; PM-to-eng ratio widens | Shared understanding can't be maintained by conversation; execution-middle breakdowns | "Can't keep engineering aligned to product intent as we scale" | LinkedIn employee-count tracking; eng-vs-PM job-posting volume analysis | `implementation`, `sprint_review`; FM-12, FM-08, FM-09, FM-10, FM-01, FM-14 |
| **BT-04** AI coding adoption | Team adopts Copilot/Cursor; code velocity jumps | Code outpaces shared understanding; drift & divergent interpretation accelerate | "Shipping faster but lost alignment between generated code and intent" | GitHub public-repo analysis; eng blog posts; job posts mentioning AI-assisted dev | `implementation`, `sprint_review`; FM-08, FM-12, FM-15, FM-04, FM-19, FM-17, FM-14 |
| **BT-05** Series A funding | Series A raised; engineering scales from <10 to >20 | Informal processes break down; refinement boundary gap opens | "The informal way we stayed aligned doesn't scale" | Crunchbase funding alerts; press-release monitoring + headcount growth | `requirements`, `implementation`; FM-14, FM-09, FM-05, FM-22, FM-01 |

---

## 5. Additional trigger candidates (hypotheses)

The five triggers above are the validated set the research names explicitly. Framework 4's logic
(any recognized workflow breakdown can fire a trigger) implies further candidates, but the
research corpus does not yet establish concrete, externally observable detection methods for
them. They are recorded here as **hypotheses / detection candidates** — *not* assigned stable
`BT-NN` ids until validated through the Layer 6 Commercial Learning Loop:

- **Acute Context Reconstruction Tax threshold** — "release meetings getting longer,"
  "engineering repeatedly explaining behavior" crossing a pain threshold (FM-23, FM-24). Hard to
  detect externally today; may surface via Glassdoor/community complaints. *(hypothesis)*
- **Post-incident / quality-crisis event** — a public incident or a run of production surprises
  (FM-20 Reality Drift, FM-25). Detectable via status pages / incident write-ups. *(hypothesis)*
- **Methodology/process debate going public** — engineering-blog or conference content about
  process breakdown or the Scrum↔Product-led tension (FM-17). *(hypothesis)*

> These stay out of the canonical `BT-NN` set so downstream layers consume a stable, validated
> trigger list. Promotion to a `BT-NN` id requires a validated detection method.

---

*Next: [Section 2 — Failure-mode → company-level signals](02-failure-mode-company-signals.md) · Back to [Layer 4 hub](../layer-4-buying-trigger-graph.md)*
