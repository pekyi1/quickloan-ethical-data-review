# Deliverable 2 — Corrected Data Flow Diagram (Annotations)

Below are the numbered corrections to apply directly on the provided data flow diagram. Each correction includes what to change and why.

## Corrections (use these as numbered callouts/footnotes on the diagram)

**[1] Implement Data Minimization (Step 1 — User Mobile App)**  
Reduce data collection to only essential loan decision data. Remove access to full contact lists and unnecessary device logs; limit location use to clearly justified fraud/risk purposes.  
**Why:** Prevents excessive collection, reduces privacy risk, and aligns with data minimization and lawful processing.

**[2] Add Explicit Consent Capture (Between Step 2 and Step 3 — API Gateway → Raw Data DB)**  
Introduce a consent management check at the API Gateway. Store and verify user consent (timestamp, purpose, version) before any personal data is written to the Raw Data DB.  
**Why:** Addresses compliance risk and supports auditability under Ghana’s Data Protection Act (Act 843).

**[3] Apply Data Classification & Retention (Step 3 — Raw Data DB ‘AllEvents’)**  
Classify stored data as **Sensitive** and enforce retention rules (e.g., delete raw events after X days once transformed/aggregated).  
**Why:** Prevents indefinite storage of sensitive personal data and reduces breach impact.

**[4] Enable Decision Transparency Logging (Step 7 — Decision Service)**  
Log decision inputs (features used), outputs (approve/deny), timestamps, and model version. Store logs in a secure audit log store with restricted access.  
**Why:** Provides accountability, explainability, and supports bias investigations.

**[5] Implement Masking/Anonymization for Analytics (Step 9 — Analytics DB)**  
Remove direct identifiers and mask/anonymize data before storing in Analytics DB. Only store aggregated metrics where possible.  
**Why:** Protects PII from misuse and supports privacy-by-design.

## Diagram Files
- `diagrams/flawed-data-flow.png` should contain the original diagram.
- `diagrams/corrected-data-flow.png` should contain your annotated version with callouts [1]–[5].
