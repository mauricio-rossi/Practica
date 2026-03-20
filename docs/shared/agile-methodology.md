# 📘 Agile Methodology – Practica App

This document outlines the Agile approach used in the development of the **Practica App** project. It serves as a living reference to define processes, roles, and workflows as they evolve.

## 📑 Table of Contents

- [🎯 Agile Philosophy](#-agile-philosophy)
- [🧩 Core Agile Artifacts](#-core-agile-artifacts)
- [📆 Sprint Lifecycle](#-sprint-lifecycle)
- [🌿 Branching and Promotion Workflow](#branching-and-promotion-workflow)
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
- Links to the original story file and the completed story record when available

This file acts as the **central map** connecting backlog entries with sprint outcomes.  

**Example Story Index (`docs/shared/story-index.md`):**

| ID      | Title          | Sprint  | Outcome                  | Result Link |
|---------|----------------|---------|--------------------------|-------------|
| US-00001 | Email Sign-up  | Sprint 1 | ✅ Completed             | [Results](../sprints/sprint-01/completed/US-00001.md) |
| US-00002 | Login          | Sprint 2 | 🔄 In Progress           | - |
| US-00003 | Profile Page   | Sprint 2 | ⏸ Split → US-00010, US-00011 | - |
| US-00004 | Password Reset | Sprint 2 | ❌ Closed (not needed)   | - |

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
  Defines the sprint goal, planned stories, and high-level scope for the iteration.

- `feedback.md`  
  Records raw observations, tester feedback, and issues discovered during the sprint.

- `retrospective.md`  
  Documents reflections at the end of the sprint, including what worked well and what should improve.

- `completed/`  
  Contains a Completed Story document (`US-XXXXX.md`) for each story accepted during the sprint.  
  These files record acceptance verification, delivery notes, and evidence of delivered functionality.

---

## 📆 Sprint Lifecycle

1. **Backlog Refinement**
   - Define user stories & acceptance criteria in the story files located in `docs/shared/user-stories/`
   - Add stories to the backlog index (`docs/shared/user-stories/README.md`) with priority and status
   - Re-prioritize unfinished stories as needed

2. **Sprint Planning**
   - Define the sprint goal in `roadmap.md`
   - Select 1–3 stories from the backlog for the sprint
   - Record the sprint plan in `docs/sprints/sprint-XX/sprint-overview.md`
   - Create GitHub Issues for each story and any related tasks
   - Track Issues on the GitHub Project board (Kanban) for sprint visibility

3. **Development**
   - Create a `feature/*` branch per story
   - Implement the story and commit freely while referencing the Story ID in commits
   - Use issues and the project board to track work progress
   - Test the feature in relevant environments (mobile, web, or desktop as applicable).

4. **Acceptance Review**
   - Verify that all acceptance criteria are satisfied
   - Confirm the implementation aligns with the original story goal
   - Note any deviations, deferred work, or follow-up tasks

   Once verified, document the story using the **Completed Story template** located at:

   `docs/sprints/sprint-XX/completed/US-XXXXX.md`

   This file records:
   - Acceptance verification
   - Delivery notes
   - Evidence of delivered functionality

   The Completed Story document serves as the **final validation record** of the work delivered during the sprint.

5. **Integration**
   - Squash-merge the feature branch into `develop`
   - Ensure the squash commit references the Story ID

6. **Documentation Updates**
   - Update the **Story Index** (`docs/shared/story-index.md`) with the story outcome and result link
   - Update any relevant shared documentation (roadmap, feature list, feedback log)

7. **Sprint Promotion**
   - At the end of the sprint, squash-merge the completed sprint from `develop` into `main`
   - Tag the sprint milestone in `main` (e.g., `sprint-01-complete`) to preserve a versioned snapshot of completed work

8. **Sprint Wrap-Up**
   - Record reflections and improvement notes in `retrospective.md`
   - Carry unfinished stories back to the backlog for re-prioritization

Optional: For public releases, create version tags such as `v0.1.0`.

---

## 🌿 Branching and Promotion Workflow

The repository uses a layered branching model designed to preserve detailed development history while keeping shared integration branches concise and readable.

### Branch Strategy

| Branch | Purpose |
|------|------|
| `feature/*` | Full development history for a single user story |
| `develop` | Squashed integration branch containing completed user stories |
| `main` | Squashed sprint-level history representing stable internal milestones |
| `releases` | Squashed release-level history representing public or externally shared versions |

### Workflow

1. Each user story is implemented in a dedicated `feature/*` branch.
2. Feature branches may contain full development history including intermediate commits.
3. feature → develop → main → releases
4. At the end of a sprint, completed work is **squashed from `develop` into `main`**.
5. Stable internal versions may be promoted from **`main` to `releases`** for public distribution.

### Design Goals

This branching strategy allows the project to:

- Preserve detailed development history during story implementation
- Keep integration branches clean and readable
- Maintain clear separation between story, sprint, and release history
- Support structured Agile documentation alongside development work

---

## 🔐 Commit Message Convention

All commits follow this format:

`<type>(<scope>): <summary> [Story ID]`

- Example: `feat(auth): add login validation [US-00004]`

### Commit Types

| Type | Purpose |
|-----|-----|
| `feat` | New feature implementation |
| `fix` | Bug fix |
| `docs` | Documentation updates |
| `test` | Test additions or updates |
| `refactor` | Code restructuring without behavioral change |
| `style` | Formatting or style-only changes |
| `chore` | Tooling, maintenance, or dependency updates |

- Scope is optional but encouraged for clarity

- Bracketed Story ID links commit to sprint planning

### Documentation Commits

Documentation updates should use the `docs` type and reference the updated file or section.

Example:
docs: update shared/user-personas.md to include new target learner group [US-00003]

### 🔸 Non-Story Commits

Occasionally work arises outside planned user stories. These commits should use a special prefix.

| Prefix | Purpose |
|------|------|
| `NO-STORY:` | Unplanned fixes or small improvements not tied to a story |
| `CHORE-000:` | Tooling updates, cleanup, refactoring, or developer workflow improvements |
| `OPS-000:` | CI/CD configuration, deployment, or infrastructure changes |

Examples:

NO-STORY: fix Firebase staging configuration
CHORE-000: add ESLint configuration and resolve lint errors
OPS-000: update GitHub Actions cache configuration

Non-story commits should be documented in the **Sprint Retrospective** for visibility and are included in squash merges like any other work.

---

## 🧪 Testing Strategy

Testing will be introduced progressively as the project evolves.

The testing approach includes:

- **Unit testing** for core logic and reusable components (planned using Jest)
- **Manual testing** during development on both mobile and desktop environments
- **Future expansion** toward integration and end-to-end testing

Feature branches should include any relevant unit tests alongside the implementation they validate.

As testing infrastructure matures, coverage expectations and CI enforcement may be expanded.

---

## 🔄 CI/CD Pipeline

Continuous integration will be implemented using **GitHub Actions**.

The pipeline is intended to:

- Run unit tests on push and pull requests
- Ensure builds pass before merges are accepted
- Automate deployment for supported environments

As the project evolves, the pipeline may expand to include additional checks such as linting, build verification, or automated release steps.

---

## 📌 License

This project is distributed under a **restrictive portfolio license**.

The repository is intended for **educational and demonstration purposes only**.  
Reuse, redistribution, or commercial use is not permitted without permission.

---

## 🧪 In Practice

This methodology evolves over time. For example, [Sprint 0](../sprints/sprint-0/sprint-overview.md) established our base structure and tooling. Future sprints may refine workflow, testing, or release practices based on real usage.
