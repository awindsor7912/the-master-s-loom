![The Master's Loom Banner](loom-banner.png)

# The Master's Loom
**An experimental TTRPG campaign management system, evolving toward a real-time AI-augmented platform.**

## 🌌 The Vision
The Master's Loom is a "Single Source of Truth" platform designed to bridge the gap between high-fantasy storytelling and real-time data management. By eliminating paper silos and manual tracking, the system allows Dungeon Masters and Players to maintain narrative immersion while the "Game State" is synchronized in the background.

## Current Development Path

The Master's Loom is currently being prototyped in **MIT App Inventor** as a learning-first build.

### Why this shift?
The original target stack was **FlutterFlow + Firebase**, later expanded to consider **Supabase**. However, because this project is currently self-funded and learning-driven, the immediate goal is to:
- learn core app concepts
- prototype the data model and user flows
- validate the campaign-management experience
- defer platform-specific scaling decisions until later

### Planned Build Phases
1. **Phase 1 – MIT App Inventor Prototype**
   - Core screens
   - Local/simple cloud data
   - Campaign, character, session, and notes workflows
   - Learning app fundamentals by building

2. **Phase 2 – Platform Rebuild**
   - Rebuild validated workflows in FlutterFlow
   - Evaluate **Supabase** or **Firebase** for backend services
   - Add cleaner auth, data structure, and UX

3. **Phase 3 – Advanced Features**
   - Real-time sync
   - AI-generated summaries
   - Whisper system
   - Shared battlemap/state management

## ⚔️ Key Capabilities
* **Live Session HUD:** A bi-directional dashboard where player updates (HP, AC, Spell Slots) reflect instantly on the DM’s "Combat Monitor".
* **Chronicle Engine:** A multimodal logging system that uses AI to synthesize live session transcripts into automated narrative recaps.
* **Interactive Battlemap:** A shared digital canvas featuring "Smart Figurines" that track position and status across all connected devices in real-time.
* **The Whisper Network:** A secure, real-time messaging layer for private plot-point communication without breaking table immersion.

## 🛠️ Architectural Goals
1. **Low Latency:** Optimized for <100ms updates for critical combat statistics.
2. **Platform Agnostic:** A single-codebase approach ensuring a seamless experience across Web, iOS, and Android.
3. **AI-Native Logic:** Integrated pipelines for narrative assistance, world-building, and session summarization.

## Planned Features

- Campaign management
- Character tracking
- Session notes
- World-building elements
- Inventory and item tracking

## ⚖️ Intellectual Property & Proprietary Rights
**Copyright © 2026 Ashley Windsor. All Rights Reserved.**

"The Master's Loom," its associated brand identity, system architecture, data schemas, and user experience frameworks are the exclusive intellectual property of the author. 

**Public Disclosure Notice:**
This repository serves as a public design journal and architectural portfolio. The presence of this documentation in a public forum does **not** constitute a license for:
* Reproduction or distribution of these architectural frameworks.
* The commercial or private development of software based on these specific schemas.
* The use of "The Master's Loom" branding or trade dress.

For inquiries regarding collaboration or professional discussion, please contact the author via LinkedIn.
