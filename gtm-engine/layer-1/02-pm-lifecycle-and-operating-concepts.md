# Layer 1 · Section 2 — PM Lifecycle Stages & Operating-Model Concepts

> **Role in the knowledge graph:** This is the **node-and-edge core** of the Industrial
> Knowledge Graph. Each concept below is a structured *node*; the relationship map at the
> end defines the *edges* between them. Downstream layers (Failure Mode Library DIV-33,
> Capability Graph DIV-34, Buying Trigger Graph DIV-35) attach their entries to the node
> IDs defined here.
>
> **Source:** Documents 3–7 (with the evidence-type catalogue from Document 6).
> **Owning subtask:** DIV-42.
> **Out of scope here:** the research narrative (Section 1), the two loops / CPA operating
> model (Section 3), company-specific implementations (Section 4), the refinement boundary
> gap (Section 5), and any failure modes / capability gaps (sibling parents DIV-33/34/35).

---

## How to read a concept node

Every concept is documented with the same nine fields so it can be referenced uniformly:

| Field | Meaning |
| --- | --- |
| **Node ID** | Stable identifier for cross-referencing from downstream layers |
| **Question it answers** | The single question the concept exists to resolve |
| **Purpose** | What the concept achieves in the delivery lifecycle |
| **Key activities** | The constituent activities that comprise it |
| **Artifacts produced** | What tangible outputs it creates |
| **Roles involved** | Who participates |
| **Decision points** | Where decisions are made within it |
| **Review mechanisms** | How work is reviewed within it |
| **Relationships** | Which concepts feed into / depend on it (the edges) |
| **Source documents** | Where it was identified or validated |

---

## CN-01 · Backlog Refinement

- **Question it answers:** *What should we build (and is it ready to build)?*
- **Purpose:** Continuously prepare and clarify upcoming backlog items so work is understood
  before implementation begins. Anchor activity of the Discovery/Refinement loop (Section 3).
- **Key activities:** Story Refinement, Three Amigos, Example Mapping, Story Splitting,
  scope negotiation.
- **Artifacts produced:** Refined/"ready" backlog items, split stories, initial Acceptance
  Criteria drafts, shared examples.
- **Roles involved:** Product Manager / Product Owner, Engineering, QA.
- **Decision points:** Whether a story is "ready for development"; how to split a story;
  what is in vs out of scope.
- **Review mechanisms:** Team review of refined items against a readiness/"ready" standard.
- **Relationships:** Umbrella that contains **CN-02 Three Amigos** and **CN-03 Story
  Clarification**; feeds **CN-04 Acceptance Criteria**; is one observable manifestation of
  **Continuous Product Alignment** (Section 3).
- **Source documents:** Doc 5 (terminology), Doc 8 (positioned within the Discovery loop).

## CN-02 · Three Amigos

- **Question it answers:** *Do Product, Engineering, and QA share the same understanding of
  this story?*
- **Purpose:** Bring the three perspectives together to build shared understanding of a story
  before it is built, surfacing ambiguity early.
- **Key activities:** Joint story review across Product, Engineering, and QA; example
  mapping; edge-case discovery.
- **Artifacts produced:** Shared understanding, clarified/expanded Acceptance Criteria,
  documented examples and edge cases.
- **Roles involved:** Product (Owner/Manager), Engineering, QA — the "three amigos."
- **Decision points:** Whether the story is understood well enough to proceed; which edge
  cases must be handled.
- **Review mechanisms:** Cross-functional conversation as the review of shared understanding.
- **Relationships:** An activity within **CN-01 Backlog Refinement**; overlaps **CN-03 Story
  Clarification**; sharpens **CN-04 Acceptance Criteria**.
- **Source documents:** Docs 3 (identified as where implementation-validation work lives),
  5 (terminology adopted).

## CN-03 · Story Clarification

- **Question it answers:** *What exactly does this story mean?*
- **Purpose:** Resolve ambiguity in a story's intent so it can be implemented as agreed —
  distinct from *changing* the intent (see Clarification vs Requirement Evolution, Section 3).
- **Key activities:** Question-and-answer on intent, worked examples, tightening wording of
  Acceptance Criteria.
- **Artifacts produced:** Clarified story, updated examples, shared understanding notes.
- **Roles involved:** Product Owner / Product Manager, Engineering, QA.
- **Decision points:** Whether a question is a *clarification* (no AC change) or a
  *requirement evolution* (new backlog work) — the boundary defined in Section 3.
- **Review mechanisms:** Confirmation that the clarified understanding matches original intent.
- **Relationships:** Activity within **CN-01 Backlog Refinement**; closely tied to **CN-02
  Three Amigos**; governed by the Clarification vs Requirement Evolution boundary (Section 3).
- **Source documents:** Docs 3, 5.

## CN-04 · Acceptance Criteria (AC)

- **Question it answers:** ***"What should the feature do?"*** (per Document 6).
- **Purpose:** Define, per story, the specific behavior the feature must exhibit — the
  agreed statement of *what* is being built.
