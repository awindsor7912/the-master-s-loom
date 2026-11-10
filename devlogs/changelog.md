---
title: "Development Changelog"
description: "Project milestones, decisions, and superseded experiments."
---

# 🛠️ Development Log: The Master's Loom

Entries preserve the project's historical experiments and current implementation milestones. The active Next.js frontend is housed in the separate public [masters-loom-app](https://github.com/awindsor7912/masters-loom-app) repository; features marked as planned remain unimplemented.

---

## [Phase 1: Initial UI/UX & Wireframing] - 2026-03-14

### 🚀 Progress Update
* **UI Prototyping Started:** Successfully initiated the primary design system in **FlutterFlow**.
* **Player HUD (v0.1):** Completed high-fidelity wireframes for the mobile "Player HUD." Focused on the "Reactive Health Slider" and "Active Spell Slot" indicators to ensure high-visibility during low-light table play.
* **DM Combat Monitor (v0.1):** Drafted the desktop "Command Center" view. Integrated a multi-pane layout to show the "Whisper" chat alongside real-time party vitals.
* **Data Flow Testing:** Validated the **Firebase Firestore** schema logic for bi-directional syncing of Hit Points (HP) between the Player and DM views.

### 🎯 Current Focus
* Finalizing the "Dark Mode" aesthetic (Obsidian/Violet) to match the project branding.
* Researching **Gemini API** integration for the automated "Session Chronicle" summaries.

### 🛡️ Known Challenges
* Optimizing the Interactive Map layer for mobile screen real estate without sacrificing clarity.

---

---

## [Architecture Direction Update] - 2026-11-09

### Decision
- Selected a **web-first** prototype rather than MIT App Inventor, FlutterFlow, or a Godot-based game client.
- Preferred stack: **Next.js / React / TypeScript + Supabase PostgreSQL/Auth/Realtime/Storage**; **React Konva** for an eventual interactive map.
- Prioritized synchronized DM/player interfaces, authoritative combat state, browser access, and role-based data security.
- Selected **D&D Fifth Edition (2024 revision)** as the initial supported ruleset; designed the application core to support versioned ruleset modules later.
- Replaced the rebuild-oriented roadmap with incremental delivery of a single web application.

### Current status
The initial Next.js frontend shell has been implemented and pushed to <a href="https://github.com/awindsor7912/masters-loom-app">the application repository</a>. Dashboard, Campaigns, Characters, and Sessions routes are available as early workspace screens. Authentication, persisted campaign data, multiplayer synchronization, and maps are planned, not implemented.

See [November 9, 2026 — Next.js Application Foundation](2026-11-09-nextjs-foundation.md).
