# Indian Traveller's Insurance (ITI) — CLAUDE.md

## 1. Project Overview
Insurance pathway dashboard for the **Indian community in the USA**.
Maps every US visa type → eligible insurance options → evidence-ranked Top 10 per category.
Target users: Indian nationals on F-1, OPT, H-1B, L-1, B-1/B-2, J-1, and other US visas.
Architecture: Interactive HTML widget (main diagram) → per-category comparison dashboards → evidence database.

---

## 2. Tech Stack
- **Frontend:** Vanilla HTML/CSS/JS — single-file widgets rendered via Cowork visualizer
- **Data:** JSON files per plan (`evidence.json`, `eligibility_profile.json`, etc.)
- **Research:** Python (document parsing), web_fetch + WebSearch (source crawling)
- **Storage:** `/InsuranceDatabase/` folder — versioned, never overwritten

---

## 3. Project Structure
```
CLAUDE.md                          ← this file
rules/
  methodology.md                   ← Phases 11–26 (READ BEFORE ANY RESEARCH)
  hard_rules.md                    ← non-negotiable constraints
InsuranceDatabase/
  USA_Visitor/
    source_registry.json           ← all discovered plans
    research_backlog.md            ← open items / NEEDS MANUAL REVIEW
    [Carrier]/[Plan]/
      raw_documents/               ← never modify
      extracted_data/              ← evidence.json, eligibility_profile.json, etc.
      analysis/
      scenario_results/
      version_history/
  Indian_Travel/  International_Health/  ← same structure
```

---

## 4. Coding Conventions (Widget)
- Single-file HTML — CSS + JS inline, no external files except CDN libs
- Card object pattern: `{ name, badge, bl, desc, tags, good, warn, tiers, conds, caveat, link }`
- CSS variables for theming: `var(--text-primary)`, `var(--surface-secondary)`, `var(--border-color)`
- No `localStorage` — all state in JS variables
- Score bars: green ≥80, amber 60–79, red <60

---

## 5. UI / Design Rules
- Legend always visible; travel toggle highlights relevant cards in amber
- Ineligible cards hidden by default → toggle to reveal (never inline-grayed at full opacity)
- Each card has a `Visit website →` link button — color-coded by provider type
- Tier tables (e.g., IMG plans, StudentSecure) use the `.tier-table` pattern — not separate cards
- Border colors: green=best, purple=int'l student, blue=IMG, teal=ISO, orange=India, red=required

---

## 6. Key Rules & Guardrails
> Full detail → `rules/hard_rules.md`

- **Never rank without evidence.** Score must trace to Certificate of Insurance or Policy Wording.
- **Never use marketing language as proof.** Confidence <60 = `NEEDS MANUAL REVIEW`.
- **Never overwrite files.** All updates = new dated version (`PlanName_YYYYMMDD.ext`).
- **Authority order:** Certificate > Policy Wording > Schedule of Benefits > Brochure > Marketing > FAQ.
- Rank **within category only** — never compare B-1/B-2 plans against F-1 plans.

---

## 7. Behavioral Instructions
- Read `rules/hard_rules.md` and `rules/methodology.md` before any research task.
- Check `InsuranceDatabase/<category>/research_backlog.md` for open blockers first.
- Follow Phase loop strictly: 11 → 12 → 13 → 14 → … → 26. Don't skip ahead to ranking.
- If a Certificate PDF isn't obtained, output `NEEDS MANUAL REVIEW` — don't infer from brochure.
- Ask before adding a new plan to a category — confirm it's B-1/B-2 compatible, not just "visitor."

---

## 8. Common Pitfalls (What Claude Gets Wrong Here)
- ❌ **Ranking from brochure data** — happened in first attempt. Marketing says "covered" ≠ policy says covered.
- ❌ **Skipping Priority 1 sources** — missed Visitor Guard and ICI on first pass; 7 plans were unknown.
- ❌ **Building dashboard before completing Phase 11** — produced an evidence-free ranking dashboard.
- ❌ **Copying source docs instead of placing them in `raw_documents/`** — wrong directory.
- ❌ **Treating `VisitorsCoverage` as a carrier** — it's an aggregator. Carrier is SiriusPoint for CoverAmerica-Gold.

---

## 9. Commands & Workflows

**Start new category research:**
1. Read `rules/methodology.md`
2. Run Phase 11: crawl all P1 sources → update `source_registry.json`
3. Run Phase 12: mkdir carrier/plan/subfolders
4. Continue 13–26 in order

**Add a new plan discovered mid-research:**
```bash
mkdir -p InsuranceDatabase/USA_Visitor/[Carrier]/[Plan]/{raw_documents,extracted_data,analysis,scenario_results,version_history}
```
Then add to `source_registry.json` and `research_backlog.md`.

**Git commit after each phase:**
```bash
git add -A && git commit -m "Phase XX complete — [category] [brief description]"
git push origin main
```

---

## 10. References
- `rules/methodology.md` — full Phases 11–26
- `rules/hard_rules.md` — evidence standards, authority levels, confidence scoring
- `InsuranceDatabase/USA_Visitor/research_backlog.md` — current open items
- `InsuranceDatabase/USA_Visitor/source_registry.json` — all discovered plans
