# 📘 Agile Methodology – Practica App

This document outlines the Agile approach used in the development of the **Practica App** project. It serves as a living reference to define processes, roles, and workflows as they evolve.

## 📑 Table of Contents

- [🎯 Agile Philosophy](#-agile-philosophy)
- [🧩 Core Agile Artifacts](#-core-agile-artifacts)
- [📆 Sprint Lifecycle](#-sprint-lifecycle)
- [🔄 Git Flow](#-git-flow)
- [🔐 Commit Message Convention](#-commit-message-convention)
- [🧪 Testing Strategy (Planned)](#-testing-strategy-planned)
- [🔄 CI/CD Pipeline (Planned)](#-cicd-pipeline-planned)
- [📌 License](#-license)
- [🧪 In Practice](#-in-practice)

---

## 🎯 Agile Philosophy

I follow an Agile-inspired methodology focused on:

* **Iterative development** through time-boxed sprints  
* **User-centered design** through defined personas  
* **Adaptability** with evolving documentation and backlog  
* **Transparency** through public GitHub project structure and commit history  

---

## 🧩 Core Agile Artifacts

### 🔹 Backlog

All user stories are stored in the **backlog folder**: `docs/shared/user-stories/`.  
Each story has its own file (`US-00001.md`, `US-00002.md`, etc.) containing its ID, description, persona, and acceptance criteria.  

A `README.md` in the same folder acts as the **backlog index**, providing an overview of stories with their **current priority and status**. Sprint files do not duplicate story details — they only link to these story files.  

If a story is not completed in a sprint, it remains in the backlog index for re-prioritization.  

Backlog stories may evolve by:  
- **Splitting** → original story marked as split, new story files created with new IDs  
- **Rewriting** → original story marked as replaced, new story file created with new ID  
- **Closing** → story file marked as closed if dropped or no longer needed  

**Example Backlog Index (`docs/shared/user-stories/README.md`):**

| ID      | Title          | Priority | Status       |
|---------|----------------|----------|--------------|
| [US-00001](US-00001.md) | Email Sign-up   | High     | ✅ Completed |
| [US-00002](US-00002.md) | Login           | High     | 🔄 In Progress |
| [US-00003](US-00003.md) | Profile Page    | Medium   | 📋 Backlog |
| [US-00004](US-00004.md) | Password Reset  | Low      | ❌ Closed |

---

### 🔹 Story Index

The **Story Index** (`docs/shared/story-index.md`) is a historical log of each story’s lifecycle across sprints.  
It shows when stories were planned, completed, or evolved.  

It records:  
- Story ID and title  
- Sprint where it was planned/completed  
- Final outcome (Completed, Split, Dropped, Replaced)  
- Links to backlog and sprint results  (Issues, Commits, Outcomes) 

This file acts as the **central map** connecting backlog entries with sprint outcomes.  

**Example Story Index (`docs/shared/story-index.md`):**

| ID      | Title          | Sprint  | Outcome                  | Result Link |
|---------|----------------|---------|--------------------------|-------------|
| US-00001 | Email Sign-up  | Sprint 1 | ✅ Completed             | [Results](../sprints/sprint-01/completed-stories.md#us-00001) |
| US-00002 | Login          | Sprint 2 | 🔄 In Progress           | - |
| US-00003 | Profile Page   | Sprint 2 | ⏸ Split → US-00010, US-00011 | - |
| US-00004 | Password Reset | Sprint 2 | ❌ Closed (not needed)   | - |

### 🔹 Kanban Boards

GitHub Projects are used to visualize sprint progress and separate active story work from non-story technical work.

Two project boards are used:

- **Practica – Sprint Board**: tracks active user stories selected for the current sprint.
- **Practica – Technical Backlog**: tracks non-story work such as chores, refactors, documentation cleanup, infrastructure, tooling, and workflow tasks.

The Sprint Board uses the following core columns:

| Column | Meaning |
|--------|---------|
| Backlog | Story issue exists but active work has not started |
| In Progress | A branch has been created and implementation/documentation work is active |
| In Review | A pull request is open and ready for review |
| Done | The pull request has been merged and acceptance results have been recorded |

Story issues should follow this naming format:

`US-XXXXX: <short description>`

Each story issue should link to the related story file, branch, and pull request when available.

Non-story work should be tracked separately in the Technical Backlog and should not use the `user-story` label. These tasks may use prefixes such as `NO-STORY`, `CHORE-000`, or `OPS-000` depending on the type of work.

Automation rules should stay lightweight:

- New sprint story issues start in **Backlog**.
- Issues move to **In Progress** when active branch work begins.
- Issues move to **In Review** when a related pull request is opened.
- Issues move to **Done** when the pull request is merged and the issue is closed.

Pull requests that complete a story should include a closing keyword such as:

`Closes #<issue-number>`

Partial or supporting work should use non-closing references such as:

`Refs #<issue-number>` or `Related to #<issue-number>`

This prevents stories from closing before acceptance criteria and completed-story documentation are finalized.

### 🔹 Shared Documents

Located in `docs/shared/`, including:

- `product-overview.md`
- `user-personas.md`
- `feature-list.md`
- `roadmap.md`
- `agile-methodology.md`
- `ci-cd.md`

These serve as living documents and may be referenced by multiple sprints.

### 🔹 Sprint Documents

Each sprint has its own folder: `docs/sprints/sprint-XX/`, containing:

- `sprint-overview.md`
- `user-stories.md`
- `completed-stories.md`
- `retrospective.md`

---

## 📆 Sprint Lifecycle

1. **Backlog Refinement**
   - Define user stories & acceptance criteria in user-stories.md
   - Add them to the backlog index (`docs/shared/user-stories/README.md`) with priority and persona link  
   - Re-prioritize unfinished stories as needed  

2. **Sprint Planning**  
   - Define the sprint goal in `roadmap.md`  
   - Select 1–3 stories from the backlog for the sprint  
   - Create GitHub Issues for each story and any related tasks, labeled with the story ID and sprint  
   - Track Issues on the appropriate GitHub Project board:
     - `Practica – Sprint Board` for active sprint user stories
     - `Practica – Technical Backlog` for non-story work such as chores, refactors, documentation cleanup, infrastructure, and workflow tasks
   - Use the Kanban workflow rules defined in the [Kanban Boards](#-kanban-boards) section

3. **Development**  
   - Create a `feature/*` branch per story  
   - Develop and commit freely, referencing story IDs in commits  
   - Test across devices and browsers  

4. **Integration & Wrap-Up**  
   - Squash-merge each feature into `main` (one commit per story)  
   - Record outcomes in `completed-stories.md`, including acceptance results, delivery notes, and evidence (PRs, demos, screenshots)  
   - Update shared docs (e.g., roadmap, feedback log)  
   - Tag the sprint milestone in `main` (e.g., `sprint-01-complete`) to preserve a versioned snapshot of completed work  

5. **Review & Retrospective**  
   - Share deployed PWA with testers and record feedback in `feedback-log.md`  
   - Document reflections in `retrospective.md` (what worked, what to improve)  
   - Update the backlog and `roadmap.md` for the next sprint  

Optional: for public releases, create versioned tags (e.g., `v0.1.0`).  

---

## 🔄 Git Flow

```bash
# Start a feature branch
git checkout -b feature/US-00002-login

# Work and commit with full history
git commit -m "feat(auth): add login form [US-00002]"

# Squash into main when story is complete
git checkout main
git merge --squash feature/US-00002-login
git commit -m "US-00002: Login with email"

# Tag sprint milestone at sprint end
git tag -a sprint-01-complete -m "End of Sprint 01"
git push origin sprint-01-complete

# Tag release if public
git tag -a v0.1.0 -m "First alpha release"
git push origin v0.1.0
```

---

## 🔐 Commit Message Convention

All commits follow this format:

`<type>(<scope>): <summary> [Story ID]`

- Example: `feat(auth): add login validation [US-00004]`
- Types: `feat`, `fix`, `docs`, `test`, `refactor`, `style`, `chore`
- Scope is optional but encouraged for clarity
- Bracketed Story ID links commit to sprint planning

Documentation updates should use the `docs()` type and include the path to the updated file.

Example:
docs: updated shared/user-personas.md to include new target learner group [US-00003]

### 🔸 Non-Story Commits

Occasionally, work arises outside of planned user stories. Use special prefixes:

Use the following prefixes when appropriate:

- `NO-STORY:` – Unplanned fixes or changes not tied to a story
- `CHORE-000:` – Refactors, cleanup, or dev tools updates
- `OPS-000:` – CI/CD, deployment, or config work

Example:

NO-STORY: Fix Firebase config for staging environment
CHORE-000: Add ESLint config and fix lint errors
OPS-000: Update GitHub Actions cache settings for Expo builds

Non-story commits should be documented in the Sprint Retrospective for visibility and included in squash merges like any other feature into main.

---

## 🧪 Testing Strategy (Planned)

I plan to implement:

* Unit testing (e.g., using Jest)
* Manual testing on mobile and desktop
* Future: integration or end-to-end testing

Each feature branch should include any relevant unit tests. Test coverage should be committed alongside the code it tests.

---

## 🔄 CI/CD Pipeline (Planned)

We will use GitHub Actions to:

* Run unit tests on push and pull requests
* Ensure builds are passing before merge
* Deploy automatically to Netlify

---

## 📌 License

This project uses a **restrictive portfolio license**:

> Viewable for educational/demo purposes only. Do not reuse or distribute.

---

## 🧪 In Practice

This methodology evolves over time. For example, [Sprint 0](../sprints/sprint-0/sprint-overview.md) established our base structure and tooling. Future sprints may refine workflow, testing, or release practices based on real usage.
