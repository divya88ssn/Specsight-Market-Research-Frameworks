# Layer 4 · Section 4 — Friction Detection & Specsight-Fit Model

> **Role in the graph:** The synthesizing section. It combines the trigger events
> ([§1](01-trigger-events-detection-methods.md)), failure-mode signals
> ([§2](02-failure-mode-company-signals.md)), and evaluation/decision process
> ([§3](03-evaluation-criteria-decision-process.md)) into one **friction-detection model** and,
> per trigger, a **Specsight-fit assessment**. It closes with the **demographic → workflow
> replacement table** that operationalizes the brief's core thesis: buying triggers replace
> demographic-based ICP with workflow-based trigger detection.
>
> **Owning subtask:** DIV-55. **Parent:** DIV-35.
> **Consumes:** the `BT-NN` triggers (§1), the `FM-NN` failure-mode signals (§2), and the
> evaluation/decision process (§3).
> **Out of scope here:** defining trigger events (§1), failure-mode→signal mapping (§2),
> evaluation/decision process (§3), cataloguing failure modes (Layer 2), the depth mapping of
> failure mode → missing capability → Specsight capability (Layer 3 / DIV-34), ICP scoring and
> outreach (sibling brief tasks).

---

## 1. The friction-detection model

The brief's key passage defines exactly what a workflow-grounded model must produce:

> *"If you understand the workflow, the decisions, the artifacts, the collaboration patterns,
> the terminology, the failure modes, then you can identify: when someone is likely to
> experience friction, how they describe that friction, what workaround they're using, what
> capability they're missing, and whether Specsight is a natural fit."*

For each buying trigger this section documents five fields:

| Field | Meaning |
| --- | --- |
| **Likelihood indicators** | Early **preconditions** that precede the full trigger firing — how to detect *likely* friction, not just the event |
| **Practitioner language** | The exact phrases practitioners use to describe the friction (Framework 5: study where practitioners complain), sourced from the research |
| **Workaround used** | What teams do today to cope |
| **Missing capability** | The capability the workaround stands in for (referenced at the Layer 2 underserved-gap level; the depth mapping to Specsight is Layer 3 / DIV-34) |
| **Specsight-fit assessment** | Whether Specsight is a natural fit and why / why not |

> **Framework 5 in action.** The `practitioner_language` field is deliberately the *practitioner
> pain* half of the Layer 2 Framework-5 separation — observable complaints, not framework
> theory. Quotes are drawn from the research corpus surfaced in Layer 2 (Documents 2–9).

> **Detection & product-detail convention.** The triggers, failure modes, and practitioner
> quotes are *validated* (Layers 1–2, Documents 2–9). The **likelihood indicators** are GTM
> **detection candidates** (preconditions to validate via the Commercial Learning Loop). Because
> Layer 3 (DIV-34) owns the capability→Specsight mapping and concrete product details are not
> established in this research, the **missing capability** is stated at the Layer 2 underserved-gap
> level and Specsight product specifics are marked *(fit hypothesis)*.

---

## 2. Per-trigger friction & fit

### BT-01 · VP Product / Head of Product hire

- **Likelihood indicators (preconditions):** company operated **>6 months without** a VP
  Product; PM team reports into Engineering or the CEO; recent product delays or quality issues
  preceding the hire. *(detection candidate.)*
- **Practitioner language:** *"Product knowledge is tribal."* · *"Slack becomes the source of
  truth."* · *"PMs are becoming translators instead of strategists."* · *"I can't get a clear
  picture of what we've built and why."* (FM-22, FM-25, FM-18, FM-21)
- **Workaround used:** manual context reconstruction from demos, Jira, dashboards, support
  tickets, and engineering explanations; onboarding interviews; more alignment meetings.
- **Missing capability:** a persistent, cohesive way to **maintain and reconstruct product
  context** across intent → implementation → validation → customer reality (Layer 2 underserved
  gap; Context Reconstruction Tax cluster). *(Layer 3 / DIV-34 maps this to a Specsight
  capability.)*
- **Specsight-fit assessment:** **Strong fit (fit hypothesis).** A continuous-alignment /
  context capability directly answers the new leader's "reconstruct fragmented context" pain.
  Weaker fit if the org is tiny (little context to reconstruct) or if the VP's mandate is purely
  strategic/market-facing rather than delivery-alignment.

### BT-02 · Product Ops / Product Operations hire

- **Likelihood indicators:** **>20 PMs with no Product Ops** function; manual reporting
  consuming significant PM time; inconsistent product metrics across teams. *(detection
  candidate.)*
