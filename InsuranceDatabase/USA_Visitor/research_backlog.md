# Research Backlog — USA Visitor Insurance (B-1/B-2)
Last updated: 2026-06-18 (Phase 25 consolidation)

---

## STATUS SUMMARY

| Priority | Count | Description |
|----------|-------|-------------|
| 🔴 CRITICAL | 3 | Must resolve before Atlas America / VisitorSecure can be ranked confidently |
| 🟠 HIGH | 8 | Must resolve before Phase 26 dashboard goes live as final version |
| 🟡 MEDIUM | 12 | Should resolve in next 90-day review cycle |
| 🟢 LOW | 6 | Background / cosmetic |

**Phases 11–24 completion status:** COMPLETE for 7 of 9 plans. Atlas America and VisitorSecure flagged PROVISIONAL pending TMHCC Certificates.

---

## 🔴 CRITICAL — Blocking Atlas America and VisitorSecure Rankings

### CD-001 — WorldTrips: TMHCC Certificate for Atlas America not obtained
- **Source:** CE-001 (Phase 22 change report) — carrier transition May 29, 2025
- **Status:** NEEDS MANUAL REVIEW
- **Impact:** Atlas America has ZERO L1/L2 evidence. Ranking score 61.7 is provisional. Actual plan may rank 3rd-5th once Certificate obtained.
- **Action:** Download Atlas America Description of Coverage from worldtrips.com (post-2025-05-29 TMHCC version). Extract evidence.json using Phase 14 method. Re-run Phase 17-19 simulations.
- **Contact:** WorldTrips customer service or download from worldtrips.com/us-visitor-health-insurance

### CD-002 — WorldTrips: TMHCC Certificate for VisitorSecure not obtained (new carrier version)
- **Source:** CE-001
- **Status:** NEEDS MANUAL REVIEW
- **Impact:** All VisitorSecure Phase 14 evidence entries from Lloyd's Certificate are potentially superseded. Confidence scores reduced 15 points across all categories.
- **Action:** Download new TMHCC VisitorSecure Description of Coverage from worldtrips.com. Re-verify all evidence entries. Document any benefit changes vs Lloyd's version.

### CD-003 — WorldTrips: Home Country Coverage REMOVED — update all files
- **Source:** CE-001
- **Status:** Open
- **Impact:** Atlas America and VisitorSecure benefit profiles still reference Home Country Coverage. Must be removed before dashboard goes live.
- **Action:** Update evidence.json for both plans. Mark Home Country Coverage as REMOVED_2025-05-29.

---

## 🟠 HIGH — Resolve Before Dashboard Final Version

### CI-001 — Safe Travels USA Comprehensive: claims filing deadline not confirmed
- **Source:** Phase 21 claims_intelligence_20260618.json
- **Status:** NEEDS MANUAL REVIEW
- **Impact:** Claims experience score penalized. Cannot confirm 90-day industry standard applies.
- **Action:** Contact Trawick at 866-696-0409 or obtain Certificate. Document exact deadline.

### CI-002 — INF Elite X: claims filing deadline not confirmed
- **Source:** Phase 21
- **Status:** NEEDS MANUAL REVIEW
- **Action:** Contact Robin Assist at 888-207-1694 or obtain Certificate.

### QC-001 — CoverAmerica Gold: COVID sub-30-day trip exclusion — verify exact Certificate language
- **Source:** Phase 17 (S-06 COVID scenario)
- **Status:** NEEDS MANUAL REVIEW
- **Impact:** Ranking notes COVID trap but exact Certificate language not quoted.
- **Action:** Locate exact exclusion language in CAG Certificate.

### QC-008 — INF Elite X: Certificate of Insurance (L1) not obtained
- **Source:** Phase 23 QC
- **Status:** All evidence is L2 (Policy Wording). Certificate not obtained.
- **Impact:** INF Elite X ranking confidence capped at 80. Any conflicting Certificate language could change rank.
- **Action:** Obtain Crum & Forster SPC Certificate for INF Elite X from infplans.com or via Robin Assist.

### PD-001 — All plans: Occupational Therapy and Speech Therapy not confirmed
- **Source:** Phase 18
- **Status:** UNCONFIRMED for all 9 plans
- **Action:** Obtain from Certificate for each plan. Critical for post-stroke and post-surgical travelers.

### PD-002 — All plans: Rehabilitation facility (inpatient) not confirmed
- **Source:** Phase 18
- **Status:** UNCONFIRMED for all 9 plans — could not find definitive language in any Certificate
- **Action:** Direct inquiry to each carrier. Key for hip fracture, stroke, post-surgical recovery.

### PD-003 — Home Nursing: unconfirmed for 7 of 9 plans (PAP/PAPL only confirmed)
- **Source:** Phase 18
- **Status:** NEEDS MANUAL REVIEW for CAG, Safe Travels, VisitorSecure, Atlas America, INF Elite X, SC Basic, SC Choice
- **Action:** Locate in Certificate for each plan.

