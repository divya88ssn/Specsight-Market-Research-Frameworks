# Layer 4 · Section 3 — Evaluation Criteria & Decision Process

> **Role in the graph:** Completes the extended Framework-4 chain — `… → Buying Trigger →
> Evaluation Criteria → Decision Process` — for each buying trigger defined in
> [§1](01-trigger-events-detection-methods.md). For every `BT-NN`, this section documents the
> evaluation criteria prospects apply, the decision process they run from trigger recognition to
> purchase, the roles involved and their influence, and the information sources they consult.
>
> **Owning subtask:** DIV-50. **Parent:** DIV-35.
> **Consumes:** the `BT-NN` triggers from §1.
> **Out of scope here:** defining the trigger events (§1), failure-mode→signal mapping (§2),
> friction detection & Specsight-fit (§4), ICP scoring (sibling brief), outreach messaging
> (sibling brief), the PLG assessment tool (sibling brief).

---

## 1. The decision-process model

The persona/JTBD research and the customer-decision proposal frame two questions — *"How do
prospects evaluate alternatives?"* and *"What information influences that decision?"* This
section answers both per trigger, over a common five-stage decision process:

| Stage id | Stage | What happens |
| --- | --- | --- |
| `trigger_recognition` | Trigger Recognition | The prospect becomes aware of their own workflow pain |
| `active_evaluation` | Active Evaluation | They search for and evaluate alternatives |
| `shortlisting` | Shortlisting | They narrow options (features, integration, fit, budget) |
| `trial_poc` | Trial / POC | A pilot, assessment, or limited-scope proof |
| `purchase_decision` | Purchase Decision | Who decides, and how budget/buy-in is secured |

Evaluation criteria are documented on four axes: **functional capabilities**, **non-functional
criteria**, **proof required**, and **comparison alternatives** (what they weigh against —
including "doing nothing").

> **Detection-status convention.** The trigger structure is validated (§1). The evaluation
> criteria, decision-process specifics, roles, and information sources here are **research-informed
> hypotheses** grounded in the persona/JTBD/customer-decision framing — to be validated and
> refined through the Layer 6 Commercial Learning Loop and the sibling PLG assessment.

---

## 2. Per-trigger evaluation & decision process

### BT-01 · VP Product / Head of Product hire

- **Evaluation criteria:**
  - *Functional:* workflow visibility across the lifecycle; a current, shared picture of what
    was built and why; the ability to reconstruct product context without manual effort.
  - *Non-functional:* fast time-to-value inside a first-90-days mandate; low team-adoption
    friction; integration with existing Jira/docs/analytics.
  - *Proof:* a demo against the org's own fragmented context; a short assessment of current
    workflow health; references from peer product leaders.
  - *Comparison alternatives:* hiring more PMs/Product Ops; internal dashboards; status-quo
    (tribal knowledge + Slack).
- **Decision process:** `trigger_recognition` (new VP finds fragmented context in first 30 days)
  → `active_evaluation` (peer-leader recommendations, product-leadership communities) →
  `shortlisting` (fit to first-90-days plan, integration check) → `trial_poc` (pilot with one
  product team) → `purchase_decision` (VP holds budget and authority; approves directly).
- **Key decision roles:** VP Product — **decision maker / champion** (high); Product Ops / Senior
  PM — evaluator (medium); Engineering Lead — buy-in (medium).
- **Information sources:** product-leadership communities and peer networks (e.g., Lenny's
  community, CPO/VP-Product Slack groups), analyst/peer references, vendor site.

### BT-02 · Product Ops / Product Operations hire

- **Evaluation criteria:**
  - *Functional:* standardized acceptance and release-evidence assembly; consistent, comparable
    product metrics across teams; reduction of manual reporting.
  - *Non-functional:* scalability across many PMs/teams; repeatability; integration with the
    existing stack.
  - *Proof:* a structured workflow assessment; a pilot showing reduced manual reporting;
    quantified time savings.
  - *Comparison alternatives:* building internal reporting/process; spreadsheets and manual
    checklists; BI dashboards.
- **Decision process:** `trigger_recognition` (Product Ops hire chartered to systematize) →
  `active_evaluation` (Product Ops communities, tooling comparisons) → `shortlisting` (fit to
  the standardization charter) → `trial_poc` (assessment + limited rollout to a few teams) →
  `purchase_decision` (Product Ops recommends; VP Product / CPO approves budget).
- **Key decision roles:** Product Ops — **champion / evaluator** (high); VP Product / CPO —
  approver (high); PM team — adoption stakeholders (medium).
- **Information sources:** Product Ops communities (e.g., Product Ops HQ / Mind the Product),
  peer Product-Ops practitioners, vendor comparisons, engineering blogs.

### BT-03 · Engineering growth outpacing PM hiring

- **Evaluation criteria:**
  - *Functional:* continuous alignment between product intent and engineering execution at
    scale; requirements clarity; a way to keep shared understanding as headcount grows.
  - *Non-functional:* low per-engineer adoption friction; fits existing engineering workflow;
    scales without adding PM headcount.
  - *Proof:* pilot on one squad showing fewer misinterpretations / less rework; developer
    adoption evidence.
  - *Comparison alternatives:* hiring more PMs; more meetings/ceremonies; heavier documentation;
    doing nothing.
