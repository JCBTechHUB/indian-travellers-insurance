# Coverage Change Report — USA Visitor Insurance
**Report Date:** 2026-06-18  
**Phase:** 22 — Coverage Change Detection  
**Baseline:** This is the INITIAL baseline report (first research pass). No prior baseline exists to compare against.  
**Next review:** 2026-09-18 (90-day cycle)

---

## Summary

One **confirmed major change** identified affecting 2 of 9 plans. One confirmed minor event (new product line, no impact). One policy renewal date noted. No changes detected for PAP, PAPL, INF Elite X, or Seven Corners plans.

---

## CONFIRMED CHANGES

### CE-001 — WorldTrips: Carrier Transition (HIGH IMPACT)
**Plans affected:** Atlas America, VisitorSecure  
**Effective date:** 2025-05-29 (12:01 AM EDT)  
**Source:** https://www.atlasamericainsurance.net/atlas-carrier-transition-product-updates-2025/

#### What changed:

**Carrier:**  
- Old: Lloyd's of London (Lloyd's syndicates)  
- New (all states except FL): TMHCC (CI) Insurance SPC Ltd — part of Tokio Marine HCC Group  
- New (Florida policies only): Houston Casualty Company (HC)  

New carrier ratings: AM Best A++ (Superior), S&P A+ (Strong), Fitch AA-. This is a rating *upgrade* from Lloyd's.

**Benefits REMOVED:**
- **Home Country Coverage** — removed from all WorldTrips plans including Atlas America and VisitorSecure. Travelers who previously relied on incidental home country coverage (e.g., brief return to India during a US stay) lose this benefit entirely.

**Benefits ADDED:** None.

**Eligibility restrictions CHANGED:**
New purchase location restrictions were added. Indian travelers purchasing WorldTrips plans **cannot** purchase if located in:
- Australia, Canada, New York, or Washington (at time of purchase)
- Maryland (both applicant and purchaser)
- EEA countries (list of 22+ countries)

These restrictions are unlikely to affect most Indian B-1/B-2 visitors purchasing from India before travel. However, travelers already in the US who might want to purchase or extend from within NY or WA cannot do so for new policies under the TMHCC carrier.

**Restricted countries list:** Now follows TMHCC Noted Countries and Territories for Eligibility list. Key additions to never-eligible: Cuba, Iran, North Korea, Syria (destination). Ukraine added to "not available as destination."

#### Impact on ITI Evidence Database:

> **ACTION REQUIRED before Phase 24 ranking:** Any Atlas America or VisitorSecure Certificate of Insurance obtained prior to May 29, 2025 belongs to the Lloyd's carrier. Those Certificates no longer apply to newly issued policies. Evidence.json entries built from Lloyd's Certificates must be flagged as potentially superseded and re-verified against the TMHCC Certificate.

Steps required:
1. Download new TMHCC Certificate of Insurance for Atlas America (post-2025-05-29 version)
2. Download new TMHCC Certificate of Insurance for VisitorSecure (post-2025-05-29 version)
3. Compare to existing evidence.json entries
4. Flag any changed or removed benefit entries
5. Remove Home Country Coverage from Atlas America and VisitorSecure benefit profiles

**Confidence in this change:** 98 (confirmed from official WorldTrips/VISOA update page — L6, but describing their own policy change)

---

### CE-003 — CoverAmerica Gold: Master Policy Renewal (LOW IMPACT)
**Plans affected:** CoverAmerica Gold  
**Effective date:** 2024-10-02  
**Source:** VisitorsCoverage CAG policy document

Master Policy effective date confirmed as October 2, 2024. No specific benefit changes identified — this appears to be a standard annual renewal. The plan structure, coinsurance schedule, cardiac/stroke sub-limits, and COVID coverage appear consistent with prior terms based on available sources.

**Impact on ITI Evidence Database:** Verify Certificate file in raw_documents/ is dated October 2024 or later. If an older Certificate was used for Phase 14 evidence extraction, re-download and verify.

---

## NO CHANGE DETECTED

The following plans show no significant changes between their last known Certificate version and current available sources:

| Plan | Last Known Certificate | Change Signal | Status |
|------|----------------------|---------------|--------|
| Patriot America Plus | Phase 13-14 | None detected | No action |
| Patriot America Platinum | Phase 13-14 | None detected | No action |
| Safe Travels USA Comprehensive | Phase 13-14 | New Pathway products are different line; Safe Travels unchanged | No action |
| INF Elite X | Phase 13-14 | No product announcements found | No action |
| SC Travel Medical Basic | Phase 13-14 | No product announcements found | No action |
| SC Travel Medical Choice | Phase 13-14 | No product announcements found | No action |

> Note: "No change detected" means no change was found via web search (L6 authority). It does NOT mean no change occurred. Only Certificate-to-Certificate comparison (L1) can confirm this definitively. These plans should still be re-verified at the 90-day review.

---

## NEW CONFIRMED DATA POINT (not a change — clarifies prior NEEDS MANUAL REVIEW)

**INF Elite X — Pre-Certification Requirement CONFIRMED:**  
Search result from Robin Assist / INF confirmed: "Pre-certification is required for any non-emergency hospital admission, and failure to pre-certify may affect your claim."  

This resolves the open item in claims_intelligence_20260618.json regarding pre-certification for INF Elite X. Update claims_intelligence file at next version:
- Pre-certification: REQUIRED for non-emergency hospital admissions
- Failure consequence: "may affect your claim" (exact penalty not specified — still needs Certificate confirmation)

---

## OPEN ITEMS CARRIED FORWARD TO PHASE 25 BACKLOG

| ID | Description | Priority |
|----|-------------|----------|
| CD-001 | Download TMHCC post-2025-05-29 Certificate for Atlas America. Re-verify all Phase 14 evidence entries. | CRITICAL |
| CD-002 | Download TMHCC post-2025-05-29 Certificate for VisitorSecure. Re-verify all Phase 14 evidence entries. | CRITICAL |
| CD-003 | Remove Home Country Coverage from Atlas America and VisitorSecure benefit profiles. | HIGH |
| CD-004 | Confirm CoverAmerica Gold Certificate in raw_documents/ is October 2024 version or later. | MEDIUM |
| CD-005 | INF Elite X pre-cert failure penalty — obtain exact language from Policy Wording or Certificate. | MEDIUM |
| CD-006 | Set up 90-day monitoring calendar. Next review: 2026-09-18. Re-check all plan product pages and carrier update feeds. | LOW |

---

## Monitoring Sources for Future Reviews

| Carrier | Change Announcement URL |
|---------|------------------------|
| IMG (PAP/PAPL/CAG) | imglobal.com/travel-medical-insurance/patriot-america-plus |
| WorldTrips (Atlas/VisitorSecure) | atlasamericainsurance.net/updates/ |
| Trawick International | trawickinternational.com/products/safe-travels-usa-comprehensive/ |
| INF / Robin Assist | infplans.com/elite-network-x/ |
| Seven Corners | sevencorners.com/plans/visitors-insurance |

---

*Next change report should be generated: 2026-09-18. Compare against this baseline.*