### NW-001 — INF Elite X: PPO network URL discrepancy
- **Source:** Phase 20
- **Status:** infplans.com/first-health-ppo/ page title says First Health but confirmed network is UHC Options PPO
- **Action:** Verify from actual ID card or call Robin Assist to confirm exact network name for provider lookup.

---

## 🟡 MEDIUM — 90-Day Review Cycle

### CI-003 — Atlas America: claims deadline not confirmed
- **Source:** Phase 21
- **Likely:** 60 days from Certificate end (same as VisitorSecure) but must verify

### CI-004 — CoverAmerica Gold: confirm claims deadline 90 days vs 180 days
- **Source:** Phase 21
- **Note:** IMG administers both PAP (180 days) and CAG. CAG may share same 180-day deadline or have separate 90-day per aggregator source.

### CI-005 — Pre-cert service lists for 6 of 9 plans not confirmed
- **Plans:** CAG, Safe Travels, Atlas America, INF Elite X, SC Basic, SC Choice
- **Action:** Obtain from Certificate for each plan

### PE-001 — INF Elite X: unlimited lookback edge cases
- **Source:** Phase 19
- **Issue:** "Reasonably prudent person" standard — no fixed lookback. How far back can INF deny? Legal interpretation varies.
- **Action:** Request written clarification from INF/Robin Assist or find case precedent.

### PE-002 — VisitorSecure: full pre-existing definition — TMHCC version needed
- **Source:** Phase 19
- **Blocked by:** CD-002 (TMHCC Certificate needed)

### PE-003 — INF Elite X: multi-medication edge case
- **Source:** Phase 19
- **Issue:** Traveler on 3 medications — 2 stable 24+ months, 1 changed 18 months ago. Does the stable medication exception apply to the stable 2 or does any medication change defeat the whole exception?
- **Action:** Written clarification from INF/Robin Assist

### NW-002 — Atlas America: OON coinsurance rate not confirmed
- **Source:** Phase 20
- **Blocked by:** CD-001

### NW-003 — SC Basic/Choice: PHCS dual-network confirmed at L5 only
- **Source:** Phase 20
- **Action:** Verify from Certificate that PHCS/Multiplan is explicitly listed as secondary network

### NW-004 — Safe Travels: pharmacy reimbursement process not confirmed
- **Source:** Phase 20
- **Known:** No pharmacy in-network. But reimbursement process and limits not documented.

### B-022 — Duplicate carrier directory names in InsuranceDatabase
- **Issue:** INF/ vs INF_Plans/, SevenCorners/ vs Seven_Corners/, Trawick/ vs Trawick_International/
- **Action:** Consolidate. Merge into primary name (INF/, SevenCorners/, Trawick/).

### B-023 — GeoBlue plan eligibility for non-US nationals visiting USA
- **Status:** Unverified
- **Action:** Confirm from GeoBlue website. Likely excludes non-US nationals for USA coverage.

### QC-002 — CoverAmerica Gold Certificate date verification
- **Source:** Phase 23
- **Action:** Confirm Certificate in raw_documents matches October 2, 2024 effective date

---

## 🟢 LOW — Background Items

### B-024 — Seven Corners plan name verification (Liaison vs Travel Medical)
- Confirm current plan lineup — Liaison plans may be legacy names

### B-025 — INF plan naming: INF_Premier vs INF_Premier_X
- Confirm from infplans.com if Premier and Premier_X are same or different plans

### B-003 — International Citizens Insurance (ICI) website fetch keeps timing out
- Low impact — no new plans expected; P1+P2 crawl already complete

### CD-006 — Schedule next 90-day monitoring review
- **Next review date:** 2026-09-18
- Re-check all carrier product pages for changes
- Verify all plan Certificates against baseline

### DASHBOARD-001 — Atlas America card marked PROVISIONAL in dashboard
- Once CD-001 resolved and TMHCC Certificate obtained, update Atlas America card with confirmed evidence

### DASHBOARD-002 — Add price comparison data when available
- Current dashboard uses relative price tiers (Budget / Mid / Premium) — add actual per-day rates when quote data is obtained

---

## RESOLVED ITEMS (closed this session)

| ID | Description | Resolved |
|----|-------------|---------|
| B-001 | Certificate of Insurance documents — 7 of 9 plans obtained (Atlas America and VisitorSecure TMHCC version pending) | PARTIAL |
| B-012 | Acute onset exact language — verified for 7 of 9 plans at L1 | PARTIAL |
| B-013 | Pre-existing condition lookback — verified for 7 of 9 plans | PARTIAL |
| B-014 | eligibility_profile.json created (Phase 16) | DONE |
| B-015 | preexisting_profile.json created (Phase 19) | DONE |
| CE-001 | WorldTrips carrier transition documented — Home Country Coverage removal noted | DOCUMENTED |
| INF pre-cert | INF Elite X pre-certification requirement confirmed from search | CONFIRMED |
| All phases 17-22 | Claim simulation, post-discharge, pre-existing, network, claims, change detection | DONE |
