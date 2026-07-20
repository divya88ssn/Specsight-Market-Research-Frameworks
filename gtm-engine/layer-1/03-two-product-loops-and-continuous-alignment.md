# Layer 1 · Section 3 — Two Product Loops & Continuous Product Alignment

> **Role in the knowledge graph:** Section 2 catalogued the individual concept *nodes*.
> This section documents the **operating model that connects them into a coherent system** —
> the two product loops, the operational boundary between clarification and requirement
> evolution, Continuous Product Alignment (CPA) as the higher-level lens, the two emerging
> schools of practice, and the curated research corpus that validates the model.
>
> **Source:** Documents 8–9.
> **Owning subtask:** DIV-46.
> **Out of scope here:** individual concept nodes (Section 2), company implementations
> (Section 4), the refinement boundary gap as a standalone analysis (Section 5), and the
> six-layer GTM engine architecture (sibling parent DIV-36).

---

## 1. The two product loops (Document 8)

Document 8's most important conceptual contribution is separating two loops that are often
discussed together but solve fundamentally different problems. Concept nodes from Section 2
(CN-xx) are distributed across the two loops.

### Discovery / Refinement Loop

- **Question answered:** *What should we build?*
- **Purpose:** Continuous understanding **before** implementation.
- **Constituent activities:** Backlog Refinement (CN-01), Story Refinement, Three Amigos
  (CN-02), Example Mapping, Story Splitting, Scope negotiation. *(Story Clarification, CN-03,
  operates here — governed by the boundary in §2 below.)*

### Verification / Acceptance Loop

- **Question answered:** *Did we build what we agreed?*
- **Purpose:** **Verification — not further discovery.**
- **Constituent activities:** Story Acceptance (CN-08), Product Owner Acceptance (CN-06),
  Acceptance Testing, Feature Validation, Definition of Done verification (CN-05).

### The boundary between the loops

The two loops are separated by an explicit transition point: **discovery ends when a story
is agreed and "ready for development"; verification begins when completed work is checked
against what was agreed.** Crossing back from verification into discovery (i.e., discovering
*new* things to build during acceptance) is the signal that requirement evolution — not
clarification — is occurring (see §2). This boundary is foundational for understanding the
Product Operating System.

```text
        DISCOVERY / REFINEMENT LOOP                    VERIFICATION / ACCEPTANCE LOOP
        "What should we build?"                        "Did we build what we agreed?"
        (understanding before build)                   (verification, not discovery)

  ┌────────────────────────────────────┐        ┌────────────────────────────────────┐
  │  Backlog Refinement (CN-01)         │        │  Story Acceptance (CN-08)           │
  │  Story Refinement                   │        │  Product Owner Acceptance (CN-06)   │
  │  Three Amigos (CN-02)               │        │  Acceptance Testing                 │
  │  Example Mapping                    │        │  Feature Validation                 │
  │  Story Splitting                    │        │  DoD verification (CN-05)           │
  │  Scope negotiation                  │        │                                     │
  └───────────────────┬────────────────┘        └────────────────▲───────────────────┘
                      │                                            │
                      │        ══════ BOUNDARY ══════              │
                      └──►  "ready for development"  ──► implement ─┘
                           (agreement reached;              (verify against
                            discovery ends)                  what was agreed)
```

> The stretch of lifecycle *between* "ready for development" and stakeholder-level Sprint
> Review — where verification actually happens but published frameworks go quiet — is the
> refinement boundary gap analyzed in **[Section 5](05-refinement-boundary-gap.md)**.

---

## 2. Clarification vs Requirement Evolution (Document 8)

Document 8 distinguishes two conversations that are often conflated. This distinction is an
**operational decision point** in the knowledge graph (it governs Story Clarification, CN-03).

| | **Clarification** | **Requirement Evolution** |
| --- | --- | --- |
| **Effect on shared understanding** | Improves it | Changes what is being built |
| **Effect on Acceptance Criteria** | **Does NOT change AC** | Introduces new business behavior |
| **Effect on the backlog** | No new work | **Creates new backlog work** |
| **What it represents** | Continuous alignment | Scope change |

