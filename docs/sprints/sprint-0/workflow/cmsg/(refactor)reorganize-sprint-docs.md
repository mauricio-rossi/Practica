refactor(docs): standardize sprint documentation structure under workflow folders

## Description
Reorganized sprint documentation to follow a consistent workflow-based structure.  
Each sprint folder now includes a `/workflow/` directory containing:
- `/cmsg/` → commit message drafts for story and non-story branches  
- `/retro-notes/` → retrospective reflections for those branches  

This improves clarity and traceability by separating Agile workflow artifacts  
from core sprint deliverables (`sprint-overview.md`, `user-stories.md`, `completed-stories.md`, `feedback.md`).  
It also establishes a repeatable layout for future sprints aligned with branch naming conventions.

## Rationale
- Simplifies navigation and reduces clutter in sprint folders  
- Reinforces Agile documentation transparency for portfolio presentation  
- Creates a scalable pattern for future workflow-related assets (e.g., `/workflow/test-logs/`)

## Scope
- Updated all sprint folders under `/docs/sprints/`  
- Added `/workflow/` directories with `cmsg/` and `retro-notes/` subfolders  
- Relocated and renamed existing commit and retro files for consistency  

## Impact
- Standardized sprint documentation structure for all future work  
- Improved readability and organization across sprints  
- No content or functionality changes — structure only
