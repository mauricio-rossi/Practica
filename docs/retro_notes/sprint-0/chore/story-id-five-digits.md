CHORE: Standardize user story IDs to 5-digit format

## ✅ What Went Well
- Consolidated on a single, scalable ID format (5 digits) without breaking links.
- Explicit checklist prevented missed references.
- Clarified how to handle non-story work (chores, docs, fixes) as part of this standardization.
- Decided to drop numeric CHORE IDs and rely on descriptive branch prefixes and Conventional Commit messages.

## ⚠️ What Could Be Improved
- ID format decision surfaced mid-sprint; should be defined earlier in methodology.
- Large find/replace operations can be error-prone—prefer explicit targets and spot checks.

## 🔁 Action Items
- Document 5-digit ID rule in `agile-methodology.md` (done).
- Add an “ID format” item to the project bootstrap checklist for future repos.
- Consider a small script/check to validate story ID patterns in CI later.
- Incorporate non-story work guidelines into `agile-methodology.md` (as part of US-00006).