# Research Backlog — USA Visitor Insurance (B-1/B-2)
Last updated: 2026-06-17

---

## 🔴 BLOCKING — Must Resolve Before Any Ranking

### B-001 — Certificate of Insurance documents not obtained
- **Status:** NEEDS MANUAL REVIEW
- **Impact:** All current plan data is brochure/marketing level (authority 6–7). No ranking can be finalized until Certificates are obtained.
- **Action required:** Download Certificate of Insurance PDF for each plan from carrier direct website
- **Plans affected:** ALL 32 plans discovered
- **Priority:** CRITICAL

---

## 🟡 Directory Structure Issues

### B-022 — Duplicate carrier directories from Phase 12
- **Status:** Open
- **Issue:** Phase 12 created inconsistent naming: `INF/` and `INF_Plans/`, `SevenCorners/` and `Seven_Corners/`, `Trawick/` and `Trawick_International/`
- **Action:** Consolidate before Phase 13. Merge `INF_Plans/` into `INF/`, merge `Seven_Corners/` into `SevenCorners/`, merge `Trawick_International/` into `Trawick/`. Then commit.
- **Also:** `Diplomat_America` is under `IMG/` but administrator is Global Underwriters (carrier = Crum & Forster). Move to `Global_Underwriters/Diplomat_America/`.
- **Also:** `Visitors_Protect_Insurance` in `Unknown_Carrier/` → move to `IMG/Visitors_Protect_Insurance/` (SiriusPoint carrier, IMG administrator)
- **Also:** `International_Major_Medical` in `Unknown_Carrier/` → move to `Lloyds/International_Major_Medical/`
- **Priority:** HIGH (before Phase 13)

---

## 🟡 Source Crawl Gaps

### B-003 — International Citizens Insurance fetch keeps timing out
- **Status:** STILL INCOMPLETE — both fetch attempts timed out (2026-06-17)
- **Note:** WebSearch confirms no new plans beyond what P1/P2 found. Low priority now.
- **Action:** Try Chrome browser tool; or accept as non-blocking since plan list is complete

### B-023 — GeoBlue plans eligibility not confirmed for B-1/B-2
- **Status:** NEEDS MANUAL REVIEW
- **Plans:** GeoBlue_Trekker, GeoBlue_Xplorer, GeoBlue_Voyager, GeoBlue_Navigator
- **Issue:** GeoBlue is BCBS Global Solutions, primarily for US citizens abroad and expats. Trekker/Voyager explicitly exclude USA coverage. Xplorer may work for people returning to USA.
- **Action:** Verify directly if any GeoBlue plan covers non-US nationals visiting USA on B-1/B-2. If not, exclude from rankings.
- **Priority:** HIGH

### B-024 — Seven Corners plan name verification
- **Status:** Open
- **Issue:** Phase 12 directories have `Liaison_Majestic` and `Liaison_Travel_Plus`. P2 crawl found `Liaison_Travel_Basic/Economy/Choice/Elite`. Are the Phase 12 plans old names or different products?
- **Action:** Check sevencorners.com directly — confirm current plan lineup

### B-025 — INF plan naming inconsistency
- **Status:** Open
- **Issue:** Phase 12 created `INF_Premier` and `INF_Standard` (no X suffix). P2 crawl found `INF_Premier_X`, `INF_Easy_Select`. Verify: are INF_Premier ≠ INF_Premier_X, or are they the same?
- **Action:** Check infplans.com — confirm current plan lineup

---

## 🟡 Document Gaps Per Plan

### B-010 — All plans: Policy Wording PDFs missing
- **Authority level needed:** Level 2 (Policy Wording)
- **Current data authority:** Level 6 (Marketing / Brochure)

### B-011 — All plans: Schedule of Benefits missing
- **Authority level needed:** Level 3

### B-012 — Acute onset exact language not verified
- **Status:** NEEDS MANUAL REVIEW — affects ALL plans
- **Why critical:** Marketing says "acute onset covered" but Certificate language determines actual coverage

### B-013 — Pre-existing condition lookback period not verified
- **Status:** NEEDS MANUAL REVIEW — affects ALL plans

---

## 🟢 Research Tasks — Phases 15–22

### B-014 — Phase 16: eligibility_profile.json not created
- Need per plan: can-buy-while-in-USA, waiting periods, extension rules

### B-015 — Phase 19: preexisting_profile.json not created
- 6 test cases (rotator cuff, diabetes, hypertension, heart disease, cancer, stroke) not run

### B-016 — Phase 20: network_profile.json not created
- UHC PPO vs First Health PPO vs Multiplan PPO comparison not done

### B-017 — Phase 21: claims experience not collected

### B-018 — Phase 18: post-discharge benefits not analyzed
- PT, OT, DME, home nursing, follow-up specialists

---

## 📋 Plans to Investigate

### B-019 — Global_Medical_Insurance — likely NOT a visitor plan
- **Status:** NEEDS MANUAL REVIEW
- **Finding:** IMG's Global Medical Insurance is an annual plan with underwriting, preventive care, and maternity. Designed for expats, not B-1/B-2 visitors.
- **Action:** Confirm ineligibility; remove from B-1/B-2 rankings if confirmed.

### B-020 — Patriot_America_Standard — verify vs Patriot_America_Plus
- Confirm whether Standard = Plus or separate tier

### B-021 — Safe Travels USA three tiers
- Cost Saver < USA (basic) < Comprehensive — exact differences need Schedule of Benefits comparison

---

## ✅ Completed

- Phase 11 P1 partial crawl (VisitorsCoverage, Insubuy, Visitor Guard) — 2026-06-17
- Phase 12 directory structure created — 2026-06-17
- source_registry.json created — 2026-06-17
- CLAUDE.md rewritten (10-section template) — 2026-06-17
- GitHub repo initialized (JCBTechHUB/indian-travellers-insurance) — 2026-06-17
- Phase 11 ICI re-crawl attempted (still timing out; no new plans identified) — 2026-06-17
- Phase 11 P2 all sources crawled (IMG, WorldTrips, Seven Corners, Trawick, GeoBlue, INF) — 2026-06-17
- Carrier identifications resolved for all 4 unknown plans — 2026-06-17
- Phase 11 COMPLETE — 32 plans discovered, source_registry.json updated — 2026-06-17
