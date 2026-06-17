# Research Backlog — USA Visitor Insurance (B-1/B-2)
Last updated: 2026-06-17

---

## 🔴 BLOCKING — Must Resolve Before Any Ranking

### B-001 — Certificate of Insurance documents not obtained
- **Status:** NEEDS MANUAL REVIEW
- **Impact:** All current plan data is brochure/marketing level (authority 6–7). No ranking can be finalized until Certificates are obtained.
- **Action required:** Download Certificate of Insurance PDF for each plan from carrier direct website
- **Plans affected:** ALL 20 plans discovered
- **Priority:** CRITICAL

### B-002 — 4 plans have unknown carriers
- **Status:** NEEDS MANUAL REVIEW
- **Plans:** Visitors_Protect_Insurance, International_Major_Medical, Global_Medical_Insurance, Diplomat_America
- **Action required:** Identify underwriter and carrier for each. Check carrier direct websites.
- **Priority:** HIGH

### B-003 — International Citizens Insurance crawl incomplete
- **Status:** Fetch timed out on 2026-06-17
- **Action required:** Re-crawl https://www.internationalinsurance.com/visitors/ 
- **Priority:** HIGH

---

## 🟡 Priority 2 Sources — Not Yet Crawled

### B-004 — IMG Direct not crawled
- URL: https://www.imglobal.com/travel-medical-insurance/visitor-insurance
- May reveal plans not listed on aggregators

### B-005 — WorldTrips Direct not crawled
- URL: https://www.worldtrips.com/visitor-insurance

### B-006 — Seven Corners Direct not crawled
- URL: https://www.sevencorners.com/plan/liaison-travel

### B-007 — Trawick Direct not crawled
- URL: https://www.trawickinternational.com

### B-008 — GeoBlue not crawled
- URL: https://www.geo-blue.com

### B-009 — INF Plans Direct not crawled
- URL: https://www.infplans.com

---

## 🟡 Document Gaps Per Plan

### B-010 — All plans: Policy Wording PDFs missing
- **Authority level needed:** Level 2 (Policy Wording)
- **Current data authority:** Level 6 (Marketing / Brochure)
- **Action:** Obtain from carrier direct websites

### B-011 — All plans: Schedule of Benefits missing
- **Authority level needed:** Level 3
- **Action:** Download from each plan's carrier page

### B-012 — Acute onset exact language not verified
- **Status:** NEEDS MANUAL REVIEW
- **Plans affected:** ALL
- **Why critical:** Marketing says "acute onset covered" but Certificate language determines actual coverage. Terms like "chronic" and "non-chronic" are defined differently per carrier.

### B-013 — Pre-existing condition lookback period not verified
- **Status:** NEEDS MANUAL REVIEW
- **Plans affected:** ALL
- **Action:** Extract exact definition and lookback period from Certificate

---

## 🟢 Research Tasks — Next Steps

### B-014 — Phase 16 eligibility_profile.json not created
- Need to verify for each plan: can-buy-while-in-USA, waiting periods, extension rules
- Source needed: Certificate or Policy Wording (not marketing)

### B-015 — Phase 19 preexisting_profile.json not created
- 6 test cases (rotator cuff, diabetes, hypertension, heart disease, cancer, stroke) not run

### B-016 — Phase 20 network_profile.json not created
- UHC PPO vs First Health PPO network strength comparison not done

### B-017 — Phase 21 claims experience not collected
- Claim complexity scores not calculated for any plan

### B-018 — Phase 18 post-discharge benefits not analyzed
- PT, OT, DME, home nursing, follow-up specialists — not reviewed for any plan

---

## 📋 New Plans to Investigate

### B-019 — Visitors Protect Insurance — carrier unknown
- Found on: Visitor Guard
- Action: Identify carrier, obtain brochure and certificate

### B-020 — Global Medical Insurance — carrier unknown  
- Found on: Visitor Guard
- Note: Could be IMG's long-term expat plan — needs confirmation

### B-021 — Safe Travels USA Cost Saver vs Safe Travels USA vs Safe Travels Comprehensive
- Three distinct Trawick plans — exact differences not documented
- Action: Compare Schedule of Benefits for all three

---

## ✅ Completed

- Phase 11 P1 partial crawl (VisitorsCoverage, Insubuy, Visitor Guard) — 2026-06-17
- Phase 12 directory structure created — 2026-06-17
- source_registry.json created — 2026-06-17
