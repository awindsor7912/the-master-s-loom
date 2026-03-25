![The Master's Loom Banner](loom-banner.png)

# The Master's Loom
**An experimental TTRPG campaign management system, evolving toward a real-time AI-augmented platform.**

## 🌌 The Vision
The Master's Loom is a "Single Source of Truth" platform designed to bridge the gap between high-fantasy storytelling and real-time data management. By eliminating paper silos and manual tracking, the system allows Dungeon Masters and Players to maintain narrative immersion while the "Game State" is synchronized in the background.

## 🎯 Project Purpose 

This project is primarily a hands-on learning initiative designed to build practical experience in:

- Application architecture and system design
- Frontend and backend integration
- Data modeling and schema design
- Iterative development across multiple technology stacks

The goal is not just to build a functional application, but to develop a deep understanding of how scalable, modern applications are designed and implemented.

## Current Development Path

The Master's Loom is currently being prototyped in **MIT App Inventor** as a learning-first build. The project follows a multi-phase development strategy, separating learning from production implementation.

**Current Phase (Phase 1 – Prototype & Validation)**
- Built using MIT App Inventor
- Focused on learning UI structure and navigation
- Testing core workflows (campaigns, characters, sessions)
- Using local storage (TinyDB or equivalent)
- Rapid iteration without concern for scalability

### Why this shift?
The original target stack was **FlutterFlow + Firebase**, later expanded to consider **Supabase**. However, because this project is currently self-funded and learning-driven, the immediate goal is to:
- learn core app concepts
- prototype the data model and user flows
- validate the campaign-management experience
- defer platform-specific scaling decisions until later

### Planned Build Phases
1. **Phase 1 – MIT App Inventor Prototype (Learning & Validation)**
   - Core screens
   - Local/simple cloud data
   - Campaign, character, session, and notes workflows
   - Learning app fundamentals by building

2. **Phase 2 – Platform Rebuild (Structured Development)**
   - Rebuild validated workflows in FlutterFlow
   - Evaluate **Supabase** or **Firebase** for backend services
   - Add cleaner auth, data structure, and UX

3. **Phase 3 – Expansion (Advanced Features)**
   - Real-time sync
   - AI-generated summaries
   - Whisper system
   - Shared battlemap/state management

## 🧪 Current Prototype Features (MIT App Inventor)

- Basic campaign creation
- Character tracking
- Session notes
- Local data storage (TinyDB or equivalent)
- Simple navigation between screens

## ⚠️ Current Limitations

- Prototype built in MIT App Inventor (not production-ready)
- No real-time sync
- No persistent backend yet
- Limited UI flexibility
- Will require rebuild in future phases

## Planned Features

- Campaign management
- Character tracking
- Session notes
- World-building elements
- Inventory and item tracking

## ⚔️ Target Capabilities (Long-Term Vision)
* **Live Session HUD:** A bi-directional dashboard where player updates (HP, AC, Spell Slots) reflect instantly on the DM’s "Combat Monitor".
* **Chronicle Engine:** A multimodal logging system that uses AI to synthesize live session transcripts into automated narrative recaps. 
* **Interactive Battlemap:** A shared digital canvas featuring "Smart Figurines" that track position and status across all connected devices in real-time.
* **The Whisper Network:** A secure, real-time messaging layer for private plot-point communication without breaking table immersion.

## 🛠️ Future Architectural Goals
1. **Low Latency:** Low-latency synchronization for critical combat statistics.
2. **Platform Agnostic:** A single-codebase approach ensuring a seamless experience across Web, iOS, and Android.
3. **AI-Native Logic:** Integrated pipelines for narrative assistance, world-building, and session summarization.
4. **Cloud-Based Backend:** Supabase or Firebase for database storage, user management, and secure authentication. 

## 📌 Project Philosophy

This project is intentionally iterative and exploratory.

Rather than aiming for immediate production readiness, The Master's Loom is designed as a structured learning journey—building, testing, refining, and rebuilding with better tools and deeper understanding at each stage.

## 📖 Status

🚧 Early Prototype — Actively in development and experimentation phase

## 📂 Project Documentation

- [Roadmap](roadmap.md)
- [System Architecture](architecture/system-architecture.md)
- [Data Schema](data/data-schema.md)
- [User Journey](user-journey.md)
- [Tech Evaluations](evaluations/tech-evaluations.md)
- [Prototype Docs](prototype/README.md)
- [Dev Logs](devlogs/changelog.md)
- [Learning Log](learninglog/)

## ⚖️ Intellectual Property & Proprietary Rights
**Copyright © 2026 Ashley Windsor. All Rights Reserved.**

"The Master's Loom," its associated brand identity, system architecture, data schemas, and user experience frameworks are the exclusive intellectual property of the author. 

**Public Disclosure Notice:**
This repository serves as a public design journal and architectural portfolio. The presence of this documentation in a public forum does **not** constitute a license for:
* Reproduction or distribution of these architectural frameworks.
* The commercial or private development of software based on these specific schemas.
* The use of "The Master's Loom" branding or trade dress.

For inquiries regarding collaboration or professional discussion, please contact the author via LinkedIn.