**The operational rule:** *Clarification does not change Acceptance Criteria; requirement
evolution creates new backlog work.* This rule draws the line between **continuous alignment**
and **scope creep** — the practical decision teams must make every time a question arises
during delivery.

---

## 3. Continuous Product Alignment (CPA) — the higher-level operating model (Document 8)

CPA reframes the individual practices. Rather than treating Backlog Refinement, Product
Validation, Acceptance, and Story Clarification as isolated practices, Document 8 proposes
viewing them as **observable manifestations of a broader operating capability: Continuous
Product Alignment.**

- **Backlog Refinement becomes one activity *inside* that capability — not the capability
  itself.** The same holds for Product Validation, Acceptance, and Story Clarification.
- **CPA is an analytical lens, not a new methodology to sell** — a way of understanding how
  organizations maintain alignment from discovery through release.

```text
                    ┌───────────────────────────────────────────────┐
                    │        CONTINUOUS PRODUCT ALIGNMENT (CPA)        │
                    │   (the operating capability / analytical lens)   │
                    │                                                  │
                    │   observable manifestations:                     │
                    │     • Backlog Refinement (CN-01)                 │
                    │     • Product Validation                         │
                    │     • Acceptance (CN-06 / CN-08)                 │
                    │     • Story Clarification (CN-03)                 │
                    └───────────────────────────────────────────────┘
```

### Product Operating Model Research Framework (Document 8)

Instead of searching for ceremonies, Document 8 proposes researching *how organizations
implement Continuous Alignment* along seven dimensions:

1. Requirement evolution
2. PM involvement
3. Engineering autonomy
4. Customer validation
5. Reviews
6. Documentation
7. Communication

> This framework is the lens applied to real organizations (Microsoft, Stripe, Atlassian,
> GitHub, Shopify, Amazon) in **[Section 4](04-company-implementations-matrix.md)**.

---

## 4. Emerging schools of practice (Document 9)

Document 9 identifies two evolving operating philosophies. The research does **not** pick a
winner — it proposes studying *where each organization draws the boundary between
clarification and new requirements* (§2).

| Dimension | **Traditional Scrum** | **AI-native / Product-led** |
| --- | --- | --- |
| **Refinement weight** | Heavy upfront refinement | Lightweight refinement |
| **Acceptance Criteria** | Largely frozen | Controlled requirement evolution |
| **Live discovery** | Limited live discovery | Continuous validation |
| **Success measured by** | Sprint predictability | Decision speed and customer outcomes |

---

## 5. Curated research corpus (Document 9)

Rather than searching broadly, Document 9 recommends studying a focused set of authors,
because each consistently represents one aspect of the Product Operating Model. This corpus
is the validation base for the model above and a source pool for downstream layers.

| Practitioner | Aspect of the Product Operating Model they contribute to |
| --- | --- |
| **Mike Cohn** | Refinement and story practices |
| **Joel Bancroft-Connors** | Shared understanding / agile coaching |
| **Maarten Dalmijn** | Refinement and requirement evolution |
| **Roman Pichler** | Product ownership and alignment |
| **Barry Overeem** | Scrum practice and shared understanding |
| **Stefan Wolpers** | Practitioner failure patterns and refinement |
| **Lenny Rachitsky** | Product management practice and judgment |
| **Shreyas Doshi** | Product judgment and prioritization |
| **Saurabh Juneja** | AI / emerging product practice |

> **Methodological note (Document 9):** the corpus favors practitioners discussing *real
> sprint failures* (implementation drift, skipped refinement, unclear acceptance criteria,
> blocked engineering, velocity loss, developers interpreting stories differently) over
> well-known Agile guidance — those operational breakdowns are inputs for workflow research
> rather than anecdotal advice. The failure patterns themselves are catalogued by the
> Failure Mode Library (sibling parent DIV-33), not here.

---

*Previous: [Section 2 — PM Lifecycle Stages & Operating-Model Concepts](02-pm-lifecycle-and-operating-concepts.md) · Next: [Section 4 — Company-Specific Implementations](04-company-implementations-matrix.md)*
