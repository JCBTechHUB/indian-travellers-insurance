# Hard Rules — Non-Negotiable

## File Safety
- NEVER delete files
- NEVER overwrite originals
- NEVER modify source documents
- Every update creates a new YYYYMMDD_version file
  - Example: `AtlasTravel_20260617.pdf`, `AtlasTravel_20260701.pdf`
- Always preserve raw documents exactly as downloaded

## Evidence Standards
- Every conclusion must be evidence-backed
- Every ranking must be reproducible
- Every recommendation must be explainable
- If evidence is insufficient → output `NEEDS MANUAL REVIEW`, never guess

## Document Authority Order (Phase 13)
When documents conflict, higher authority wins. Lower authority CANNOT override higher.
1. Certificate of Insurance
2. Policy Wording
3. Schedule of Benefits
4. Coverage Summary
5. Brochure
6. Marketing Material
7. FAQ

## Quality Control (Phase 23)
Every extracted fact requires:
- Source document name
- Page number
- Section heading
- Exact quoted language
- Confidence score (0–100)

If ANY of the above is missing → flag as `NEEDS MANUAL REVIEW`

## Ranking Rules (Phase 24)
- Rank ONLY within a category
- NEVER compare across categories
- Never use marketing language as the basis for a score
- Score must trace back to a Certificate or Policy Wording document

## Confidence Scoring
- 95–100: From Certificate of Insurance, exact language quoted
- 80–94: From Policy Wording or Schedule of Benefits
- 60–79: From Coverage Summary or Brochure (flag for Certificate verification)
- Below 60: From Marketing/FAQ only → always `NEEDS MANUAL REVIEW`
