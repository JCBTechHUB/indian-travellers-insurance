# Research Methodology — Phases 11–26
# Always read this before starting any research or ranking work.

---

## PHASE 11 — DATA SOURCE REGISTRY

### Primary USA Visitor Insurance Sources
**Priority 1** (crawl first, most comprehensive aggregators)
- VisitorsCoverage — https://www.visitorscoverage.com
- Insubuy — https://www.insubuy.com
- Visitor Guard — https://www.visitorguard.com
- International Citizens Insurance — https://www.internationalinsurance.com

**Priority 2** (carrier/aggregator direct)
- IMG — https://www.imglobal.com
- WorldTrips — https://www.worldtrips.com
- Seven Corners — https://www.sevencorners.com
- Trawick — https://www.trawickinternational.com
- GeoBlue — https://www.geo-blue.com
- INF Plans — https://www.infplans.com

**Priority 3** (carrier direct websites, after P1+P2 complete)
- SiriusPoint, Zurich, TMHCC, etc.

### Goal
Discover ALL B1/B2 compatible plans. No plan should be missed.

### Output: `source_registry.json`
Fields per source:
- source_name
- source_url
- last_crawl_date
- plans_found (array of plan names)
- plans_removed (since last crawl)
- new_plans_detected (since last crawl)

---

## PHASE 12 — DOCUMENT MANAGEMENT

### Directory Structure
```
InsuranceDatabase/
  USA_Visitor/
    source_registry.json
    research_backlog.md
    [CarrierName]/
      [PlanName]/
        raw_documents/      ← never modify, never delete
        extracted_data/     ← JSON extractions with evidence
        analysis/           ← scoring, gap analysis
        scenario_results/   ← claim simulations
        version_history/    ← all dated versions

  Indian_Travel/
    [same structure]

  International_Health/
    [same structure]
```

### Versioning Rule
Never overwrite. Every update = new dated file.
- Format: `PlanName_YYYYMMDD.ext`
- Example: `AtlasAmerica_20260617.pdf`, `AtlasAmerica_20260701.pdf`

---

## PHASE 13 — DOCUMENT PRIORITY HIERARCHY

When documents conflict, higher authority wins.
1. Certificate of Insurance
2. Policy Wording
3. Schedule of Benefits
4. Coverage Summary
5. Brochure
6. Marketing Material
7. FAQ

Store `authority_level` (1–7) for every extracted statement.

---

## PHASE 14 — EVIDENCE ENGINE

Every conclusion requires evidence. No exceptions.

### Output: `evidence.json` per plan
Fields:
- carrier
- plan
- benefit
- conclusion
- source_document
- page_number
- section
- exact_language (verbatim quote)
- confidence_score (0–100)
- authority_level (1–7)

---

## PHASE 15 — COVERAGE KNOWLEDGE GRAPH

Normalize benefit names across carriers.
Example: "Hospitalization" maps to:
- Inpatient Hospitalization
- Hospital Admission
- Hospital Stay
- Room and Board

### Output: `coverage_graph.json`
Purpose: enable apples-to-apples comparison across all carriers.

---

## PHASE 16 — COVERAGE GAP ANALYSIS

Track for every plan:
- Can purchase while already in USA?
- Coverage lapse allowed?
- Waiting period (illness vs. accident)?
- Previous insurance required?
- Extension permitted?

### Output: `eligibility_profile.json`
This is critical for real B-1/B-2 travelers who may already be in the USA.

---

## PHASE 17 — CLAIM SIMULATION ENGINE

For every scenario (ER visit, hospitalization, surgery, etc.) determine:
- LIKELY COVERED
- LIKELY PARTIALLY COVERED
- LIKELY DENIED
- NEEDS MANUAL REVIEW

### Scoring per scenario:
- Coverage Score: 0–100
- Denial Risk: 0–100
- Confidence: 0–100

Never produce definitive legal conclusions. Always indicate confidence level.

---

## PHASE 18 — POST-DISCHARGE INTELLIGENCE

Analyze coverage for frequently overlooked post-discharge items:
- PT (Physical Therapy)
- OT (Occupational Therapy)
- Speech Therapy
- Home Health Aide
- Home Nursing
- Rehabilitation
- Walker / Wheelchair / DME
- Prescription Refills
- Follow-up Specialists
- Follow-up Imaging

### Output: `post_discharge_profile.json`

---

## PHASE 19 — PRE-EXISTING CONDITION INTELLIGENCE

Extract from Certificate of Insurance:
- Definition of pre-existing condition
- Lookback period
- Acute onset rules
- Stability requirements
- Waiting periods
- Exclusions

### Output: `preexisting_profile.json`

### Special Test Cases:
- Rotator Cuff injury
- Diabetes
- Hypertension
- Heart Disease
- Cancer History
- Stroke History

---

## PHASE 20 — PPO NETWORK INTELLIGENCE

Extract:
- Network name (UHC PPO / First Health / Multiplan)
- Hospital availability
- Urgent care availability
- Specialist access

### Output: `network_profile.json`

---

## PHASE 21 — CLAIMS EXPERIENCE INTELLIGENCE

Collect:
- Claim submission process
- Required documents
- Filing deadlines
- Appeal procedures

### Output: `claim_complexity_score`
Factors:
- Number of documents required
- Appeal difficulty
- Manual reimbursement burden

---

## PHASE 22 — COVERAGE CHANGE DETECTION

When any source document changes, generate `change_report_YYYYMMDD.md`:
- Added Benefits
- Removed Benefits
- Coverage Reductions
- Coverage Improvements

---

## PHASE 23 — QUALITY CONTROL

Every extracted fact requires: Source + Page + Evidence + Confidence.
If missing → `NEEDS MANUAL REVIEW`. Never assume. Never infer. Never use marketing language as proof.

---

## PHASE 24 — RANKING METHODOLOGY

Rank only within category. Never across categories.

Evaluation dimensions:
1. Hospitalization
2. ER
3. ICU
4. Surgery
5. Acute Onset of Pre-Existing
6. MRI / CT / Labs
7. Prescriptions
8. Post-Discharge Care
9. Network Quality
10. Claims Experience
11. Eligibility Flexibility
12. Price / Value

### Output: Top 10 Plans per category, evidence-backed scores only.

---

## PHASE 25 — RESEARCH BACKLOG

### File: `research_backlog.md` per category
Track:
- Unknown Benefits (needs Certificate verification)
- Missing Documents (need to obtain)
- Conflicting Language (between sources)
- Manual Review Requests
- New Plans Discovered
- Retired Plans

---

## PHASE 26 — FINAL DELIVERABLES

- Insurance Repository
- Coverage Database
- Scenario Engine
- Claim Intelligence Database
- Evidence Database
- Coverage Change Tracker
- USA Visitor Rankings
- Indian Travel Rankings
- International Health Rankings
- Traveler Decision Dashboard