- **Practitioner language:** *"Whose call is it whether this is done?"* · *"Every PM does
  acceptance differently."* · *"Release meetings are getting longer."* · *"We reassemble evidence
  from many systems every release."* (FM-05, FM-24, FM-23)
- **Workaround used:** manual reporting and checklists; committee-based acceptance; spreadsheets;
  reassembling release evidence by hand each cycle; hiring the Product Ops role itself.
- **Missing capability:** a **systematic, repeatable operating capability** — consistent
  acceptance ownership and assembled release-readiness evidence — instead of per-PM improvisation
  (Layer 2 underserved gap: FM-05, FM-24). *(Layer 3 / DIV-34 maps to Specsight.)*
- **Specsight-fit assessment:** **Strong fit (fit hypothesis).** The Product Ops charter *is*
  standardizing workflow operations — a natural buyer for a cohesive alignment/evidence
  capability. Weaker fit if the org already runs a mature internal platform, or if Product Ops is
  scoped narrowly to analytics/BI.

### BT-03 · Engineering growth outpacing PM hiring

- **Likelihood indicators:** engineering headcount growing **>30% YoY while PM headcount is
  flat**; PM-to-engineer ratio dropping below ~**1:8**. *(detection candidate.)*
- **Practitioner language:** *"Devs interpret stories differently."* · *"PM can't keep up with
  what engineering is building."* · *"It drifted from what we wanted."* · *"We were blocked / we
  guessed."* (FM-12, FM-08, FM-10)
- **Workaround used:** more meetings and ceremonies; heavier documentation; asking engineering
  to explain what was built; hiring more PMs; ad hoc clarification during the sprint.
- **Missing capability:** a **continuous shared-understanding capability** that maintains
  intent↔execution alignment as headcount scales — the refinement-boundary-gap capability (Layer
  2: FM-12, FM-08, FM-09, FM-14). *(Layer 3 / DIV-34 maps to Specsight.)*
- **Specsight-fit assessment:** **Strong fit (fit hypothesis).** This is the refinement boundary
  gap — Specsight's most differentiated zone per Layer 1 §5. Weaker fit if the team is small
  enough that conversation still maintains alignment, or if they choose to solve it purely by
  hiring PMs.

### BT-04 · AI coding tool adoption

- **Likelihood indicators:** engineering team adopted **Copilot/Cursor within the last 6
  months**; velocity increased **but bug rates or rework also increased**. *(detection
  candidate — the velocity/rework inference is not directly observable externally.)*
- **Practitioner language:** *"We're shipping faster but rework is up."* · *"Everyone read it
  differently."* · *"We built the old version."* · *"Tests pass but it misses the point."*
  (FM-08, FM-12, FM-15, FM-19)
- **Workaround used:** more code review; more QA; slowing AI adoption; extra validation passes
  at the end of the cycle.
- **Missing capability:** a capability to **maintain product intent and validate output at
  machine-generation speed** — the refinement boundary gap under acceleration (Layer 2: FM-08,
  FM-15, FM-19, FM-14). *(Layer 3 / DIV-34 maps to Specsight.)*
- **Specsight-fit assessment:** **Strong / emerging fit (fit hypothesis).** AI-accelerated
  velocity widens exactly the gap Specsight targets; this is a leading-edge trigger. Weaker fit
  if AI adoption is exploratory (low volume) or if the team has strong existing validation
  discipline that absorbs the velocity.

### BT-05 · Series A funding

- **Likelihood indicators:** **recently raised Series A**; engineering scaling from **<10 to
  >20**; informal product processes starting to break down. *(detection candidate — pair funding
  with a headcount-growth signal.)*
- **Practitioner language:** *"The informal way we stayed aligned doesn't scale."* · *"We keep
  re-clarifying the same stories."* · *"Nobody owns acceptance anymore."* (FM-14, FM-09, FM-05)
- **Workaround used:** hiring senior PMs / first Product Ops; adopting heavier Agile process;
  more documentation; keeping informal alignment as long as possible.
- **Missing capability:** a **lightweight, repeatable alignment capability** to replace informal
  founder-scale coordination as the team grows (Layer 2: FM-14, FM-09, FM-05). *(Layer 3 /
  DIV-34 maps to Specsight.)*