- **Key activities:** Writing per-story criteria; specifying expected behavior and examples;
  agreeing them with the team.
- **Artifacts produced:** Per-story Acceptance Criteria.
- **Roles involved:** Product Owner / Product Manager (owns), Engineering and QA (co-define
  and verify against).
- **Decision points:** Whether criteria are unambiguous and testable; what evidence will
  demonstrate satisfaction (see evidence-type catalogue below).
- **Review mechanisms:** Team agreement on AC during refinement; verification against AC
  during acceptance.
- **Relationships:** Produced during **CN-01 Backlog Refinement**; sharpened by **CN-02 /
  CN-03**; distinct from **CN-05 Definition of Done** (feature behavior vs increment
  readiness); verified in the Verification/Acceptance loop (Section 3); its evidence types
  are catalogued below.
- **Source documents:** Docs 5 (terminology), 6 (definition and evidence catalogue).

## CN-05 · Definition of Done (DoD)

- **Question it answers:** ***"Is the increment ready to ship?"*** (per Document 6).
- **Purpose:** Define the increment-level standard that must be met before work is
  considered complete and shippable — distinct from *what* a feature does.
- **Key activities:** Applying a shared done-checklist to the increment; verifying quality,
  testing, documentation, and evidence gates.
- **Artifacts produced:** Increment-level DoD checklist; a "done" determination.
- **Roles involved:** Whole delivery team; Product Owner acceptance is generally **embedded
  within DoD** rather than a separate workflow (Document 6 finding).
- **Decision points:** Whether every done-criterion is met; whether required evidence exists.
- **Review mechanisms:** Checklist verification at increment completion; the point at which
  Product Owner acceptance occurs (see CN-06).
- **Relationships:** Applies across stories that satisfy **CN-04 Acceptance Criteria**;
  **embeds CN-06 Product Owner Acceptance**; verified in the Verification/Acceptance loop
  (Section 3); shares the evidence-type catalogue below.
- **Source documents:** Docs 5 (terminology), 6 (definition, PO-embedding, evidence catalogue).

## CN-06 · Product Owner Acceptance

- **Question it answers:** *Does the Product Owner accept this as satisfying the agreed intent?*
- **Purpose:** Provide the authoritative signoff that delivered work meets the agreed intent.
- **Key activities:** PO review of the increment against Acceptance Criteria and evidence;
  accept / reject decision.
- **Artifacts produced:** Acceptance decision (accepted / rejected with reasons).
- **Roles involved:** Product Owner (decides); Engineering and QA (present evidence).
- **Decision points:** Accept vs reject; whether evidence is sufficient and objective.
- **Review mechanisms:** The acceptance review itself.
- **Relationships:** Generally **embedded within CN-05 Definition of Done** rather than a
  separate workflow (Doc 6); consumes **CN-04 Acceptance Criteria**; the closing step of the
  Verification/Acceptance loop (Section 3).
- **Source documents:** Docs 5, 6.

## CN-07 · Continuous Collaboration

- **Question it answers:** *How do we stay aligned throughout delivery, not just at handoff?*
- **Purpose:** Maintain ongoing alignment between Product, Engineering, and QA across the
  whole lifecycle through continuous Product Owner collaboration, ongoing refinement, and
  incremental review.
- **Key activities:** Continuous PO collaboration, ongoing refinement, incremental review;
  organization-specific implementations such as an **Implementation Walkthrough** (which is
  *not* a Scrum ceremony — Doc 4 finding, see Section 4).
- **Artifacts produced:** Ongoing shared understanding; incremental feedback.
- **Roles involved:** Product Owner / Product Manager, Engineering, QA.
- **Decision points:** When to re-align; when a walkthrough or incremental review is needed.
- **Review mechanisms:** Incremental reviews throughout delivery rather than a single
  end-of-sprint gate.
- **Relationships:** Spans **CN-01 → CN-06**; is the practice-level expression of
  **Continuous Product Alignment** (Section 3); "Implementation Walkthrough" is one company
  implementation of it (Section 4).
- **Source documents:** Docs 4 (validated by Scrum.org/Atlassian; Implementation Walkthrough
  clarified), 5 (terminology).

## CN-08 · Story Acceptance

- **Question it answers:** *Did we build what we agreed for this story?*
- **Purpose:** Verify a completed story against its Acceptance Criteria — verification, not
  further discovery. A core activity of the Verification/Acceptance loop (Section 3).
- **Key activities:** Acceptance testing, feature validation against AC, evidence review.
- **Artifacts produced:** Story acceptance result and supporting evidence.
- **Roles involved:** Product Owner (accepts), QA and Engineering (verify and provide
  evidence).
- **Decision points:** Whether the story satisfies its AC; whether evidence is sufficient.
- **Review mechanisms:** Acceptance testing and validation against AC.
- **Relationships:** Verifies **CN-04 Acceptance Criteria**; feeds **CN-06 Product Owner
  Acceptance**; sits inside the Verification/Acceptance loop (Section 3).
- **Source documents:** Doc 8 (identified within the Verification/Acceptance loop).

