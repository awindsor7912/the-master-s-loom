![The Master's Loom Banner](loom-banner.png)

# The Master's Loom

**A web-first, real-time tabletop roleplaying campaign and live-session platform.** Initial ruleset: **Dungeons & Dragons Fifth Edition (2024 revision)**. The underlying platform is intended to accommodate other tabletop systems through versioned ruleset modules.

> **Status — architecture and prototype planning (November 2026).** The web-first direction and proposed technology stack have been selected for the next prototype. This public repository documents design decisions and requirements; it does **not** yet contain a deployed web application or working real-time multiplayer implementation.

## What is The Master's Loom?

The Master's Loom is a campaign workspace and shared tabletop environment for Dungeon Masters (DMs) and players. It combines campaign organization, role-aware views, a synchronized combat monitor, an interactive battlemap, and a durable session history into one browser-accessible application.

The design goal is a single authoritative campaign record with the right information surfaced to each participant during play, whether they are on a desktop, tablet, or phone.

## Product direction

- **Web-first:** responsive browser experience rather than a native-first or game-engine-dependent application.
- **Live tabletop:** synchronized character/encounter state, initiative, maps, tokens, and presence are foundational capabilities, not optional late-stage extras.
- **Role-aware:** DM-only notes and controls remain separate from player-accessible information; permissions are enforced on the server/database, not simply by hiding UI.
- **System-flexible:** campaign, accounts, session history, communications, and map infrastructure stay independent of any one ruleset. D&D 2024 is the first implementation.
- **Deliberate automation:** the DM retains control over adjudication; AI-assisted session chronicles remain a later, reviewable enhancement.

## Proposed technology stack

| Layer | Preferred technology | Purpose |
|---|---|---|
| Application | Next.js, React, TypeScript | Pages, reusable UI, server-side application functions |
| UI | Tailwind CSS + shadcn/ui | Responsive dashboards and accessible controls |
| Campaign data | Supabase PostgreSQL | Relational campaign, character, session, and event records |
| Identity/authorization | Supabase Auth + PostgreSQL RLS | Accounts and campaign-scoped access controls |
| Real-time | Supabase Realtime | Live notifications, presence, and session updates |
| Shared battlemap | React Konva | 2D map image, grid, token interaction, overlays |
| Assets | Supabase Storage | Uploaded maps and other permitted campaign assets |
| AI (later) | Server-side provider integration | Chronicle drafting from DM-approved source material |
| Deployment (to validate) | Vercel or equivalent Node.js hosting | Browser delivery |

These are **architecture decisions for development**, not claims that the services have been implemented or deployed. Alternatives and rationale are recorded in [Technical Evaluations](evaluations/tech-evaluations.md).

## First working prototype: definition of done

A DM can create a campaign, invite a player, assign a character, start a session, adjust HP and initiative, and see those changes reflected on another connected device. Both clients can reconnect and recover the persisted authoritative state. DM-private data remains inaccessible to players. A simple shared map with movable tokens is the next milestone.

**Initial scope**
1. Sign-in, campaign creation, membership, roles, and persistent data.
2. D&D 2024 character fundamentals: name, ability scores, class/level, HP, AC, and limited resource tracking.
3. Active session, combat monitor, initiative, conditions, and a player-focused HUD.
4. A basic shared battlemap with uploaded image, grid, tokens, and persisted token positions.
5. An append-only session event history with reconnect and permission tests.

**Deferred:** full D&D rules automation, cross-system rule engines, sophisticated fog of war, built-in voice/video, automated map generation, transcription, and AI Chronicle publication. See the [Roadmap](roadmap.md) for the delivery sequence.

## Capability goals

| Capability | Design objective |
|---|---|
| DM Command Center | See campaign context, participants, encounter state, and controls in one place |
| Player HUD | Display authorized character resources, combat state, and notifications |
| Combat Monitor | Server-validated HP, conditions, initiative, and turn transitions |
| Interactive Battlemap | Shared maps and tokens with durable final positions and ephemeral movement updates |
| Whisper Network | Authorized private messaging and notifications (planned after core live session) |
| Chronicle Engine | AI-assisted recaps built from captured events and approved materials, reviewed by the DM (later) |
| Multiple rulesets | Versioned ruleset contracts; D&D 2024 implemented first |

## Architecture principles

- Separate **authoritative persistent state** (HP, turns, messages, final token coordinates) from **ephemeral live events** (drag previews, cursor activity, presence).
- Validate all sensitive operations using trusted backend code and/or PostgreSQL policies; never trust a client-declared DM role.
- Organize features around campaign membership and ruleset versions. Keep the shared application core independent of D&D-specific mechanics.
- Record significant game-state transitions as events for history, conflict resolution, and eventual Chronicle inputs.
- Measure real-time performance in actual test conditions instead of assuming a universal latency threshold.
- Prefer a modular monolith and straightforward infrastructure until requirements justify additional services.

## Development status and history

Earlier exploration included FlutterFlow/Firebase and MIT App Inventor. Those experiments remain part of the learning log but are **superseded as the forward development path**. The next implementation is a web-based prototype; no production build is represented here.

## Documentation

- [Development Roadmap](roadmap.md)
- [System Architecture](architecture/system-architecture.md)
- [Schema and Ruleset Boundaries](data/data-schema.md)
- [User Journey](user-journey.md)
- [Technical Evaluations and Decision Record](evaluations/tech-evaluations.md)
- [Prototype Scope and Acceptance Tests](prototype/README.md)
- [Known Limitations](prototype/known-limitations.md)
- [Development Log](devlogs/changelog.md)
- [Learning Log](learninglog/)

## Intellectual property and scope

**Copyright © 2026 Ashley Windsor. All rights reserved.** This repository is a public design journal and architectural portfolio. No software license is granted for the author's original project material unless a license is explicitly added. Third-party tools and dependencies retain their own licenses.

**D&D content:** The project is not affiliated with or endorsed by Wizards of the Coast. Any official rules text, imagery, trademarks, and game data must be used under applicable licenses/permissions. Initial implementation can track user-entered stats without redistributing proprietary rulebooks or comprehensive content catalogs.
