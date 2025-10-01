# Tech Stack Overview

This document outlines the technologies, tools, and services selected for the development and deployment of the application. It supports Agile workflows, simplifies future expansion, and enables effective cross-platform testing.

---

## 🧠 Core Stack

| Layer            | Technology           | Notes                                                  |
|------------------|----------------------|--------------------------------------------------------|
| UI Framework     | React Native + Expo  | Cross-platform components with web + native support    |
| Web Framework    | React Native Web     | Makes the same code render in browsers                 |
| Styling          | NativeWind           | Tailwind-style utility classes across all platforms    |
| Localization     | i18next              | Enables multilingual support with fallback and switching |
| State Management | Zustand              | Lightweight global state (may be replaced by Redux Toolkit later) |
| Navigation       | React Navigation     | Mobile + conditional web routing support               |

---

## 🌐 Deployment Strategy

### Web (Progressive Web App)
- **Platform**: Firebase Hosting
- **Purpose**: Simulate a mobile app via browser for testing and public access
- **Capabilities**:
  - Add to home screen
  - Offline support (planned)
  - No install required
- **Free Tier**:
  - 1 GB storage
  - 10 GB bandwidth/month
- **Paid Tier**:
  - $0.026/GB storage
  - $0.15/GB bandwidth

### Android
- **Platform**: Expo EAS Build → Google Play
- **Process**:
  - Build via `eas build -p android`
  - Output: `.aab` or `.apk`
- **Free Tier**: Unlimited local builds
- **Paid Tier (EAS)**: $0/month (basic), $29/month+ for cloud builds and CI/CD features

### iOS
- **Platform**: Expo EAS Build → App Store
- **Process**:
  - Build via `eas build -p ios`
  - Submit with EAS Submit or TestFlight
- **Requirements**:
  - Apple Developer Account: $99/year
  - CI/CD or access to a Mac
- **EAS Free Tier**: Limited builds, no custom build profiles
- **Paid Tier**: $29/month+ for custom workflow, GitHub CI/CD

---

## ☁️ Backend Services

### Firebase (Primary)
- **Authentication**: Email/password and third-party support
- **Firestore**: Scalable NoSQL database (real-time)
- **Storage**: For optional audio/image files
- **Free Tier**:
  - 10K Auths/month
  - 50K reads/day (Firestore)
  - 1 GB storage
- **Blaze Tier (pay-as-you-go)**:
  - $0.18/100K reads
  - $0.026/GB storage
  - $0.12/GB bandwidth

---

## 📱 Progressive Web App (PWA) Considerations

- Built using Expo + React Native Web
- Tested in browser, simulates a native app
- Ideal for pre-release testers on mobile without needing app stores
- Installable directly from browser (Add to Home Screen)
- Offline capabilities planned using Service Workers

---

## 🧪 Agile Value Alignment

- **Web-first** testing ensures rapid feedback and iteration
- **Cross-platform stack** reduces duplication and future migration costs
- **Firebase** enables quick user auth and data storage without backend engineering overhead
- **EAS** provides consistent deployment paths, including beta testing and internal distribution

---

## 🔮 Future Considerations

- Transition to Supabase if SQL-style data structures or custom API control become necessary
- Add CI/CD for automated testing and release flows
- Consider React Router or Next.js if the web interface becomes more content-driven

