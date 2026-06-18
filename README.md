# 🇮🇳 Indian Traveller's Insurance (ITI)

> An evidence-backed insurance pathway dashboard for the Indian community in the USA.

## What This Is

ITI maps every US visa type to its eligible insurance options — and ranks the top 10 plans per category based on verified policy documents, not marketing brochures.

**Target users:** Indian nationals on F-1, OPT, H-1B, L-1, B-1/B-2, J-1, and other US visas — and their families visiting from India.

## How It Works

```
Main Diagram (visa selector)
    └── Insurance cards per visa type
            ├── "Visit website →"   (direct buy link)
            └── "Compare →"         (category deep-dive dashboard)
                        └── Top 10 plans, evidence-scored across 12 dimensions
```

## Visa Types Covered

| Visa | Status |
|------|--------|
| F-1 Student | ✅ In main diagram |
| OPT / STEM OPT (Employed + Unemployed) | ✅ In main diagram |
| J-1 Exchange Visitor | ✅ In main diagram |
| H-1B, H-4, L-1, O-1, TN | ✅ In main diagram |
| B-1/B-2 Visitor | ✅ Diagram + dashboard in progress |
| Green Card / LPR | ✅ In main diagram |

## Insurance Categories Being Researched

- **USA Visitor Insurance** (B-1/B-2) — Phase 11 in progress
- F-1 Student Insurance — next
- OPT Insurance
- J-1 Exchange Visitor Insurance
- Indian Study Abroad Insurance
- International Health Insurance (expats)

## Research Methodology

Every ranking follows a strict 16-phase evidence loop (Phases 11–26):

- Phase 11: Discover all plans from Priority 1–3 sources
- Phase 12: Version-controlled document storage
- Phase 13: Authority hierarchy (Certificate > Policy > Brochure)
- Phase 14: Evidence engine — every fact must cite page + exact language
- Phase 16: Eligibility gap analysis (can buy while in USA? waiting periods?)
- Phase 17: Claim simulation (likely covered / denied / partial)
- Phase 19: Pre-existing condition intelligence
- Phase 24: Final ranking across 12 dimensions

See [`rules/methodology.md`](rules/methodology.md) for full detail.

## Hard Rules

- 🚫 No ranking from brochure data
- 🚫 No overwriting source documents
- ✅ Every score traces to a Certificate of Insurance
- ✅ If evidence is missing → `NEEDS MANUAL REVIEW`

See [`rules/hard_rules.md`](rules/hard_rules.md).

## Project Structure

```
CLAUDE.md                          ← AI instructions (10-section template)
rules/
  methodology.md                   ← Phases 11–26
  hard_rules.md                    ← evidence standards
InsuranceDatabase/
  USA_Visitor/
    source_registry.json           ← all discovered plans
    research_backlog.md            ← open items
    [Carrier]/[Plan]/
      raw_documents/
      extracted_data/
      analysis/
      scenario_results/
      version_history/
  Indian_Travel/
  International_Health/
```

## Built With

- Vanilla HTML/CSS/JS (interactive widgets)
- JSON evidence database
- Claude (AI research + dashboard generation)
- GitHub (versioned per phase)

---

*This project is for informational purposes only. Always verify coverage directly with the insurer before purchasing.*
