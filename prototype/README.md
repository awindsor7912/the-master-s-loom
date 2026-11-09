---
title: "Prototype Scope"
description: "Initial web prototype scope and acceptance criteria."
---

# Web Prototype — Scope & Acceptance Criteria

> **Status:** planned, not yet implemented in this repository. The MIT App Inventor prototype was an earlier learning direction and is no longer the active target.

## Objective

Prove that The Master's Loom can manage a D&D 2024 campaign **and** operate a live shared tabletop session in a browser, with correct synchronization and role-based privacy. The design should permit other tabletop rulesets later without building those modules yet.

## Initial prototype stack

- Next.js + TypeScript + React for the web application
- Tailwind CSS + shadcn/ui for interface components
- Supabase PostgreSQL, Auth, Realtime, and Storage
- React Konva for a basic map and token layer

## Required user journeys

1. **DM onboarding:** DM signs in, creates a campaign bound to D&D 2024, and invites a player.
2. **Player onboarding:** Player accepts invitation, sees only authorized campaign details, and creates/claims a character.
3. **Session:** DM starts a session and an encounter; both browsers show role-appropriate information.
4. **Combat:** An authorized HP change and initiative advancement persist and appear for connected participants.
5. **Reconnect:** Either browser refreshes/reconnects and recovers current authoritative state from the backend.
6. **Battlemap:** DM uploads a map; visible tokens render on two clients; final coordinates persist after refresh.
7. **Privacy:** Player cannot retrieve DM-only notes, hidden tokens, private data of another campaign, or privileged mutation endpoints.

## Definition of done / tests

| Test | Pass criterion |
|---|---|
| Same-session sync | Two authenticated devices converge on the saved HP/turn values without manual refresh |
| Authoritative update | Invalid or unauthorized mutations are rejected by trusted code/policies |
| Retry safety | Repeating an operation with the same operation ID does not apply damage twice |
| Reconnect | Latest persisted combat and token states restore after refresh/disconnect |
| Role privacy | Negative API/database policy tests prevent player reads of private information |
| Token interaction | Move token on one device; final location appears on another and persists |
| Mobile | Character HUD remains usable on a narrow mobile viewport |

These are acceptance tests, not claims of currently verified behavior.

## Explicitly out of scope

- Complete D&D spell, class, condition, or rules automation
- Other playable TTRPG rulesets (architecture supports future modules)
- AI Chronicle generation, transcription, and automated audio capture
- Built-in video/voice and sophisticated 2D game graphics
- Advanced fog-of-war and professional VTT drawing tools
- Public-scale reliability or guaranteed millisecond latency

## Suggested development layout (not created yet)

```text
src/
  app/                 # routes and UI compositions
  features/
    campaigns/
    characters/
    sessions/
    combat/
    battlemap/
  rulesets/
    core/              # ruleset contract
    dnd5e-2024/        # first implementation
  lib/
    supabase/          # authenticated client/server adapters
    auth/              # campaign-scoped access helpers
supabase/
  migrations/          # versioned SQL and RLS policies
  tests/               # authorization and transaction tests
```

The actual application may live in a separate development repository; this public repository remains a design journal unless that decision changes.
