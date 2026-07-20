# Layer 2 · Section 5 — Framework-5 Separation & Underserved-by-Tools Gaps

> **Role in the library:** The **cross-cutting synthesis** that runs across every entry in
> §1–§4. It does not create new failure modes — it applies **Framework 5** (separating expert
> best practice from observable practitioner pain) consistently across all 25 entries, assigns
> each an underserved-by-existing-tools assessment, and identifies the underserved set as
> Specsight's strongest opening and the next research frontier.
>
> **Owning subtask:** DIV-59.
> **Source basis:** Framework 5 from Document 2; the underserved signals from Documents 7, 8,
> and 2; the entries catalogued in §1–§4.
> **Out of scope here:** creating new entries (§1–§4), the schema (§0), mapping to Specsight
> capabilities (DIV-34), deriving buying triggers (DIV-35).

---

## 1. Framework 5 — the methodological shift

Document 2's Framework 5 established the methodology for all the failure-mode research:
**"Rather than studying frameworks, study where practitioners complain."** Every entry in this
library therefore carries two deliberately separated fields:

- **`expert_best_practice`** — what published frameworks, company handbooks (Microsoft,
  GitLab, Atlassian, GitHub, Shopify, Amazon), and thought leaders (Mike Cohn, Joel
  Bancroft-Connors, Maarten Dalmijn, Roman Pichler, Barry Overeem, Stefan Wolpers, Lenny
  Rachitsky, Shreyas Doshi, Saurabh Juneja) say *should* happen. The theoretical ideal.
- **`practitioner_pain`** — what the research found *actually* happens in practice, from
  practitioner discussions and operational observation. The observable operational reality.

The pivotal observation to apply throughout is Document 7's: **"practitioners consistently
discuss operational symptoms, while almost nobody frames the larger problem as a cohesive
validation capability or operating practice."** GTM that targets the *practitioner_pain* side
speaks to real friction; GTM that targets only the *expert_best_practice* side sells theory.

---

## 2. Framework-5 separation matrix (all 25 failure modes)

For each failure mode: the expert source it references (top of the separation) vs the
observable operational pain (bottom). `separation_rationale` is why the distinction matters for
GTM. Full field content lives in the per-entry sections (§1–§4); this is the consolidated view.

