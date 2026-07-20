# Layer 4 · Section 2 — Failure Mode → Company-Level Signals

> **Role in the graph:** Bridges "we know practitioners complain about this" (Layer 2) to "we
> can detect *which companies* are experiencing it." For each of the six validated practitioner
> failure modes, this section defines the externally detectable **company-level signal**, its
> **detection method**, the PM lifecycle stage(s) it occurs at, the validated industry term, and
> the **buying trigger(s) from [§1](01-trigger-events-detection-methods.md)** it correlates
> with. This is the company-level counterpart to §1's event-level triggers.
>
> **Owning subtask:** DIV-45. **Parent:** DIV-35.
> **Consumes:** Layer 2 failure modes (`FM-01…FM-07`), Layer 1 stages, and the `BT-NN` triggers
> from §1.
> **Out of scope here:** cataloguing failure modes with symptoms/evidence/workarounds (Layer 2,
> DIV-33), defining the PM lifecycle stages (Layer 1, DIV-32), defining the trigger events
> themselves (§1), mapping to Specsight capabilities (Layer 3).

---

## 1. What this section maps (and the six failure modes)

The parent task names **six validated practitioner failure modes** from the Product OS research
(Documents 6–7). Each maps to a Layer 2 `FM-NN` id (Layer 2 §1):

| Failure-mode identifier | Layer 2 id | Industry term (validated) |
| --- | --- | --- |
| `ambiguous_ac` | FM-01 | Acceptance Criteria (CN-04) |
| `subjective_po_approval` | FM-02 | Product Owner Acceptance (CN-06) |
| `missing_evidence` | FM-03 | Definition of Done / evidence (CN-05) |
| `late_validation` | FM-04 | Story Acceptance / Sprint Review (CN-08, CN-09) |
| `unclear_ownership` | FM-05 | Acceptance ownership / Three Amigos (CN-06, CN-02) |
| `qa_product_engineering_misalignment` | FM-07 | Three Amigos shared understanding (CN-02, CN-08) |

> **Stage identifiers (contract).** Company-level signals are mapped to the four lifecycle-level
> stage identifiers used by this parent task: `requirements`, `sprint_review`,
> `uat_release_readiness`, `production`. These are the Document-2 lifecycle stages (also used in
> Layer 2 §4); they are a coarser view of the fuller Layer 1 stage set. The finer Layer 1
> concept nodes are cited alongside for precise anchoring.

