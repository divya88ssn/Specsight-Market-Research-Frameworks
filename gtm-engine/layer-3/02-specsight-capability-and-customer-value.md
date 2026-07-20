# Layer 3 · Section 2 — Specsight Capability & Customer Value (Links 5–6)

> **Role in the Capability Graph:** Completes the `CapabilityMappingChain`
> ([§0](00-capability-mapping-chain-schema.md)) by populating **links 5–6** — Specsight
> capability and customer value — for every `CAP` node defined in
> [§1](01-failure-mode-to-capability-map.md). This produces the complete six-link chain for
> every failure mode.
>
> **Owning subtask:** DIV-54.
> **Consumes:** the `CAP-01…CAP-07` registry and links 1–4 from §1.
> **Applies:** Framework 3 (Missing Capability → Specsight Capability → Customer Value), using
> the persona document's "What Specsight Could Do", "Value Created", and trigger-table
> "Specsight Value" columns as the validated language pattern.
> **Out of scope here:** the current-vs-missing gap assessment (§3, DIV-57), buying triggers
> (Layer 4), messaging/positioning copy (sibling brief).

---

## 1. Framework 3 in one line

Each missing capability is completed to a **Specsight capability** and the **customer value**
it delivers, in the research's validated value vocabulary — *persistent behavioral model,
implementation-aware behavioral summary, traceable behavioral validation, behavioral
traceability, persistent product knowledge, a single behavioral view* — never generic
feature-list or "improve collaboration / streamline workflows" language. Where Document 2 does
not establish a concrete Specsight capability, the node is marked **`Hypothesis / roadmap
candidate`** and framed as what Specsight *could* do, not invented product detail
([§0.6](00-capability-mapping-chain-schema.md)).

---

## 2. CAP-01 · Persistent representation of customer intent

- **Specsight capability (link 5):** *Create a persistent behavioral model from requirements
  and continuously link it to implementation* — a living behavioral model that explains how the
  product is intended to work and stays authoritative as understanding evolves.
- **Customer value (link 6):** *Everyone starts implementation from the same behavioral
  understanding, reducing clarification meetings and interpretation drift.*
- **`specsightConfidence`:** `Validated` (persona "What Specsight Could Do" A; trigger-table
  "persistent product knowledge").

## 3. CAP-02 · Continuously maintained shared understanding during execution

- **Specsight capability (link 5):** *Continuously link the persistent behavioral model to
  implementation as work proceeds* — keeping the behavioral understanding of intent maintained
  through the execution middle rather than decaying after Sprint Planning. This is the
  continuous-alignment application of the persistent behavioral model to the refinement
  boundary gap (Layer 1 §5), where Specsight is most differentiated.
- **Customer value (link 6):** *Product intent stays aligned with the build through execution —
  fewer blocked stories, less mid-sprint rework, and fewer emergency clarification meetings,
  because shared understanding is maintained rather than reconstructed.*
- **`specsightConfidence`:** `Validated` (persona A's "continuously link it to implementation";
  the execution-middle differentiation is grounded in Layer 1 §5).

## 4. CAP-03 · Automatic comparison of intent vs implemented behavior