| FM | Failure mode | Expert best practice (source) | Practitioner pain (observable) | Why the separation matters for GTM |
| --- | --- | --- | --- | --- |
| FM-01 | Ambiguous Acceptance Criteria | Microsoft/GitLab/Atlassian collaborative AC + DoD checklist (Doc 6) | AC agreed only nominally; same story built to different mental models | Prospects don't ask for "better AC practice"; they complain stories are interpreted differently |
| FM-02 | Subjective PO Approval | Evidence-based acceptance embedded in DoD (Doc 6) | Signoff is a judgment call because agreed evidence isn't assembled | The pain is "acceptance is subjective," not "adopt evidence-based DoD" |
| FM-03 | Missing Evidence | Product-type evidence catalogue (Doc 6) | No agreed sufficient-evidence standard; "done" is asserted | Prospects feel "we can't prove it's done," not "we lack an evidence taxonomy" |
| FM-04 | Late Validation | Continuous validation throughout delivery (CN-07, Doc 7) | Validation deferred to the review gate; expensive to fix | The complaint is "we find out too late," not "shift-left your validation" |
| FM-05 | Unclear Ownership | Acceptance ownership embedded in DoD + Three Amigos (Doc 6) | Responsibility fragmented across PM/QA/Eng; verification inconsistent | The pain is "whose call is this?", not "define an ownership model" |
| FM-06 | Demo Difficulties | Evidence-based acceptance over happy-path demo (Doc 6) | Demos hide edge cases; PM depends on eng to explain the build | Prospects say "demos hide the truth," not "replace demos with evidence" |
| FM-07 | QA–Product–Eng Misalignment | Three Amigos shared understanding before build (Doc 6/7) | Three roles verify different things; passing work misses intent | The pain is "QA passed but it's wrong," not "align your three amigos" |
| FM-08 | Implementation Drift | Refinement as ongoing shared understanding (Cohn, Dalmijn, Bancroft-Connors, Doc 3) | Refinement stops after planning; build diverges from intent | The complaint is "it drifted from what we wanted," not "do continuous refinement" |
| FM-09 | Skipped Refinement | "Continuously maintain shared understanding" shift (Doc 5 Pt 3) | Refinement treated as one-and-done; understanding decays | Prospects feel decay mid-sprint, not the absence of a named practice |
| FM-10 | Blocked Engineering | Story Clarification + Three Amigos before build (Doc 3) | Under-refined stories block eng; wait or guess | The pain is "we're blocked / we guessed," not "refine more upfront" |
| FM-11 | Velocity Loss | Continuous shared understanding avoids rework (Doc 3) | Velocity eroded by rework, re-clarification, failed acceptance | The complaint is "we're slowing down," not "reduce misalignment" |
| FM-12 | Developers Interpreting Differently | Shared understanding of intent (Three Amigos, Doc 9) | Each dev resolves ambiguity alone; divergent implementations | Prospects say "everyone read it differently," not "build shared understanding" |
| FM-13 | Clarification vs Scope Creep Confusion | Clarification-vs-requirement-evolution rule (Doc 8) | No shared model; scope creeps in disguised as clarification | The pain is "scope crept," not "adopt the clarification boundary" |
| FM-14 | Refinement Boundary Gap | Continuous Product Alignment over the middle (Doc 8) | Execution middle unowned; intent maintained informally, validated late | The frontier: under-documented *and* under-tooled — the strongest opening |
| FM-15 | Requirement Evolution w/o Shared Understanding | Maintain shared understanding as reqs evolve (Doc 9) | Requirements move faster than understanding; intent and execution diverge | The complaint is "we built the old version," not "version your understanding" |
| FM-16 | Two-Loop Conflation | Explicit separation of the two loops (Doc 8) | Loops run as one; verification drifts into discovery | The pain is "scope reopened at review," not "separate your loops" |
| FM-17 | Schools-of-Practice Tension | Draw an explicit clarification/new-requirement boundary (Doc 9) | Teams straddle two philosophies without a boundary | The pain is recurring process debate, not "pick a school" |
| FM-18 | Implementation Drift (cross-stage) | Reflect implementation decisions back into intent (Doc 2) | Decisions never reflected back; record and reality diverge | Observable signal: "PMs becoming translators" — no tool addresses it |
| FM-19 | Validation Drift | Validate end-to-end customer outcomes (Doc 2) | QA loses business intent; passing validation misses the point | The pain is "tests pass but customers don't," not "test outcomes" |
| FM-20 | Reality Drift | Validate actual customer behavior in real conditions (Doc 2) | UAT validates expected, not actual, behavior | The pain is "production surprised us," not "improve UAT coverage" |
| FM-21 | Learning Drift | Persistent link production → intent; Commercial Learning Loop (Doc 1/2) | Learning re-synthesized by hand from scattered systems | The pain is "learnings are lost," not "close the loop" |
| FM-22 | Context Reconstruction @ Requirements | Remove the re-translation tax (Doc 2) | PM rebuilds/re-translates requirement context by hand | Observable signal: "PMs becoming translators instead of strategists" |
| FM-23 | Context Reconstruction @ Sprint Review | "What changed" directly comparable to intent (Doc 2) | PM reconstructs the build from demos, Jira, eng explanations | Observable signal: "Release meetings getting longer" |
| FM-24 | Context Reconstruction @ UAT | Assemble release evidence without chasing it (Doc 2) | Every release reassembles scattered evidence for Go/No-Go | Observable signal: Go/No-Go driven by meetings and manual comms |
| FM-25 | Context Reconstruction @ Production | Connect customer issues to implementation changes (Doc 2) | Every investigation rebuilds context from separate tools | Observable signals: "Support asks Product what changed"; "knowledge is tribal" |

> **Consistency check (DIV-59 acceptance):** no entry conflates the two halves — every
> `expert_best_practice` above names a specific framework, handbook, or thought leader, and
> every `practitioner_pain` describes an observable operational reality, not a theoretical gap.

---

## 3. Underserved-by-existing-tools matrix

For each failure mode: the assessment, the existing tools evaluated, and the rationale. Tools
evaluated across the library: **Jira / Azure DevOps** (issue tracking, AC as free text,
blocked-status flags), **test-management & CI tools** (functional verification, evidence
fragments), **demo / screenshare tools** (happy-path demonstration), **analytics platforms**
(post-hoc production behavior), and **collaboration tools** (Slack, docs — where intent
informally lives).