> **Detection-status convention.** As in §1, the failure modes and their industry terms are
> *validated* (Layer 2); the **observable signals and detection methods** are GTM operational
> proposals — **detection candidates** for Commercial-Learning-Loop validation. Each signal is
> *externally observable* (findable without access to the company's internal tools).

---

## 2. Failure-mode → signal entries

### FM-01 · Ambiguous Acceptance Criteria (`ambiguous_ac`)

- **Associated stage(s):** `requirements` (Layer 1: Acceptance Criteria / Definition of Done;
  `CN-04`, `CN-02`).
- **Industry term:** Acceptance Criteria.
- **Observable signal:** PM job postings that emphasize *"writing clear requirements"* or
  *"creating/defining acceptance criteria"*; engineering job postings citing *"dealing with
  ambiguous requirements"* as a challenge.
- **Detection method:** LinkedIn / job-board posting keyword analysis on PM and engineering
  reqs. *(detection candidate.)*
- **Correlated buying trigger(s):** BT-01 (new leader discovers the problem), BT-03 (ratio
  widens → ambiguity surfaces at scale), BT-05 (informal AC break down post-raise).

### FM-02 · Subjective Product Owner Approval (`subjective_po_approval`)

- **Associated stage(s):** `sprint_review`, `uat_release_readiness` (Layer 1: Verification /
  Acceptance loop; `CN-06`, `CN-05`).
- **Industry term:** Product Owner Acceptance.
- **Observable signal:** Product Owner job postings emphasizing *"acceptance"* / *"sign-off"*
  without any mention of evidence-based criteria; engineering blog posts describing demo-based
  acceptance ("we accept on the demo").
- **Detection method:** Job-posting keyword analysis for PO reqs; engineering-blog monitoring
  for acceptance/sign-off language. *(detection candidate.)*
- **Correlated buying trigger(s):** BT-02 (Product Ops chartered to make acceptance systematic),
  BT-01 (leader wants objective acceptance).

### FM-03 · Missing Evidence (`missing_evidence`)

- **Associated stage(s):** `sprint_review`, `uat_release_readiness` (Layer 1: Acceptance
  Criteria / Definition of Done; `CN-04`, `CN-05`).
- **Industry term:** Definition of Done (evidence).
- **Observable signal:** Absence of DoD / evidence standards in public engineering handbooks or
  contribution guides; QA job postings that do **not** mention test evidence or a validation
  framework.
- **Detection method:** Public engineering-handbook / GitHub docs review; QA job-posting content
  analysis (absence signal). *(detection candidate — absence signals need careful calibration.)*
- **Correlated buying trigger(s):** BT-02 (systematize release evidence), BT-04 (AI-generated
  code needs demonstrable evidence).

### FM-04 · Late Validation (`late_validation`)

- **Associated stage(s):** `sprint_review`, `uat_release_readiness` (Layer 1: Verification /
  Acceptance loop; `CN-08`, `CN-09`).
- **Industry term:** Story Acceptance / Sprint Review.
- **Observable signal:** Job postings for *"release managers"* / *"deployment engineers"*
  mentioning *"last-minute validation"*; engineering blog posts about release delays and
  end-of-cycle bug clusters.
- **Detection method:** Job-posting keyword analysis; engineering-blog monitoring for
  release-delay narratives. *(detection candidate.)*
- **Correlated buying trigger(s):** BT-04 (velocity up, validation lags), BT-03 (validation
  can't keep pace with more engineers).

### FM-05 · Unclear Ownership (`unclear_ownership`)

- **Associated stage(s):** `requirements`, `sprint_review` (Layer 1: Acceptance Criteria /
  Definition of Done; `CN-06`, `CN-02`).
- **Industry term:** Acceptance ownership / Three Amigos.
- **Observable signal:** Job postings combining PM + PO + QA responsibilities into a single
  role; org charts showing merged Product/Engineering functions.
- **Detection method:** Job-posting role-scope analysis (multi-role reqs); public org-chart /
  team-page review. *(detection candidate.)*
- **Correlated buying trigger(s):** BT-02 (role created to fix fragmented ownership), BT-05
  (roles added post-raise blur ownership).

### FM-07 · QA–Product–Engineering Misalignment (`qa_product_engineering_misalignment`)

- **Associated stage(s):** `sprint_review`, `uat_release_readiness` (Layer 1: Three Amigos /
  Story Acceptance; `CN-02`, `CN-08`).
- **Industry term:** Three Amigos shared understanding.
- **Observable signal:** QA-engineer job postings citing *"working with Product and
  Engineering"* as a key challenge; multiple simultaneous hires across QA, Product, and
  Engineering (a team standing up cross-functional capacity at once).
- **Detection method:** Job-posting keyword analysis; hiring-pattern analysis (simultaneous
  cross-function reqs). *(detection candidate.)*
- **Correlated buying trigger(s):** BT-03 (more engineers → three roles diverge), BT-01 (leader
  finds QA passes but intent is missed).

---

## 3. Summary table (all six fields populated)

| Failure Mode | Associated Stage | Industry Term | Observable Signal | Detection Method | Correlated Buying Trigger(s) |
| --- | --- | --- | --- | --- | --- |
| **FM-01** Ambiguous AC (`ambiguous_ac`) | `requirements` (CN-04, CN-02) | Acceptance Criteria | PM reqs emphasizing "clear requirements"/"acceptance criteria"; eng reqs citing "ambiguous requirements" | LinkedIn/job-board keyword analysis | BT-01, BT-03, BT-05 |
| **FM-02** Subjective PO Approval (`subjective_po_approval`) | `sprint_review`, `uat_release_readiness` (CN-06, CN-05) | Product Owner Acceptance | PO reqs emphasizing "acceptance"/"sign-off" without evidence-based criteria; blog posts on demo-based acceptance | Job-posting keyword analysis; eng-blog monitoring | BT-02, BT-01 |
| **FM-03** Missing Evidence (`missing_evidence`) | `sprint_review`, `uat_release_readiness` (CN-04, CN-05) | Definition of Done (evidence) | No DoD/evidence standard in public handbooks; QA reqs omitting test-evidence/validation framework | Public handbook/GitHub docs review; QA req content analysis | BT-02, BT-04 |
| **FM-04** Late Validation (`late_validation`) | `sprint_review`, `uat_release_readiness` (CN-08, CN-09) | Story Acceptance / Sprint Review | "Release manager"/"deployment engineer" reqs citing "last-minute validation"; blog posts on release delays | Job-posting keyword analysis; eng-blog monitoring | BT-04, BT-03 |
| **FM-05** Unclear Ownership (`unclear_ownership`) | `requirements`, `sprint_review` (CN-06, CN-02) | Acceptance ownership / Three Amigos | Reqs merging PM+PO+QA into one role; org charts showing merged Product/Eng functions | Job-posting role-scope analysis; public org-chart review | BT-02, BT-05 |
| **FM-07** QA–Product–Eng Misalignment (`qa_product_engineering_misalignment`) | `sprint_review`, `uat_release_readiness` (CN-02, CN-08) | Three Amigos shared understanding | QA reqs citing "working with Product and Engineering" as a challenge; simultaneous QA+Product+Eng hires | Job-posting keyword analysis; hiring-pattern analysis | BT-03, BT-01 |

> **Coverage note.** These are the six failure modes the parent task names (Documents 6–7). They
> are the AC/DoD-stage set minus FM-06 (Demo Difficulties). The broader underserved set — the
> refinement boundary gap cluster (FM-08…FM-17) and the Context Reconstruction Tax (FM-18…FM-25)
> — carries the *event-level* triggers in §1 and the *friction preconditions* in
> [§4](04-friction-detection-specsight-fit.md); this section stays scoped to the six practitioner
> failure modes as instructed.

---

*Previous: [Section 1 — Buying trigger events & detection methods](01-trigger-events-detection-methods.md) · Next: [Section 3 — Evaluation criteria & decision process](03-evaluation-criteria-decision-process.md) · Back to [Layer 4 hub](../layer-4-buying-trigger-graph.md)*