- **Specsight-fit assessment:** **Conditional fit (fit hypothesis).** Strong when the raise is
  paired with real engineering scaling (the gap is opening now); weaker if the company is *too
  early / too small* (informal alignment still works) or if the raise does not translate into
  headcount growth — a caution the model must honor rather than treating "Series A" as a
  demographic proxy for buying intent.

---

## 3. Friction-detection summary table

| Buying Trigger | Likelihood Indicators (preconditions) | Practitioner Language | Workaround | Missing Capability | Specsight Fit |
| --- | --- | --- | --- | --- | --- |
| **BT-01** VP Product hire | >6mo without a VP; PM reports to Eng/CEO; recent delays/quality issues | "Product knowledge is tribal"; "Slack is the source of truth"; "PMs becoming translators" | Manual context reconstruction; onboarding interviews; more meetings | Maintain/reconstruct product context (Context Reconstruction Tax cluster) | Strong (fit hypothesis) |
| **BT-02** Product Ops hire | >20 PMs, no Product Ops; manual reporting heavy; inconsistent metrics | "Whose call is done?"; "every PM does acceptance differently"; "release meetings getting longer" | Manual reporting; committee acceptance; spreadsheets; hiring the role | Systematic acceptance + assembled release evidence (FM-05, FM-24) | Strong (fit hypothesis) |
| **BT-03** Engineering growth | Eng +30% YoY, PM flat; PM-to-eng ratio < ~1:8 | "Devs interpret stories differently"; "PM can't keep up"; "it drifted from what we wanted" | More meetings/docs; ask eng to explain; hire more PMs | Continuous shared-understanding at scale (refinement boundary gap: FM-12, FM-08, FM-14) | Strong (fit hypothesis) |
| **BT-04** AI coding adoption | Copilot/Cursor adopted <6mo; velocity up **and** rework/bugs up | "Shipping faster but rework is up"; "everyone read it differently"; "we built the old version" | More review; more QA; slow AI adoption; end-of-cycle validation | Maintain intent + validate at generation speed (FM-08, FM-15, FM-19, FM-14) | Strong/emerging (fit hypothesis) |
| **BT-05** Series A funding | Recent Series A; eng scaling <10→>20; informal processes breaking | "Informal alignment doesn't scale"; "we re-clarify the same stories"; "nobody owns acceptance" | Hire senior PMs/Product Ops; heavier process; more docs | Lightweight repeatable alignment as team scales (FM-14, FM-09, FM-05) | Conditional (fit hypothesis) |

---

## 4. Demographic → Workflow replacement table

The core reframing, made operational. Each traditional demographic ICP dimension is replaced by
a **workflow-based equivalent** grounded in the triggers, signals, and failure modes above. This
is the qualification model the parent task (DIV-35) requires — no trigger qualifies on a
demographic attribute alone.

| Dimension | Demographic approach (replaced) | Workflow-based approach (this graph) |
| --- | --- | --- |
| **`company_size`** | Filter on employee count / revenue band | **Workflow complexity signals** — PM-to-engineer ratio, number of product teams, engineering-growth rate (BT-03); presence/absence of a Product Ops function (BT-02) |
| **`budget`** | Filter on funding stage / spend as a proxy for ability to pay | **Trigger-event urgency** — an *active* workflow breakdown creating acute pain now: Series A + scaling (BT-05), VP hire first-90-days mandate (BT-01), AI-velocity rework spike (BT-04) |
| **`industry`** | Filter on vertical / SIC code | **Workflow-model adoption** — Agile/ceremony maturity, DoD/evidence documentation, refinement practice; the failure-mode signals in [§2](02-failure-mode-company-signals.md) (FM-01…FM-07) |
| **`job_title`** | Target a title regardless of context | **Role-in-workflow-pain** — the PM experiencing alignment breakdown, the VP inheriting fragmented context (BT-01), the Product Ops hire seeking a systematic approach (BT-02), the Eng Lead absorbing AI-velocity drift (BT-04) |

> **Qualification rule (parent-task success criterion).** A prospect qualifies when an
> **observable workflow event** produces a **recognized capability gap** (a `BT-NN` trigger
> anchored to `FM-NN` breakdowns), **not** when a demographic filter matches. Company size,
> budget, industry, and job title enter only as their workflow-based equivalents above. This
> replacement is what lets the graph feed ICP refinement, outreach sequencing, and the PLG
> workflow assessment (Layer 5 / sibling brief) without re-interpretation.

---

*Previous: [Section 3 — Evaluation criteria & decision process](03-evaluation-criteria-decision-process.md) · Back to [Layer 4 hub](../layer-4-buying-trigger-graph.md)*
