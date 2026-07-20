# Layer 1 · Section 4 — Company-Specific Implementations of Product OS Concepts

> **Role in the knowledge graph:** This section is the **evidence base** that grounds the
> abstract concept nodes (Section 2) and operating model (Section 3) in real industry
> practice. It documents how each organization named in the research operationalizes the
> Product OS concepts, and — importantly — where the research did *not* establish a
> company's practice, so downstream layers do not treat gaps as findings.
>
> **Source:** Documents 4, 6, and 8.
> **Owning subtask:** DIV-51.
> **Discipline rule:** where the research did not document a specific company↔concept
> intersection, it is marked **"not covered in research"** rather than inferred. Several
> organizations were named as *study targets* in Document 8's research framework without the
> brief recording specific per-company findings; those are labeled accordingly.
> **Out of scope here:** the concept definitions themselves (Section 2), the CPA operating
> model (Section 3), the research narrative (Section 1), the refinement boundary gap
> (Section 5), and any failure modes (sibling parent DIV-33).

---

## What the research actually established per organization

The research recorded two kinds of company involvement:

1. **Comparative findings** — Document 6 *compared* Microsoft, GitLab, Atlassian, and the
   UK National Archives specifically on Acceptance Criteria, Definition of Done, Product
   Owner acceptance, and evidence. Document 4 *validated* continuous collaboration guidance
   against Scrum.org and Atlassian.
2. **Study targets** — Document 8's Product Operating Model Research Framework named
   Microsoft, Atlassian, GitHub, Shopify, and Amazon (and Stripe) as organizations *to
   study* across seven dimensions of Continuous Alignment. The brief records them as targets
   of the framework but does not record detailed per-company operating-model findings.

Both kinds are represented below; the second is explicitly marked so it is not mistaken for
established practice.

---

## Company profiles

### Microsoft  *(Docs 6, 8)*
- **Acceptance Criteria / Definition of Done:** one of the organizations compared in
  Document 6 to establish the AC vs DoD distinction and how mature engineering
  organizations define and validate work.
- **Product Owner acceptance:** included in the Document 6 comparison from which the
  "PO acceptance embedded within DoD" finding was drawn.
- **Continuous Alignment / Product Operating Model:** named as a study target in Document 8's
  seven-dimension research framework. *Specific Microsoft operating-model practices not
  detailed in the research.*

### GitLab  *(Docs 6, 8)*
- **Acceptance Criteria / Definition of Done / evidence:** one of the organizations compared
  in Document 6 on AC, DoD, and evidence, notable as a public engineering handbook source.
- **Discovery → acceptance connection:** referenced in the Document 8 context of connecting
  discovery through acceptance. *Specific GitLab connection mechanics not detailed in the
  research.*

### Atlassian  *(Docs 4, 6, 8)*
- **Continuous collaboration:** in Document 4, Atlassian guidance helped validate that
  continuous Product Owner collaboration, ongoing refinement, and incremental review are
  widely recommended.
- **Acceptance Criteria / Definition of Done:** one of the organizations compared in
  Document 6 on AC and DoD.
- **Product Operating Model:** named as a study target in Document 8's research framework.
  *Specific Atlassian operating-model practices not detailed in the research.*

### GitHub  *(Doc 8)*
- **Continuous Alignment / Product Operating Model:** named as a study target in Document 8's
  research framework for how it implements Continuous Alignment across the delivery
  lifecycle. *Specific GitHub practices not detailed in the research.*

### Shopify  *(Doc 8)*
- **Product Operating Model:** named as a study target in Document 8's research framework.
  *Specific Shopify practices not detailed in the research.*

### Amazon  *(Doc 8)*
- **Product Operating Model:** named as a study target in Document 8's research framework.
  *Specific Amazon practices not detailed in the research.*

### UK National Archives  *(Doc 6)*
- **Acceptance Criteria / Definition of Done:** included in the Document 6 comparison as a
  **public-sector** example of how AC and DoD are defined and validated — evidence that the
  concepts appear beyond commercial software organizations.

