# ClaimPilot AI -- End-to-End Claim Workflow

``` mermaid
flowchart TD
    A["Employee Login"] --> B["Create Claim"]
    B --> C["Upload Documents"]
    C --> D["Store Original Documents"]
    D --> E["OCR + Document Classification"]
    E --> F["AI Information Extraction"]

    F --> G[("PostgreSQL<br/>Structured Data")]
    F --> H[("pgvector<br/>Chunks + Embeddings")]

    G --> I["Validation & Verification"]
    H --> I

    I --> J["Policy Rules & Anomaly Flags"]
    J --> K["AI-Assisted Review Summary"]
    K --> L["Human Reviewer"]
    L --> M{"More information?"}

    M -- Yes --> N["Request Info"]
    N --> C

    M -- No --> O["Record Final Claim Outcome"]
```

## Workflow steps

1.  **Employee Login** -- Authenticate the insurance employee and verify
    their role.
2.  **Create Claim** -- Register the claim and capture the relevant
    patient, policy, hospital, and claim details.
3.  **Upload Documents** -- Upload supporting medical documents such as
    bills, discharge summaries, prescriptions, and medical reports.
4.  **Store Original Documents** -- Securely store the original files
    and save their metadata and storage references.
5.  **OCR + Document Classification** -- Extract text and identify each
    document type.
6.  **AI Information Extraction** -- Extract structured information such
    as patient details, dates, diagnosis, treatment details, and
    amounts.
7.  **Store extracted information**:
    -   **PostgreSQL:** structured claim and extracted data.
    -   **pgvector:** document chunks and embeddings for semantic
        retrieval.
8.  **Validation & Verification** -- Check required fields and compare
    information across documents.
9.  **Policy Rules & Anomaly Flags** -- Apply configured policy checks
    and flag unusual patterns for human investigation.
10. **AI-Assisted Review Summary** -- Prepare findings, missing
    information, explanations, and references to supporting evidence.
11. **Human Reviewer** -- An authorized employee reviews the findings
    and evidence.
12. **More information?**
    -   **Yes:** Request additional information and return the claim to
        document upload.
    -   **No:** Record the final claim outcome.

> **Important:** AI supports the review process; it does not make the
> final claim decision. An anomaly flag is an indicator for
> investigation, not proof of fraud. Final outcomes are recorded by an
> authorized human reviewer.
