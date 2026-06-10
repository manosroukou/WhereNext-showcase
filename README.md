# WhereNext

> Swipe your way to your next experience — discover restaurants, events, and outdoor activities the way you discover everything else worth discovering.

<p align="center">
  <!-- Replace with your app icon or a hero banner -->
  <img src="screenshots/hero.png" alt="WhereNext" width="720"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-iOS%2017%2B-blue.svg" alt="Platform"/>
  <img src="https://img.shields.io/badge/Swift-5.9-orange.svg" alt="Swift"/>
  <img src="https://img.shields.io/badge/UI-SwiftUI-purple.svg" alt="SwiftUI"/>
  <img src="https://img.shields.io/badge/Architecture-MVVM-green.svg" alt="MVVM"/>
  <img src="https://img.shields.io/badge/Status-In%20Development-yellow.svg" alt="Status"/>
</p>

---

## 📖 Overview

**WhereNext** is an iOS application that reimagines how people discover the world around them. Instead of scrolling through endless lists or wading through filters, users browse restaurants, events, and outdoor activities through a fast, intuitive swipe interface — swipe right to save, swipe left to skip.

The project is built around a two-sided product model:

- **For users:** a frictionless, location-aware discovery experience, with a personalization engine that learns from swipe behavior.
- **For venues:** a subscription-based platform to extend their listings with rich, interactive *frames* — menus, event announcements, photo galleries, push notifications to followers, and more.

---

## ⚠️ Project Status

WhereNext is currently a **concept project in active development**. The iOS frontend is functional and explorable end-to-end; the backend, live venue data ingestion, and the full recommendation engine are part of the ongoing roadmap.

This repository is a **public showcase** of the project's vision, design, and engineering progress. The production codebase is kept private while the project matures — feel free to reach out if you'd like a deeper walkthrough.

---

## ✨ Features

### For Users
- **Swipe-based discovery.** A clean, Tinder-style card interface for browsing nearby venues and events, with hand-tuned gesture animations.
- **Detailed venue profiles.** Tap into any card to see full descriptions, photos, videos, user reviews, and the venue's interactive *frames*.
- **Location-aware map view** *(in progress).* Adjustable-radius map for exploring venues spatially, powered by Core Location and MapKit.
- **Personalized recommendations** *(in progress).* A swipe-driven preference model combining TF-IDF on content features with embedding-based semantic similarity.
- **Authentication.** Polished login and sign-up flows.

### For Venues *(planned)*
- **Creator profiles** with media upload and listing management.
- **Modular content frames** — menus, event schedules, follower notifications, galleries.
- **Subscription tiers** — freemium model with paid feature unlocks.

---

## 📱 Screenshots

<!-- Place your screenshots in a /screenshots folder at the repo root.
     Recommended: 3:6.5 ratio (iPhone), ~300–400px wide for the table cells. -->

| Discovery (Swipe) | Venue Profile | Map View |
|:---:|:---:|:---:|
| <img src="screenshots/swipe.png" width="240"/> | <img src="screenshots/profile.png" width="240"/> | <img src="screenshots/map.png" width="240"/> |

| Login | Sign Up | Creator Flow |
|:---:|:---:|:---:|
| <img src="screenshots/login.png" width="240"/> | <img src="screenshots/signup.png" width="240"/> | <img src="screenshots/creator.png" width="240"/> |

> *A short demo GIF of the swipe interaction will be added here once recorded.*

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Language | Swift 5.9 |
| UI Framework | SwiftUI |
| Architecture | MVVM |
| Location | Core Location, MapKit |
| Animations | SwiftUI gesture & transform APIs, custom spring tuning |
| Recommendations *(WIP)* | TF-IDF, vector embeddings, cosine similarity |
| Backend | *Design phase* |

---

## 🏗 Architecture

WhereNext follows a clean **MVVM** architecture with SwiftUI's reactive property wrappers (`@State`, `@StateObject`, `@ObservedObject`, `@EnvironmentObject`) handling view–view-model bindings. Views remain declarative and stateless; ViewModels own state and orchestrate domain services such as `LocationService` and the forthcoming `RecommendationService`.

```text
WhereNext/
├── Views/              # SwiftUI screens (Discovery, Profile, Map, Auth)
├── ViewModels/         # State & business logic per screen
├── Models/             # Domain models (Venue, Event, User, Frame…)
├── Services/           # LocationService, RecommendationService, …
├── Components/         # Reusable UI (SwipeCard, FrameView, …)
└── Resources/          # Assets, fonts, mock data
```

---

## 🎯 Technical Highlights

**Custom swipe animation engine.** The card stack uses gesture-driven transforms with spring physics tuned by hand — drag rotation, threshold-based snap-back vs. fly-off, and stack-depth animations as the top card is removed. The interaction is built on SwiftUI primitives rather than third-party libraries, and it's the piece of the app I'm most proud of.

**Two-sided product design.** Beyond consumer UX, the app models a full venue/creator side with separate authentication, content creation, and a planned subscription system. The goal was to design a real product, not just a feature.

**Recommendation engine R&D.** Prototyping a hybrid approach that combines TF-IDF on textual venue features (cuisine, tags, descriptions) with dense embeddings for semantic similarity, scored against the user's swipe history. Exploring on-device inference to preserve user privacy and avoid round-trips.

**Location-aware UX.** Core Location integration with live updates and an adjustable radius, so the discovery feed adapts to the user's context — tighter downtown, wider in suburban areas.

---

## 🗺 Roadmap

- [x] Core swipe interface with custom animations
- [x] Venue profile view with media and reviews
- [x] Login & sign-up flows (user + creator)
- [x] Core Location integration
- [ ] Adjustable-radius map view *(in progress)*
- [ ] TF-IDF + embedding recommendation engine *(in progress)*
- [ ] Backend service (auth, venue data, persistence)
- [ ] Creator dashboard & frame management
- [ ] Push notifications for events
- [ ] TestFlight beta
- [ ] App Store submission

---

## 👤 About the Developer

I'm **Emmanouil (Manos) Roukounakis**, a Computer Science student at the Athens University of Economics and Business (AUEB) with an Erasmus exchange at NTNU in Trondheim, Norway. I work primarily in iOS, with a strong interest in distributed systems and applied ML, and I like building products end-to-end — from idea to running app.

**Get in touch:**
- 💼 LinkedIn: [your-linkedin-url]
- 📧 Email: [your-email]
- 🐙 GitHub: [your-github-profile]

---

## 📄 Code Access

The full source of WhereNext is **private** while the project is in active development. If you're a recruiter or potential collaborator interested in a deeper technical walkthrough, please reach out — I'm happy to share more under the right circumstances.

---

<p align="center"><i>Built with ☕ in Athens & Trondheim.</i></p>
