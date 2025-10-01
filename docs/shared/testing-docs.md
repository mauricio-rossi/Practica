# Testing Documentation Guide – Practica App

This file explains how testing files are organized, named, and linked across the repo.  
It complements the high-level strategy in [test-plan.md](./test-plan.md).

---

## 📂 Folder Structure

docs/
├─ shared/
│  ├─ user-stories/                  # backlog (planned stories)
│  │   ├─ README.md                  # backlog index
│  │   ├─ US-0001.md
│  │   └─ US-0002.md
│  └─ test-cases/                    # reusable, single-file test cases
│      ├─ README.md                  # index of all cases
│      ├─ TC-FC-0001.md              # Flashcard – View first card
│      ├─ TC-FC-0002.md              # Flashcard – Flip card
│      └─ TC-AU-0001.md              # Audio – Play pronunciation
└─ sprints/
   └─ sprint-01/
      ├─ sprint-overview.md          # goal, planned stories, related docs
      ├─ sprint-scope-testing.md     # which test cases executed this sprint
      ├─ completed-stories/          # one file per story outcome
      │   ├─ US-0001.md              # references test cases + session logs
      │   └─ US-0002.md
      └─ tests/                      # actual test execution (per sprint)
         ├─ test-session-2025-09-24.md   # log of cases run + results
         └─ screenshots/                 # proof attached to session/story
            ├─ tc-fc-0001_iphone.png
            ├─ tc-fc-0002_android.png
            └─ tc-au-0001_chrome.png

---

## 🧾 File Types & Purpose

| File | Purpose |
|------|---------|
| `shared/test-cases/TC-XXXX.md` | Single test case (steps, expected result, tags) |
| `shared/test-cases/README.md` | Index of all cases with links, grouped by feature |
| `sprint-XX/sprint-scope-testing.md` | Which test cases were executed in this sprint |
| `sprint-XX/completed-stories/US-XXXX.md` | Story results: which cases verified it, evidence, pass/fail |
| `sprint-XX/tests/test-session-YYYY-MM-DD.md` | Execution log: results of running cases (story + non-story) |

---

## 🔖 Naming Conventions
- **Test cases:** `TC-<feature>-<number>.md`  
  Example: `TC-FC-0001.md` (Flashcards – Case 1)  
- **Session logs:** `test-session-YYYY-MM-DD.md`  
  Example: `test-session-2025-09-24.md`  

---

## 🧪 Templates

### Test Case (`TC-FC-0001.md`)
```markdown
---
id: TC-FC-0001
title: View first card (front)
feature: flashcards
priority: P1
type: functional
tags: [flashcards, mvp]
---

## Preconditions
- Demo deck with ≥ 5 cards loaded

## Steps
1. Open app → Flashcards
2. Observe the first card

## Expected
- Front shows Visaya word
- No layout overflow
- Controls visible

## Notes
- Test long/short words
