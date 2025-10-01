# Test Plan – Practica App

## 🎯 Purpose
Define the overall strategy for testing the app, ensuring features meet acceptance criteria and work reliably across devices.  
This document is high-level; file organization and execution details are in [testing-docs.md](./testing-docs.md).

---

## 🧩 Scope
MVP testing covers:
- Flashcard viewer
- Audio playback
- Basic responsiveness (phone, tablet, desktop)

Post-MVP: multiple-choice quizzes, progress tracking, gamification.

---

## 🛠️ Approaches
- **Functional (black-box):** verify expected behavior from user perspective  
- **Exploratory:** time-boxed sessions to uncover unexpected issues  
- **Responsiveness:** check layout/interaction across P1 and P2 devices  
- **Regression (light):** re-run critical tests after new features  
- **Accessibility (basic):** ensure essential controls are keyboard/touch accessible  
- **Unit Testing:** validate small utilities (e.g., random selection, score calc) with Jest  
- **Integration Testing:** ensure modules work together (e.g., quiz scoring updates progress)  
- **UI/Component Testing:** confirm components render correctly in different states  
- **Acceptance Testing:** verify user stories against acceptance criteria before closing  
- **Input Validation/Security (basic):** test handling of invalid or malicious input

---

## 📱 Device Matrix
- **P1:** iPhone (Safari), Android (Chrome), Desktop Chrome  
- **P2:** iPad (Safari), Desktop Edge/Safari  

---

## 📋 Traceability
- **Source of criteria:** `docs/shared/user-stories/US-XXXX.md`  
- **Test cases:** `docs/shared/test-cases/` (one file per case)  
- **Sprint scope:** `docs/sprints/sprint-XX/sprint-scope-testing.md`  
- **Completed stories:** reference the specific cases executed  
- **Session logs:** stored in `sprints/sprint-XX/tests/`  

---

## 🐞 Bug Tracking
- Tracked in GitHub Issues with labels:  
  - `bug`  
  - Severity: `P0` (critical), `P1` (major), `P2` (minor)  
  - Sprint tag (e.g., `sprint-02`)  

---

## ✅ Acceptance Gate (Definition of Done)
A story is **Done** when:
1. All acceptance criteria are tested and met  
2. P1 device tests pass; no open P0/P1 bugs  
3. Evidence attached (screenshots, session logs, or demo link)  
4. Linked commits/issues closed; squash commit merged to `main`  