### Scrum.org  *(Doc 4)*
- **Continuous collaboration:** the official-guidance reference in Document 4 for continuous
  Product Owner collaboration, ongoing refinement, and incremental review.
- **Implementation Walkthrough:** Document 4 clarified — using Scrum.org's frame — that
  Implementation Walkthrough is **not a Scrum ceremony**, but one organizational
  implementation of continuous collaboration.

---

## Cross-reference matrix

Companies (columns) × Product OS concepts (rows). Cells state what the research established;
**"not covered"** marks intersections the research did not document; **"study target"** marks
organizations named for study in Document 8 without recorded per-company findings.

| Concept ↓ / Company → | Microsoft | GitLab | Atlassian | GitHub | Shopify | Amazon | UK Nat. Archives | Scrum.org |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| **Acceptance Criteria (CN-04)** | Compared (Doc 6) | Compared (Doc 6) | Compared (Doc 6) | not covered | not covered | not covered | Compared — public sector (Doc 6) | not covered |
| **Definition of Done (CN-05)** | Compared (Doc 6) | Compared (Doc 6) | Compared (Doc 6) | not covered | not covered | not covered | Compared — public sector (Doc 6) | not covered |
| **Product Owner Acceptance (CN-06)** | In Doc 6 comparison (embedded in DoD) | not covered | not covered | not covered | not covered | not covered | not covered | not covered |
| **Continuous Collaboration (CN-07)** | not covered | not covered | Validated guidance (Doc 4) | not covered | not covered | not covered | not covered | Official guidance (Doc 4); Impl. Walkthrough ≠ ceremony |
| **Continuous Alignment / Product Operating Model** | Study target (Doc 8) | Discovery→acceptance context (Doc 8) | Study target (Doc 8) | Study target (Doc 8) | Study target (Doc 8) | Study target (Doc 8) | not covered | not covered |
| **Evidence types (consumer/API/infra/AI)** | Doc 6 catalogue (not attributed per company) | Doc 6 catalogue (not attributed per company) | Doc 6 catalogue (not attributed per company) | not covered | not covered | not covered | Doc 6 catalogue (not attributed per company) | not covered |

> **Note on evidence types:** Document 6 catalogued evidence by *product type* (consumer,
> API, infrastructure, AI — see [Section 2](02-pm-lifecycle-and-operating-concepts.md#evidence-type-catalogue-document-6)),
> not by company. The matrix therefore marks the evidence row against the Document 6
> comparison set without inferring which company uses which evidence type.
>
> **Note on Stripe:** Document 8's research framework also named **Stripe** as a study
> target. It is not among the eight organizations profiled for this subtask and the brief
> records no specific Stripe findings, so it is noted here only for completeness.

---

## Key comparative findings

Three cross-company observations are load-bearing for the whole knowledge graph:

1. **AC vs DoD distinction** *(validated across Microsoft, GitLab, Atlassian, UK National
   Archives — Doc 6):* Acceptance Criteria define *"What should the feature do?"*; Definition
   of Done defines *"Is the increment ready to ship?"* The distinction holds across
   commercial and public-sector organizations.
2. **Product Owner acceptance is embedded within DoD** *(Doc 6):* across the compared
   organizations, PO acceptance is generally part of the Definition of Done rather than a
   separate standalone workflow.
3. **Implementation Walkthrough is not a Scrum ceremony** *(Doc 4):* it is one
   organizational implementation of continuous collaboration, not an official ceremony —
   evidence that the same underlying capability (Continuous Collaboration, CN-07) surfaces
   under company-specific names.

---

*Previous: [Section 3 — Two Product Loops & Continuous Product Alignment](03-two-product-loops-and-continuous-alignment.md) · Next: [Section 5 — The Refinement Boundary Gap](05-refinement-boundary-gap.md)*