- **Decision process:** `trigger_recognition` (PM can't keep up with what engineering ships) →
  `active_evaluation` (PM + eng-leadership communities, peer recommendations) → `shortlisting`
  (developer-adoption fit, integration with dev tools) → `trial_poc` (pilot with one squad) →
  `purchase_decision` (Senior/Group PM champions; VP Product or Eng Lead approves; engineering
  buy-in required).
- **Key decision roles:** Senior PM / Group PM — **champion** (high); Engineering Lead — buy-in
  / co-approver (high); VP Product — budget approver (medium).
- **Information sources:** r/productmanagement, Hacker News, engineering-leadership networks,
  peer PMs, vendor site.

### BT-04 · AI coding tool adoption

- **Evaluation criteria:**
  - *Functional:* maintaining product intent when code-generation velocity outpaces review;
    validating generated output against intent; catching drift early.
  - *Non-functional:* keeps up with AI-accelerated velocity; integrates with the AI-native dev
    workflow; minimal added process.
  - *Proof:* pilot demonstrating drift/rework reduction under AI-assisted development; evidence
    it does not slow the velocity gains.
  - *Comparison alternatives:* more code review; more QA; slowing down AI adoption; doing
    nothing.
- **Decision process:** `trigger_recognition` (velocity up but rework/bugs up) →
  `active_evaluation` (AI-native dev communities, Hacker News, engineering blogs) →
  `shortlisting` (fit to AI toolchain, velocity impact) → `trial_poc` (pilot on an
  AI-heavy team) → `purchase_decision` (Engineering Lead + PM champion co-decide; budget from
  eng or product).
- **Key decision roles:** Engineering Lead / Head of Eng — **champion / co-decision** (high);
  Senior PM — co-champion (high); VP Product — approver (medium).
- **Information sources:** Hacker News, AI-native engineering communities and blogs, GitHub
  discussions, peer engineering leaders.

### BT-05 · Series A funding

- **Evaluation criteria:**
  - *Functional:* a repeatable way to keep product and engineering aligned as the team scales;
    lightweight process infrastructure that grows with headcount.
  - *Non-functional:* fast to stand up; cheap relative to the raise; won't slow a fast-moving
    team; scales from ~10 to ~30+.
  - *Proof:* quick pilot; peer references from other recently-funded startups; short
    time-to-value.
  - *Comparison alternatives:* hiring senior PMs/Product Ops; adopting heavier Agile process;
    keeping informal alignment; doing nothing.
- **Decision process:** `trigger_recognition` (informal alignment starts breaking post-raise) →
  `active_evaluation` (founder/early-PM networks, startup communities) → `shortlisting`
  (lightweight fit, cost) → `trial_poc` (fast pilot across the small team) → `purchase_decision`
  (founder / Head of Product decides quickly; short cycle).
- **Key decision roles:** Founder / Head of Product — **decision maker** (high); early Engineering
  Lead — buy-in (medium); first PM hire — evaluator (medium).
- **Information sources:** founder and early-stage communities, YC/startup networks, peer
  founders, LinkedIn, vendor site.

---

## 3. Summary table (all five fields populated)

| Buying Trigger | Evaluation Criteria | Decision Process Stages | Key Decision Roles | Information Sources |
| --- | --- | --- | --- | --- |
| **BT-01** VP Product hire | Lifecycle workflow visibility; context reconstruction; fast time-to-value; Jira/docs/analytics integration; proof via demo on own context + peer refs; vs. more PMs / dashboards / status-quo | recognition → active eval → shortlist → pilot (one team) → VP approves | VP Product (decision/champion, high); Product Ops/Sr PM (eval, med); Eng Lead (buy-in, med) | Product-leadership communities & peer networks; analyst/peer refs; vendor site |
| **BT-02** Product Ops hire | Standardized acceptance & release evidence; comparable metrics; less manual reporting; scalable/repeatable; proof via assessment + pilot; vs. internal build / spreadsheets / BI | recognition → active eval → shortlist → assessment + limited rollout → Product Ops recommends, CPO approves | Product Ops (champion, high); VP Product/CPO (approver, high); PM team (adoption, med) | Product Ops communities; peer Product-Ops; vendor comparisons; eng blogs |
| **BT-03** Engineering growth | Continuous intent↔execution alignment at scale; requirements clarity; low per-eng friction; scales without PM headcount; proof via squad pilot; vs. more PMs / meetings / docs | recognition → active eval → shortlist → squad pilot → Sr PM champions, VP/Eng Lead approve | Sr/Group PM (champion, high); Eng Lead (buy-in/co-approver, high); VP Product (budget, med) | r/productmanagement; Hacker News; eng-leadership networks; peer PMs; vendor site |
| **BT-04** AI coding adoption | Maintain intent at AI velocity; validate output vs intent; catch drift early; keeps up with velocity; proof via AI-team pilot; vs. more review / QA / slowing down | recognition → active eval → shortlist → AI-team pilot → Eng Lead + PM co-decide | Eng Lead/Head of Eng (champion/co-decision, high); Sr PM (co-champion, high); VP Product (approver, med) | Hacker News; AI-native eng communities & blogs; GitHub discussions; peer eng leaders |
| **BT-05** Series A funding | Repeatable alignment as team scales; lightweight infra; fast to stand up; cheap vs raise; proof via quick pilot + peer refs; vs. senior PM hires / heavy process / informal | recognition → active eval → shortlist → fast team-wide pilot → founder/Head of Product decides | Founder/Head of Product (decision, high); early Eng Lead (buy-in, med); first PM (eval, med) | Founder & early-stage communities; YC/startup networks; peer founders; LinkedIn; vendor site |

---

*Previous: [Section 2 — Failure-mode → company-level signals](02-failure-mode-company-signals.md) · Next: [Section 4 — Friction detection & Specsight-fit model](04-friction-detection-specsight-fit.md) · Back to [Layer 4 hub](../layer-4-buying-trigger-graph.md)*