| FM | Assessment | Existing tools evaluated | Rationale |
| --- | --- | --- | --- |
| FM-01 | Partially served | Jira, Azure DevOps | Store AC as free text; don't test for ambiguity or confirm shared understanding |
| FM-02 | Underserved | Jira, test tools | No tool assembles the evidence a PO needs; acceptance lives in meetings |
| FM-03 | Underserved | test-management, CI | Produce evidence in fragments; none defines/assembles the sufficient-evidence set |
| FM-04 | Partially served | CI, test tools | Run tests continuously but don't validate implementation against product intent |
| FM-05 | Partially served | Jira, Azure DevOps | Model assignee/status, not acceptance ownership across PM/QA/Eng |
| FM-06 | Underserved | demo/screenshare tools | Show the happy path; nothing surfaces the omitted edge cases |
| FM-07 | Underserved | test tools, Jira | Verify functionality and track status; don't align QA's check with Product's intent |
| FM-08 | Underserved | Jira, docs | Nothing reflects mid-sprint implementation decisions back into product artifacts |
| FM-09 | Underserved | Jira (ceremonies) | Schedule refinement as a ceremony; don't maintain shared understanding continuously |
| FM-10 | Partially served | Jira | Flags blocked status but doesn't resolve the clarification gap |
| FM-11 | Partially served | Jira (velocity charts) | Measure the loss after the fact; don't address the misalignment causing it |
| FM-12 | Underserved | Jira, docs | Store one story text; don't confirm shared interpretation of it |
| FM-13 | Underserved | Jira, collaboration tools | No tool helps decide, in the moment, clarification vs new requirement |
| FM-14 | Underserved | (frameworks/tools stop before the middle) | Under-documented → under-tooled; no tool owns the execution middle |
| FM-15 | Underserved | Jira (versioning) | Version the requirement text; don't maintain/verify shared understanding of it |
| FM-16 | Partially served | Jira, Azure DevOps | Model a single linear workflow, not two loops with a boundary |
| FM-17 | Underserved | (methodology tooling) | No tool locates a team on the Scrum↔Product-led spectrum or runs a chosen boundary |
| FM-18 | Underserved | Jira, docs, analytics | Observable signal ("PMs becoming translators") no tool addresses holistically |
| FM-19 | Underserved | test tools | Verify functionality; none connects validation to business intent / customer workflows |
| FM-20 | Underserved | analytics platforms | Observe production after the fact; don't connect it to release-readiness decisions |
| FM-21 | Underserved | analytics, support, CRM | Data live in separate tools; nothing links production learning back to intent |
| FM-22 | Underserved | Jira, docs, Slack | Re-translation done by hand; no tool removes the requirements-stage tax |
| FM-23 | Underserved | Jira, demo tools | PM reconstructs the build manually; no tool makes "what changed" comparable to intent |
| FM-24 | Underserved | QA/release tools, spreadsheets | Business acceptance combines many systems; no tool assembles release readiness |
| FM-25 | Underserved | analytics, support, incident tools | Data live in separate tools; none connects customer issues to implementation changes |

The library-wide pattern is exactly what the research predicted: existing tools address
**individual stages** (Jira for requirements, test tools for QA, analytics for production) but
**no tool connects intent → implementation → validation → customer outcomes.** Per Document 7,
tools address individual symptoms but "almost nobody frames the larger problem as a cohesive
validation capability."

---

## 4. Summary — where Specsight's opening is (the next research frontier)

Across the 25 failure modes: **19 are Underserved, 6 are Partially served, 0 are adequately
served.** That distribution is itself a finding — the whole library sits in territory existing
tools do not cover cohesively.

### 4a. Fully underserved — Specsight's strongest opening (19)

FM-02, FM-03, FM-06, FM-07, FM-08, FM-09, FM-12, FM-13, FM-14, FM-15, FM-17, FM-18, FM-19,
FM-20, FM-21, FM-22, FM-23, FM-24, FM-25.

These cluster into three high-value bands:

1. **The refinement boundary gap (FM-08, FM-09, FM-10*, FM-12, FM-13, FM-14, FM-15, FM-17)** —
   the under-documented, under-tooled execution middle Layer 1 Section 5 names as the frontier.
   FM-14 is the anchor: it is under-documented *and* under-tooled, the single strongest opening.
   *(FM-10 is Partially served but sits in this band.)*
2. **Evidence & acceptance objectivity (FM-02, FM-03, FM-06, FM-07)** — the AC/DoD stage
   failures where acceptance is subjective because product-appropriate evidence isn't assembled.
3. **The Context Reconstruction Tax and cross-stage drift (FM-18–FM-25)** — the lifecycle-wide
   cost of intent, implementation, validation, and customer reality living in disconnected
   systems, surfaced as observable signals ("PMs becoming translators," "Release meetings
   getting longer," "Support asks Product what changed," "knowledge is tribal," "Slack becomes
   the source of truth") that no tool addresses holistically.

### 4b. Partially served — real but contested openings (6)

FM-01, FM-04, FM-05, FM-10, FM-11, FM-16. Existing tools touch a symptom (AC storage, CI,
blocked-status, velocity charts, linear workflow) but not the cohesive problem. Credible
openings, but a prospect may believe their current tool "already does this."

### 4c. Adequately served (0)

No failure mode in the library is adequately served by existing tools — consistent with the
research thesis that the cohesive validation/alignment capability is precisely what the market
lacks.

### 4d. The next research frontier

Per the parent task, the underserved set — anchored on **the refinement boundary gap (FM-14)**
and the **Context Reconstruction Tax (FM-22–FM-25)** — is the next research frontier: the zone
where practitioner pain concentrates, existing tools are absent, and (per Layer 1 Section 5)
buying triggers are most likely to fire and Specsight's continuous-alignment capability is most
differentiated. Layers 3 (Capability Graph, DIV-34) and 4 (Buying Trigger Graph, DIV-35) do
their most valuable work against these underserved `FM-NN` ids.

> **Scope boundary:** this synthesis stops at *assessing* the underserved gap. Naming the
> Specsight capability that fills it is DIV-34; deriving the buying trigger from it is DIV-35.

---

*Previous: [Section 4 — Cross-stage drift taxonomy & Context Reconstruction Tax](04-cross-stage-drift-and-context-reconstruction-tax.md) · Back to [Layer 2 hub](../layer-2-failure-mode-library.md)*
