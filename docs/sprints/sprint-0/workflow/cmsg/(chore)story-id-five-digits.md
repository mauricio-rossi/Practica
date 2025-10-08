CHORE-000: Standardize user story IDs to 5-digit format

## Description
- Renamed story files from 4-digit IDs to 5-digit IDs (e.g., US-0001 → US-00001).
- Updated references in backlog index, story index, Sprint 0 docs, and methodology examples.

## Rationale
Consistent 5-digit IDs improve scalability and traceability across docs, branches, and PRs.

Additionally, this work clarified how non-story items (chores, docs, fixes) should be handled:
- No numeric IDs will be assigned to non-story work.
- Such branches will use descriptive prefixes (`chore/`, `docs/`, `fix/`).
- Commit messages will follow Conventional Commits style (e.g., `chore: …`).
- Optional tracking via GitHub Issues or `docs/shared/ops-log.md`.

## Scope
- File renames in `docs/shared/user-stories/`.
- Link updates in:
  - `docs/shared/user-stories/README.md`
  - `docs/sprints/sprint-0/sprint-overview.md`
  - `docs/shared/agile-methodology.md`

## Impact
- All future branches/stories must use 5-digit IDs (e.g., `feature/US-00006-title`).
