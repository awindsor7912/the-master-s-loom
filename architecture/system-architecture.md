# System Architecture

<div class="lore-card">
  <h3>Architect's Note</h3>
  <p>
    The current architecture is deliberately simple and local-first. Its purpose is to validate how the system should behave before committing to infrastructure decisions.
  </p>
  <p>
    Future architecture builds upon these validated patterns, introducing synchronization, modularity, and AI-assisted systems.
  </p>
</div>

> Note: This document describes both the current prototype architecture and the long-term target architecture for The Master's Loom.  
> The current build is being developed in MIT App Inventor and uses a simplified local-first design.  
> Future phases may rebuild these validated concepts in FlutterFlow with a cloud backend such as Supabase or Firebase.

---

## 1. Architecture Overview

The Master's Loom is being developed in stages.

### Current Prototype Architecture
The current prototype is a local-first application built to validate:
- screen structure
- user flows
- core data entities
- campaign, character, and session interactions

At this stage, the architecture is intentionally simple:
- MIT App Inventor frontend
- local storage using TinyDB or equivalent
- manually structured screen-to-screen navigation
- no real-time synchronization
- no production backend

### Long-Term Target Architecture
The long-term vision is a modular, cloud-connected platform that supports:
- shared campaign state
- real-time session updates
- AI-assisted summarization
- battlemap coordination
- multi-user interaction across devices

---

## 2. Current Prototype Components

### Frontend Layer
The prototype frontend is responsible for:
- campaign creation and editing
- character management
- session logging
- navigation between major screens

### Local Data Layer
Prototype data is stored locally for fast iteration and simple testing.

This layer is responsible for:
- saving campaign records
- linking characters to campaigns
- linking sessions to campaigns
- persisting notes between app sessions

### Workflow Validation Layer
Although not a separate technical service, the prototype phase is also validating:
- what information the user needs most often
- which data should be editable during play
- which data belongs in long-term records vs live session state

---

## 3. Future Target Components

### Client Application Layer
A future rebuild may use FlutterFlow or another frontend stack to support:
- better UI control
- reusable components
- platform consistency across mobile and web

### Backend/Data Layer
A future backend such as Supabase or Firebase would manage:
- persistent cloud storage
- authentication
- campaign sharing
- synchronized state updates
- cross-device access

### Real-Time State Layer
To support a “command center” experience, the system would use an event-driven sync model.

Key concepts:
- client updates are pushed to shared cloud state
- subscribed clients receive live updates
- combat-critical fields such as HP, AC, conditions, or actor position can refresh without manual reloads

### AI Chronicle Layer
The Chronicle Engine is the future summarization pipeline.

Proposed stages:
1. **Capture** – collect raw session content such as notes, text logs, or future audio transcripts
2. **Contextualization** – compare current session events against campaign lore, NPC records, and prior session history
3. **Synthesis** – generate a narrative summary and store it as part of the campaign history

### Battlemap/Canvas Layer
The future map system is treated as a layered interactive object:
- **Background Layer** – uploaded or generated map image
- **Grid Layer** – rule-based positioning system
- **Actor Layer** – tokens or figurines linked to characters, NPCs, or enemies
- **State Layer** – conditions, movement, visibility, and combat state

---

## 4. Data Flow by Phase

### Prototype Phase
User Input → MIT App Inventor Screens → Local Storage → Screen Refresh / Manual Review

### Future Cloud Phase
User Input → Client App → Cloud Database / Realtime Service → Other Connected Clients

### Future AI Summary Flow
Session Notes / Logs → Processing Buffer → Context Lookup → Summary Generation → Campaign History

---

## 5. Design Priorities

### Current Priorities
- fast iteration
- simple structure
- learning by building
- validating workflow assumptions

### Future Priorities
- modularity
- low-friction synchronization
- scalable data relationships
- AI-assisted recordkeeping
- cross-platform usability

---

## 6. Architectural Boundaries

To keep the project maintainable, the system should continue separating:
- **campaign records** from **live session state**
- **user-authored notes** from **AI-generated summaries**
- **core gameplay data** from **visual battlemap state**
- **prototype assumptions** from **future implementation decisions**

---

## 7. Summary

The current architecture is intentionally lightweight and local-first.  
Its purpose is to validate the shape of the application before investing in a more scalable frontend and backend stack.

The future architecture expands that validated core into a synchronized, modular, AI-assisted TTRPG management platform.
