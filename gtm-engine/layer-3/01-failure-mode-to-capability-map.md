# Layer 3 · Section 1 — Failure-Mode-to-Capability Map (Links 1–4)

> **Role in the Capability Graph:** Populates **links 1–4** of the `CapabilityMappingChain`
> ([§0](00-capability-mapping-chain-schema.md)) for **every** failure mode in the Failure Mode
> Library: failure mode → missing capability → current workaround → existing alternatives. It
> also establishes the `CAP-NN` registry that §2 and §3 build on.
>
> **Owning subtask:** DIV-49.
> **Consumes:** Layer 2 `FM-01…FM-25` (name, `workflow_stage`, `current_workarounds`, and the
> underserved matrix's "existing tools evaluated") and Document 2's maturity-level tool
> inventory.
> **Applies:** Framework 2 (Failure Mode → Missing Capability) — a *capability*, never a
> feature or a generic problem.
> **Out of scope here:** naming Specsight capabilities / customer value (§2, DIV-54), the gap
> assessment (§3, DIV-57), re-cataloguing failure modes (Layer 2 owns symptoms/evidence).

---

## 1. Framework 2 in one line

Every failure mode is translated to the **capability the team is missing**, not to a problem
or a product feature. Following Document 2: not *"Poor requirements"* but *"Missing continuous
alignment capability"*; not *"Better demo tool"* but *"Automatic comparison of intent vs
implemented behavior"*. The 25 failure modes collapse into **seven distinct missing
capabilities** because many breakdowns are the same capability gap seen at different stages.

---

## 2. The `CAP-NN` registry (the seven missing capabilities)

Each `CAP` is a distinct capability gap; its member `FM` ids are the Layer 2 failure modes
that manifest it. The partition is total (all 25 `FM` ids) and non-overlapping.

| `CAP` | Missing capability (link 2, Framework 2 framing) | Member `FM` ids | Persona anchor |
| --- | --- | --- | --- |
| **CAP-01** | **Persistent representation of customer intent** — a shared, persistent representation of what the product should do that stays authoritative as work proceeds (not free-text AC re-interpreted per reader). | FM-01, FM-12, FM-15, FM-22 | Persona capability **A** |
| **CAP-02** | **Continuously maintained shared understanding during execution** — the continuous-alignment capability that keeps product intent and engineering execution aligned *through the refinement boundary gap*, not just at planning. | FM-09, FM-10, FM-11, FM-14 | Extends A into execution (Layer 1 §5 frontier) |
| **CAP-03** | **Automatic comparison of intent vs implemented behavior** — the capability to see what was actually built and how it differs from intended behavior, without reconstructing it by hand. | FM-04, FM-06, FM-08, FM-18, FM-23 | Persona capability **B** |
| **CAP-04** | **Shared behavioral understanding across Product, QA & Engineering** — a single behavioral view all three roles verify against, so functional checks and intent checks align. | FM-05, FM-07 | Trigger table "Shared behavioral understanding" |
| **CAP-05** | **Traceable behavioral validation (AC → validated behaviors)** — the capability to see which agreed behaviors are validated, partially validated, or unverified, with assembled evidence. | FM-02, FM-03, FM-19, FM-20, FM-24 | Persona capability **C** |
| **CAP-06** | **Continuous traceability from intent → implementation → validation → customer outcomes** — a persistent link from production behavior back to implemented features and original intent. | FM-21, FM-25 | Persona capability **D** |
| **CAP-07** | **Operational clarification-vs-requirement-evolution boundary** — the capability to decide, in the moment and with a shared record, whether a change is clarification (no AC change) or requirement evolution (new backlog work), and to keep the two loops distinct. | FM-13, FM-16, FM-17 | Framework 5 / Document 8 boundary rule |

> **Partition rationale.** CAP-01 gathers the *shared-intent* failures (ambiguous AC,
> divergent interpretation, requirement evolution outrunning understanding, requirements-stage
> re-translation). CAP-02 gathers the *execution-middle* failures Layer 1 §5 names as the
> frontier (skipped refinement, blocked engineering, velocity loss, the refinement boundary
> gap itself). CAP-03 gathers the *intent-vs-build comparison* failures (per the Layer 2
> hub cross-stage note, FM-08 and FM-18 are one gap). CAP-05 gathers the *evidence &
> validation* failures. CAP-04, CAP-06, and CAP-07 gather the shared-view, production-loop,
> and boundary-governance failures respectively. The four persona capabilities (A/B/C/D) map
> exactly to CAP-01/03/05/06; CAP-02, CAP-04, and CAP-07 **extend** the four to cover all 25
> failure modes rather than dropping any.

---

## 3. CAP-01 · Persistent representation of customer intent

**Missing capability (link 2):** a persistent, shared representation of *intended behavior*
that all roles work from and that stays current as understanding evolves — so the same story is
not implemented and accepted against different mental models.

| `FM` | Failure mode (link 1) | Current workaround (link 3) | Existing alternatives (link 4) | Stage · Loop |
| --- | --- | --- | --- | --- |
| FM-01 | Ambiguous Acceptance Criteria — the same story is built to different mental models | Ad hoc clarification meetings; asking engineering to explain what was built; manual back-and-forth to reconcile interpretations | AC as free text in Jira / Azure DevOps; PRDs, Figma (Level 1 Planning) | AC / DoD · Discovery/Refinement |
| FM-12 | Developers interpreting stories differently — divergent implementations of one story | More detailed written stories; manual reconciliation when interpretations diverge; asking engineering which interpretation was taken | One story text in Jira / docs (no confirmation of shared interpretation) | Implementation / Continuous Collaboration · Discovery/Refinement |
| FM-15 | Requirement evolution without shared understanding — reqs move faster than understanding | Manual re-communication of the evolved requirement; re-sync meetings; updating docs and hoping everyone re-reads | Requirement-text versioning in Jira; docs | Discovery / Refinement Loop · Discovery/Refinement |
| FM-22 | Context Reconstruction @ Requirements — PM rebuilds/re-translates requirement context by hand | PM rewrites requirements and manually reconciles feasibility with intent; repeated alignment meetings to translate intent | Jira, docs, Slack (intent lives informally) | Requirements / Backlog Refinement · Discovery/Refinement |

---

## 4. CAP-02 · Continuously maintained shared understanding during execution

**Missing capability (link 2):** a continuous-alignment capability that maintains shared
understanding of intent *during* implementation — the under-tooled execution middle between
"ready for development" and Sprint Review (Layer 1 §5). This is Specsight's most differentiated
zone.

| `FM` | Failure mode (link 1) | Current workaround (link 3) | Existing alternatives (link 4) | Stage · Loop |
| --- | --- | --- | --- | --- |
| FM-09 | Skipped Refinement — refinement treated as one-and-done; understanding decays mid-sprint | Emergency clarification meetings; engineers proceed on their own interpretation; more upfront documentation | Refinement scheduled as a Jira ceremony (no continuous mechanism) | Implementation / Continuous Collaboration · Discovery/Refinement |
| FM-10 | Blocked Engineering — under-refined stories block engineering | Engineers guess and proceed (feeding drift); ad hoc clarification pings; pulling in other work while blocked | Jira blocked-status flags | Implementation / Continuous Collaboration · Discovery/Refinement |
| FM-11 | Velocity Loss — rework, re-clarification, and failed acceptance erode throughput | Adding estimate buffer; more pre-emptive meetings; PM absorbing requirement-rewriting load | Jira velocity charts (measure the loss after the fact) | Implementation / Continuous Collaboration · Discovery/Refinement |
| FM-14 | Refinement Boundary Gap — the execution middle is unowned; intent maintained informally, validated late | Informal ad hoc alignment during execution; relying on the demo as first real validation; individual PMs improvising a mid-sprint check | (frameworks/tools stop before the middle) Slack, hallway conversations, demos | Verification / Acceptance Loop *(spans the boundary)* · Verification/Acceptance |

---

## 5. CAP-03 · Automatic comparison of intent vs implemented behavior

**Missing capability (link 2):** the capability to see *what was actually built* and how it
differs from intended behavior — surfacing changed workflows, edge cases, and undocumented
deviations — without the PM reconstructing it from demos and engineering explanations.

| `FM` | Failure mode (link 1) | Current workaround (link 3) | Existing alternatives (link 4) | Stage · Loop |
| --- | --- | --- | --- | --- |
| FM-04 | Late Validation — the first real check against intent is the demo | Batch validation at sprint end; extending Sprint Review to absorb validation; hotfix cycles after late discovery | CI / test tools (run tests, but don't validate implementation against product intent) | AC / DoD · Verification/Acceptance |
| FM-06 | Demo Difficulties — demos show happy paths and hide edge cases; PM depends on eng to explain the build | PM accepts on the demo; post-demo Q&A to reconstruct what was built; manually probing skipped edge cases | Demo / screenshare tools (happy path only) | AC / DoD · Verification/Acceptance |
| FM-08 | Implementation Drift — refinement stops after planning; the build silently diverges from intent | PM validates through demos after the fact; retroactive artifact updates; asking eng to explain mid-sprint decisions | Jira, product docs, demos (nothing reflects decisions back into artifacts) | Implementation / Continuous Collaboration · Verification/Acceptance |
| FM-18 | Implementation Drift (cross-stage) — implementation decisions never reflected back into intent (**one gap with FM-08**) | "Engineers interpret requirements and implement them; PM validates primarily through demos"; post-hoc artifact updates | Jira, docs, analytics ("PMs becoming translators") | Requirements / Backlog Refinement · Verification/Acceptance |
| FM-23 | Context Reconstruction @ Sprint Review — PM reconstructs the build from demos, Jira, and eng explanations | "Watches demos and accepts work"; reconstructing what changed from demos, Jira, and engineering explanations | Jira, demo tools, GitHub PRs, release notes, engineering walkthroughs | Sprint Review · Verification/Acceptance |

---

## 6. CAP-04 · Shared behavioral understanding across Product, QA & Engineering

**Missing capability (link 2):** a single behavioral view of intended and implemented behavior
that Product, QA, and Engineering all verify against — so functional correctness and business
intent are checked against the same understanding, and acceptance ownership is legible.

| `FM` | Failure mode (link 1) | Current workaround (link 3) | Existing alternatives (link 4) | Stage · Loop |
| --- | --- | --- | --- | --- |
| FM-05 | Unclear Ownership — acceptance responsibility fragmented across PM / QA / Eng | Convening all three roles to co-own by committee; informal per-team sign-off norms; PM absorbing reconciliation by default | Jira / Azure DevOps model assignee & status, not acceptance ownership | AC / DoD · Verification/Acceptance |
| FM-07 | QA–Product–Engineering Misalignment — the three roles verify different things; passing work misses intent | Manual reconciliation of QA results against business intent; extra alignment meetings; PM re-checking QA-passed work by hand | Test tools (verify functionality) + Jira (track status) — neither aligns QA's check with Product's intent | AC / DoD · Verification/Acceptance |

---

## 7. CAP-05 · Traceable behavioral validation (AC → validated behaviors)

**Missing capability (link 2):** the capability to trace validated behaviors back to the
agreed acceptance criteria and customer workflows — surfacing what is validated, partially
validated, or unverified, with the sufficient evidence assembled rather than asserted.

| `FM` | Failure mode (link 1) | Current workaround (link 3) | Existing alternatives (link 4) | Stage · Loop |
| --- | --- | --- | --- | --- |
| FM-02 | Subjective Product Owner Approval — signoff is a judgment call because agreed evidence isn't assembled | PO accepts on a demo; verbal reassurance from eng substitutes for evidence; extra sign-off meetings | Jira + test tools (acceptance lives in meetings) | AC / DoD · Verification/Acceptance |
| FM-03 | Missing Evidence — no agreed sufficient-evidence standard; "done" is asserted | Manually collecting screenshots/logs/test results per story; relying on QA's word; accepting without evidence and reopening later | Test-management & CI tools (evidence in fragments) | AC / DoD · Verification/Acceptance |
| FM-19 | Validation Drift — QA verifies what was implemented but loses business intent and customer workflows | "QA creates test cases from stories and acceptance criteria"; manual reconciliation of QA results against business intent | Test tools, QA reports (verify functionality, not customer outcomes) | Sprint Review · Verification/Acceptance |
| FM-20 | Reality Drift — UAT validates expected, not actual, behavior | "Release approved on test evidence; product monitors analytics after launch"; post-launch firefighting on uncovered scenarios | Analytics platforms (observe production after the fact, disconnected from release readiness) | UAT / Release Readiness · Verification/Acceptance |
| FM-24 | Context Reconstruction @ UAT — every release reassembles scattered evidence for Go/No-Go | "Reviews QA and release status"; reassembling evidence from QA, Engineering, and Operations to make the release call | QA / release tools, spreadsheets (business acceptance combines many systems) | UAT / Release Readiness · Verification/Acceptance |

---

## 8. CAP-06 · Continuous traceability from intent → implementation → validation → customer outcomes

**Missing capability (link 2):** a persistent link from production behavior back to implemented
features and original product intent — so customer observations connect to the behavioral
changes and releases that caused them, without rebuilding context from scratch each cycle.

| `FM` | Failure mode (link 1) | Current workaround (link 3) | Existing alternatives (link 4) | Stage · Loop |
| --- | --- | --- | --- | --- |
| FM-21 | Learning Drift — no persistent link from production observations to original intent; learning re-synthesized by hand | "PM reviews dashboards, support tickets, incidents, interviews, analytics"; manual synthesis of scattered learnings into the next requirements | Analytics, support, CRM, incident reviews (Level 3 Operations, in separate tools) | Production Review · Cross-loop (lifecycle-spanning) |
| FM-25 | Context Reconstruction @ Production — every investigation rebuilds context from separate tools | "Looks at dashboards and support tickets"; manually correlating releases with customer behavior across separate tools | Analytics, support, incident tools (data live in separate tools) | Production Review · Cross-loop (lifecycle-spanning) |

---

## 9. CAP-07 · Operational clarification-vs-requirement-evolution boundary

**Missing capability (link 2):** the capability to decide, in the moment and with a shared
record, whether a mid-flight change is *clarification* (no AC change) or *requirement
evolution* (new backlog work) — and to keep the discovery and verification loops distinct so
scope does not creep in disguised as clarification.

| `FM` | Failure mode (link 1) | Current workaround (link 3) | Existing alternatives (link 4) | Stage · Loop |
| --- | --- | --- | --- | --- |
| FM-13 | Clarification vs Scope Creep Confusion — no shared model; scope creeps in disguised as clarification | Ad hoc case-by-case scope negotiation; informal story splitting; alignment meetings to adjudicate the line | Jira, collaboration tools / Slack (no in-the-moment clarification-vs-new-requirement decision) | Discovery / Refinement Loop · Discovery/Refinement |
| FM-16 | Two-Loop Conflation — verification drifts into discovery; scope reopens at the acceptance gate | Absorbing discovery into acceptance meetings; re-opening scope at review; informal separation depending on facilitator | Jira / Azure DevOps model a single linear workflow, not two loops with a boundary | Verification / Acceptance Loop · Verification/Acceptance |
| FM-17 | Schools-of-Practice Tension — teams straddle Traditional-Scrum vs Product-led without a boundary | Informally picking one philosophy; case-by-case negotiation of "enough" refinement; blending both without an explicit model | (methodology tooling — none locates a team on the spectrum or runs a chosen boundary) | Discovery / Refinement Loop · Discovery/Refinement |

---

## 10. Coverage check (DIV-49 acceptance)

- **All 25 failure modes mapped.** FM-01…FM-25 each appear in exactly one `CAP` (§3–§9);
  4 + 4 + 5 + 2 + 5 + 2 + 3 = 25.
- **Framework 2 respected.** Every link-2 statement is a *capability* ("persistent
  representation of customer intent", "automatic comparison of intent vs implemented
  behavior"), never a problem ("poor requirements") or a feature ("better demo tool").
- **Workarounds trace to source.** Every link-3 cell is drawn from a Layer 2 entry's
  `current_workarounds` or Document 2's "Current Process" language.
- **Alternatives are specific.** Every link-4 cell names concrete tools/ceremonies (Jira,
  Figma, demos, GitHub PRs, analytics, support/incident tools), aligned to the maturity-level
  inventory, not generic categories.
- **The four persona capabilities are present and extended.** A→CAP-01, B→CAP-03, C→CAP-05,
  D→CAP-06; CAP-02/04/07 extend them to cover all failure modes, not just the four PM
  lifecycle stages.
- **Consolidation honored.** FM-08 and FM-18 share `CAP-03` as one gap (Layer 2 hub cross-stage
  note).

Links 5–6 (Specsight capability + customer value) are completed for every `CAP` in
[§2](02-specsight-capability-and-customer-value.md).

---

*Previous: [Section 0 — Schema & Cross-Referencing Contract](00-capability-mapping-chain-schema.md) · Next: [Section 2 — Specsight Capability & Customer Value (links 5–6)](02-specsight-capability-and-customer-value.md)*