- **Specsight capability (link 5):** *Automatically generate an implementation-aware
  behavioral summary from the repository — show what changed, impacted workflows, edge cases,
  and differences from expected behavior* ("behavioral summaries and workflow impact derived
  from the repository").
- **Customer value (link 6):** *PM reviews behavior instead of reverse-engineering
  implementation; engineering spends less time translating code into business language.*
- **`specsightConfidence`:** `Validated` (persona "What Specsight Could Do" B; trigger-table
  "Continuous understanding of implemented behavior").

## 5. CAP-04 · Shared behavioral understanding across Product, QA & Engineering

- **Specsight capability (link 5):** *One behavioral view accessible to Product, QA, Support,
  and Leadership* — a single view of intended and implemented behavior that all roles verify
  against, so functional and intent checks reference the same understanding.
- **Customer value (link 6):** *The three roles verify against one behavioral understanding —
  QA's functional check and Product's intent check align, passing work stops missing intent,
  and acceptance ownership becomes legible.*
- **`specsightConfidence`:** `Validated` (trigger-table "Shared behavioral understanding: one
  behavioral view accessible to Product, QA, Support, and Leadership").

## 6. CAP-05 · Traceable behavioral validation (AC → validated behaviors)

- **Specsight capability (link 5):** *Trace validated behaviors back to the original acceptance
  criteria and customer workflows; surface what has been validated, partially validated, or
  remains unverified* ("show intended → implemented → validated behaviors in one place").
- **Customer value (link 6):** *Go/No-Go decisions become evidence-based instead of
  meeting-based; Product gains confidence that the right behaviors — not just the right tests —
  were validated.*
- **`specsightConfidence`:** `Validated` (persona "What Specsight Could Do" C; trigger-table
  "Traceable behavioral validation").

## 7. CAP-06 · Continuous traceability from intent → implementation → validation → customer outcomes

- **Specsight capability (link 5):** *Connect production behavior back to implemented features
  and original product intent — explain which behaviors changed, which customer journeys are
  affected, and which releases likely contributed* ("connect customer observations to
  behavioral changes and implementation history").
- **Customer value (link 6):** *Faster understanding of customer impact, better
  prioritization, and less dependence on Engineering for every production investigation.*
- **`specsightConfidence`:** `Validated` (persona "What Specsight Could Do" D; trigger-table
  "Behavioral traceability").

## 8. CAP-07 · Operational clarification-vs-requirement-evolution boundary

- **Specsight capability (link 5) — *hypothesis*:** The research does **not** establish a
  concrete Specsight capability for the clarification-vs-requirement-evolution decision, loop
  separation, or locating a team on the Scrum↔Product-led spectrum. As a roadmap candidate,
  Specsight's persistent behavioral model *could* make requirement-changing changes visible —
  flagging when a mid-flight change alters *intended behavior* (requirement evolution → new
  backlog work) versus merely clarifies it (no AC change) — but the decision, governance, and
  loop-separation workflow are not part of the validated capability set.
- **Customer value (link 6) — *hypothesis*:** *Teams could distinguish continuous alignment
  from scope creep against a shared behavioral record, reducing the recurring process debate
  and silent AC drift* — value contingent on the roadmap capability above.
- **`specsightConfidence`:** `Hypothesis / roadmap candidate` (no Document 2 capability
  established; framed as could-do, no product detail invented).

---

## 9. The complete `CapabilityMappingChain` (all six links)

Consolidated view — every `CAP` node with all six links. Links 1–4 summarize §1; links 5–6 are
populated here. Full per-failure-mode workarounds and alternatives live in §1.

| `CAP` · `FM` ids | 1 · Failure mode | 2 · Missing capability | 3 · Workaround | 4 · Alternatives | 5 · Specsight capability | 6 · Customer value | Conf. |
| --- | --- | --- | --- | --- | --- | --- | --- |
| **CAP-01** · FM-01/12/15/22 | Ambiguous AC; divergent interpretation; reqs outrun understanding; requirements re-translation tax | Persistent representation of customer intent | Clarification meetings; manual re-communication; PM rewriting requirements | AC free-text in Jira; PRDs, Figma, docs, Slack | Persistent behavioral model from requirements, continuously linked to implementation | Everyone starts from the same behavioral understanding; fewer clarification meetings and less interpretation drift | Validated |
| **CAP-02** · FM-09/10/11/14 | Skipped refinement; blocked eng; velocity loss; refinement boundary gap | Continuously maintained shared understanding during execution | Emergency clarification; guessing to proceed; estimate buffers; informal mid-sprint checks | Jira ceremonies/blocked-status/velocity charts; Slack, demos | Continuously link the behavioral model to implementation as work proceeds | Intent stays aligned through execution; fewer blocked stories, less rework, fewer emergency meetings | Validated |
| **CAP-03** · FM-04/06/08/18/23 | Late validation; happy-path demos; implementation drift; Sprint-Review reconstruction | Automatic comparison of intent vs implemented behavior | Demo-based validation; post-demo Q&A; retroactive artifact updates | CI/test tools; demo tools; Jira, docs, GitHub PRs, release notes | Implementation-aware behavioral summary from the repository (what changed, impacted workflows, edge cases, deviations) | PM reviews behavior instead of reverse-engineering; engineering translates less code into business language | Validated |
| **CAP-04** · FM-05/07 | Unclear acceptance ownership; QA–Product–Eng misalignment | Shared behavioral understanding across Product, QA & Engineering | Committee co-ownership; manual reconciliation of QA vs intent; extra alignment meetings | Jira assignee/status; test tools | One behavioral view accessible to Product, QA, Support, and Leadership | Three roles verify against one understanding; QA and intent checks align; ownership becomes legible | Validated |
| **CAP-05** · FM-02/03/19/20/24 | Subjective PO approval; missing evidence; validation drift; reality drift; UAT evidence reassembly | Traceable behavioral validation (AC → validated behaviors) | Accept on demo/QA's word; manual evidence collection; reassembling evidence for Go/No-Go | Jira + test/CI tools; QA/release tools, spreadsheets; analytics | Trace validated behaviors to AC and customer workflows; surface validated/partial/unverified | Go/No-Go becomes evidence-based; confidence the right behaviors (not just tests) were validated | Validated |
| **CAP-06** · FM-21/25 | Learning drift; production context reconstruction | Continuous traceability intent → implementation → validation → customer outcomes | Manual synthesis of scattered learnings; correlating releases with behavior by hand | Analytics, support, CRM, incident tools (separate systems) | Connect production behavior to implemented features and original intent; connect customer observations to behavioral/implementation history | Faster understanding of customer impact; better prioritization; less dependence on Engineering per investigation | Validated |
| **CAP-07** · FM-13/16/17 | Clarification vs scope-creep confusion; two-loop conflation; schools-of-practice tension | Operational clarification-vs-requirement-evolution boundary | Ad hoc scope negotiation; absorbing discovery into acceptance; blending philosophies informally | Jira/Slack; linear-workflow tools; (no methodology tooling) | *Hypothesis:* flag when a change alters intended behavior (evolution) vs clarifies it — decision/governance not established | *Hypothesis:* distinguish continuous alignment from scope creep against a shared record | Hypothesis / roadmap candidate |

---

## 10. Coverage check (DIV-54 acceptance)

- **Every `CAP` has links 5–6.** CAP-01…CAP-07 each carry a Specsight capability and a customer
  value; via §1's partition this completes the six-link chain for all 25 failure modes.
- **Validated vocabulary only.** No link-5 cell uses generic marketing language ("improve
  collaboration", "streamline workflows"); each uses the research's vocabulary (persistent
  behavioral model, implementation-aware behavioral summary, traceable behavioral validation,
  behavioral traceability, one behavioral view).
- **The four persona capabilities are present and extended.** Persona A/B/C/D are CAP-01/03/05/06
  verbatim; CAP-02 and CAP-04 extend them with validated language; CAP-07 is explicitly a
  hypothesis, not invented product detail.
- **Assessable descriptions.** Each validated link-5 describes what Specsight does or could do
  specifically enough to be scored against the product in §3; CAP-07 is flagged as the one that
  cannot be met by the current capability set.
- **Traceable end-to-end.** The chain traces failure mode → value for at least three
  stage-spanning examples: CAP-01 (Requirements), CAP-03 (Sprint Review), CAP-06 (Production).

The complete chain is assessed against Specsight's current maturity in
[§3](03-capability-gap-assessment.md).

---

*Previous: [Section 1 — Failure-Mode-to-Capability Map (links 1–4)](01-failure-mode-to-capability-map.md) · Next: [Section 3 — Capability Gap Assessment (roadmap input)](03-capability-gap-assessment.md)*