## CN-09 · Sprint Review

- **Question it answers:** *Is the increment ready to show and accept at the stakeholder level?*
- **Purpose:** Provide the stakeholder-facing review at which the increment is demonstrated
  and its acceptance confirmed.
- **Key activities:** Demonstration of the increment; stakeholder feedback; confirmation of
  acceptance.
- **Artifacts produced:** Reviewed increment; stakeholder feedback; acceptance confirmation.
- **Roles involved:** Product Owner / Product Manager, Engineering, QA, stakeholders.
- **Decision points:** Whether the increment is accepted at the stakeholder level; what
  feedback re-enters the backlog.
- **Review mechanisms:** The review/demo itself.
- **Relationships:** Consumes results of **CN-08 Story Acceptance** and **CN-06 PO
  Acceptance**; is the *downstream* boundary of the refinement boundary gap (Section 5);
  feedback loops back into **CN-01 Backlog Refinement**.
- **Source documents:** Doc 3 (identified among the distributed implementation-validation
  activities).

---

## Relationship map (the edges)

The concepts feed into each other across the delivery lifecycle. The dependency chain runs
left-to-right through discovery into verification, with Continuous Collaboration (CN-07)
spanning the whole and feeding back at Sprint Review:

```text
                    ┌──────────────── CN-07 Continuous Collaboration (spans everything) ───────────────┐
                    │                                                                                    │
CN-01 Backlog ──► CN-02 Three ──► CN-03 Story ──► CN-04 Acceptance ──► CN-05 Definition ──► CN-06 PO ──► CN-09 Sprint
   Refinement       Amigos          Clarification    Criteria (AC)        of Done (DoD)      Acceptance     Review
      │               │                │                  │                   │  (embeds        │            │
      │               │                │                  │                   │   CN-06)        │            │
      └── produces ───┴── sharpen ─────┘                  └──► CN-08 Story Acceptance verifies AC ┘            │
          refined/"ready" stories                                (Verification/Acceptance loop)               │
                                                                                                              │
      ▲──────────────────────── Sprint Review feedback re-enters refinement ─────────────────────────────────┘
```

**Reading the edges:**

- **CN-01** is the umbrella that *contains* **CN-02** and **CN-03** and *produces* the first
  drafts of **CN-04**.
- **CN-02 / CN-03** *sharpen* **CN-04 Acceptance Criteria** (feature behavior).
- **CN-04 (what the feature does)** is verified by **CN-08 Story Acceptance**; **CN-05 (is
  the increment shippable)** applies at the increment level and **embeds CN-06 Product Owner
  Acceptance**.
- **CN-09 Sprint Review** consumes accepted work and *feeds back* into **CN-01**, closing the
  lifecycle loop.
- **CN-07 Continuous Collaboration** is not a stage but a *spanning* practice — the
  practice-level expression of Continuous Product Alignment (Section 3).

> The two-loop view (Discovery/Refinement vs Verification/Acceptance) and the boundary
> between them are documented in **[Section 3](03-two-product-loops-and-continuous-alignment.md)**.
> The specific point where CN-04/CN-05 verification is under-documented — between "ready for
> development" (after CN-01) and CN-09 Sprint Review — is the refinement boundary gap in
> **[Section 5](05-refinement-boundary-gap.md)**.

---

## AC ↔ DoD: the explicit distinction (Document 6)

The single most important comparative finding across the concept set, validated across
Microsoft, GitLab, Atlassian, and the UK National Archives (see Section 4):

| | **Acceptance Criteria (CN-04)** | **Definition of Done (CN-05)** |
| --- | --- | --- |
| **Question answered** | *"What should the feature do?"* | *"Is the increment ready to ship?"* |
| **Level** | Per-story / per-feature | Increment-level |
| **Scope** | Specific behavior of one item | Cross-cutting readiness standard |
| **Product Owner acceptance** | Consumes AC as the standard to check against | **PO acceptance is embedded here** (not a separate workflow) |

---

## Evidence-type catalogue (Document 6)

Document 6 catalogued the **evidence** used to satisfy Acceptance Criteria (CN-04) and
Definition of Done (CN-05) — and that the appropriate evidence differs by product type. This
catalogue attaches to the CN-04 and CN-05 nodes.

| Product type | Nature of evidence used to demonstrate AC satisfaction / DoD readiness |
| --- | --- |
| **Consumer products** | User-facing behavior demonstrated against expected experience |
| **APIs** | Contract/interface behavior demonstrated against the specified API surface |
| **Infrastructure** | Operational behavior and reliability demonstrated against expected system behavior |
| **AI products** | Model/output behavior demonstrated against expected quality and outcome |

> Per-company detail on how each organization handles this evidence is catalogued in
> **[Section 4](04-company-implementations-matrix.md)**.

---

*Previous: [Section 1 — Research Progression Narrative](01-research-progression-narrative.md) · Next: [Section 3 — Two Product Loops & Continuous Product Alignment](03-two-product-loops-and-continuous-alignment.md)*
