# Learn Visaya App

A cross-platform **modular learning platform** where users can create and adapt study materials into a variety of exercise types (e.g., flashcards, matching, sorting, quizzes).  

The platform is **general-purpose** but is demonstrated with **Visaya → English vocabulary** as the initial content example.  

This project is being developed as a solo portfolio piece to demonstrate both **business analysis** and **front-end development** capabilities in an Agile setting. All documentation and code are maintained publicly to showcase a full product lifecycle.

---

## 🎯 My Role (BA, Developer, DevOps, QA)

As the sole contributor, I am responsible for all stages of the project:

### 👓 Business Analysis
- Defined the product vision, goals, and scope  
- Identified and modeled key user personas  
- Translated high-level needs into user stories with acceptance criteria  
- Iteratively collected and incorporated feedback from early testers  
- Created and maintained all stakeholder documentation in the `/docs` folder, including:
  - Product Overview  
  - Feature List  
  - Agile Methodology  
  - Sprint Plans  
  - Roadmap  
  - User Personas  
  - Project Tracking  

### 🧑‍💻 Development
- Designed the initial UI layout and component interactions  
- Plan to develop the application front-end using **React Native with Expo**  
- Will adapt and style components for both mobile and web using **React Native Web**  
- Will handle navigation, state, and localization strategy  
- Drafted the data model and collections structure for integration with **Firebase (Firestore)** to enable scalable and structured storage for user content and progress  

### ⚙️ CI/CD and DevOps
- Manage Git version control and branching strategy  
- A living **CI/CD plan** is documented in [`docs/shared/ci-cd-overview.md`](docs/shared/ci-cd-overview.md)  
- Plan to configure **GitHub Actions** for continuous integration:
  - Auto-install dependencies and build the app on push  
  - Future auto-deploys to **Netlify (web)** and **EAS (mobile)**  

### 🧪 Testing and Feedback Loops
- Conduct exploratory testing and collect early user feedback  
- Validate usability and interface consistency across platforms  
- Maintain testing docs under `/docs/shared/`  

---

## 📌 Project Goals

### MVP
- Web-first, responsive app (works on phone, tablet, laptop)  
- Author simple study content (starting with card-based entries)  
- Flashcard study mode (baseline exercise type)  
- Preloaded Visaya → English vocabulary as demo content  

### Backlog (Post-MVP)
- Additional exercise types (matching, sorting, quizzes)  
- Multimedia support (images, audio, video)  
- User accounts for saving progress  
- Sharing and collaboration on study content  
- Gamification (progress tracking, badges, streaks)  
- Spanish-language interface  
- Offline PWA support  

---

## 🚀 Tech Stack (planned)
- **Expo** (React Native) + **React Native Web**  
- **i18next** (localization), **Zustand** or **Redux Toolkit** (state)  
- **React Navigation** (mobile) & **React Router** (web)  
- **NativeWind/Tailwind** (optional styling)  
- **Firebase** (Firestore, Auth) for content and user progress  
- **GitHub Actions** (CI), **Netlify** (web), **EAS** (mobile builds)  
- Markdown for documentation  

---

## 📂 Current Folder Structure

```text
learn-visaya-app/
├── .gitignore
├── LICENSE
├── readme.md
├── cmsg/
├── docs/
│   ├── shared/
│   │   ├── Templates/
│   │   │   ├── completed-stories.md
│   │   │   ├── features-list.md
│   │   │   ├── test-cases.md
│   │   │   └── agile-methodology.md
│   │   ├── ci-cd-overview.md
│   │   ├── feature-list.md
│   │   ├── feedback-log.md
│   │   ├── product-overview.md
│   │   ├── project-tracking.md
│   │   ├── roadmap.md
│   │   ├── techstack.md
│   │   ├── test-plan.md
│   │   ├── testing-docs.md
│   │   └── user-personas.md
│   └── sprints/
│       └── sprint-0/
│           ├── Complete Stories/
│           │   └── example.md
│           ├── feedback.md
│           ├── retrospective.md
│           └── sprint-overview.md
```

# 📄 Documentation

### 🔍 Discovery & Planning
- [Product Overview](docs/shared/product-overview.md)  
- [User Personas](docs/shared/user-personas.md)  
- [Roadmap](docs/shared/roadmap.md)  

### 📋 Requirements & Modeling
- [Feature List](docs/shared/feature-list.md)  
- [Project Tracking](docs/shared/project-tracking.md)  
- [Tech Stack](docs/shared/techstack.md)  

### ✅ Testing & Quality Assurance
- [Test Plan](docs/shared/test-plan.md)  
- [Testing Docs](docs/shared/testing-docs.md)  
- [Test Cases (Template)](docs/shared/Templates/test-cases.md)  
- [Feedback Log](docs/shared/feedback-log.md)  

### 🌀 Process & Methodology
- [Agile Methodology (Template)](docs/shared/Templates/agile-methodology.md)  
- [CI/CD Overview](docs/shared/ci-cd-overview)  

### 🗓️ Sprints
All sprint documentation is maintained under [`/docs/sprints/`](docs/sprints/).  
Each sprint includes an overview, completed stories, feedback, and retrospective.  

### 📜 License
- [License](LICENSE)  

---

## 📬 Contact

If you'd like to connect, collaborate, or discuss this project:

Mauricio Rossi  
📧 mauricio.j.rossi@outlook.com  
📍 London, ON (relocating to Toronto, 2025)  
🌐 [LinkedIn](https://www.linkedin.com/in/mauricio-rossi/)  

---

*Initial commit: documentation-first structure established; implementation to follow in subsequent sprints.*
