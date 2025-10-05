# Retro Notes – NO-STORY cmsg drafts 

## Result
- Established a **commit message draft system** where each branch has its own draft file.  
- Draft files are stored at a path that matches the branch name convention:  
  - Example: branch `nostory/cmsg-drafts` → draft file `docs/cmsg/nostory/cmsg-drafts.md`.  
- Set up a **retrospective notes folder** organized by sprint:  
  - Example: `docs/cmsg/retro_notes/sprint-0/nostory/cmsg-drafts.md`.  
  Each branch can now record its own reflections in real time, which later roll into the official retrospective.  
- This creates a system to **capture observations as work is being done**, making it easier to produce both effective commit messages and structured sprint retrospectives.  

## What went well
- Documentation and commit workflow feels more professional and consistent.  
- Draft files reduce friction — commit messages are clear before they hit history.  
- Retro notes ensure that insights don’t get lost; they’re written in the moment, not reconstructed at the end.  
- The structure encourages organization and makes retrospective writing at sprint close much simpler.  

## Challenges
- Considered tradeoffs in naming and folder nesting:
  - Branch names with slashes can map directly to nested folders, which adds clarity and categorization.  
  - However, over-nesting may become unwieldy; this will need to be evaluated as the project grows.  
- Deciding whether to make this alias-driven or keep it manual for now — chose to keep it simple, no alias yet.  

## Improvements
- Add a short section to the Agile methodology doc explaining this system, so future contributors understand it quickly.  
- Define a reusable template for retro notes to keep style uniform across branches and sprints.  
- Revisit alias automation later to reduce typing, once the draft file structure proves stable.  

## Evidence
- Commit introducing the system: `<commit-sha>`  
- Draft file example: `docs/cmsg/nostory/cmsg-drafts.md`  
- Retro notes example (this file): `docs/cmsg/retro_notes/sprint-0/nostory/cmsg-drafts.md`