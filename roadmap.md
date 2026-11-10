---
title: Roadmap
description: Web-first development plan for The Master's Loom.
---

# Development Roadmap

> **Planning status — November 2026.** Checkboxes represent intended work, not completed implementation. Older MIT App Inventor and FlutterFlow milestones are retained in the [development log](devlogs/changelog.md), not the active roadmap.

## Phase 0 — Project setup and contracts
- [x] Establish initial application shell and Dashboard, Campaigns, Characters, and Sessions placeholder routes
- [x] Verify local route navigation, production build, and GitHub push
- [ ] Define D&D 2024 V1 acceptance criteria and non-goals
- [ ] Initialize Next.js / React / TypeScript app in a development branch or separate private app repository
- [ ] Establish design tokens, accessible responsive shell, DM and player navigation
- [ ] Set up Supabase development project and migration/version-control workflow
- [ ] Write initial ruleset-module contract (`dnd5e-2024`) and fixture data
- [ ] Create security test plan and separate environment secrets from repository

## Phase 1 — Campaign foundation

- [ ] Add authentication and account profile handling
- [ ] Create rulesets and version tables; seed `dnd5e-2024`
- [ ] Build campaign creation, list, and detail views
- [ ] Build campaign invitation, membership, DM/player role controls
- [ ] Add character creation/editing (D&D fundamentals) and persistent session records
- [ ] Implement and test campaign-scoped RLS policies
- [ ] Test DM + player flows with two independent accounts

## Phase 2 — Live session and combat vertical slice

- [ ] Create session start/stop and live participant indicators
- [ ] Implement authoritative HP and combat-resource transactions
- [ ] Build DM Combat Monitor and Player HUD from shared application state
- [ ] Implement initiative ordering and turn advancement
- [ ] Add append-only `session_events`, operation identifiers, and concurrency controls
- [ ] Deliver real-time notifications with Supabase Realtime
- [ ] Test refresh/reconnect, duplicate requests, role authorization, and simultaneous edits

## Phase 3 — Shared tabletop

- [ ] Implement React Konva map viewer, upload, and responsive controls
- [ ] Add configurable grid and token creation/movement
- [ ] Broadcast throttled movement previews; persist final token locations
- [ ] Enforce token/map visibility server-side and in authorized asset access
- [ ] Test usability on desktop, tablet, and phone

## Phase 4 — Session history and communications

- [ ] Add role-controlled notes and session event timeline
- [ ] Build private whispers and targeted notifications
- [ ] Test private-topic authorization, query access, and message retention
- [ ] Introduce campaign lore and NPC reference panels

## Phase 5 — Chronicle and expanded rulesets

- [ ] Generate Chronicle drafts from structured session events and DM-approved sources
- [ ] Add DM review/edit/approve workflow and source traceability
- [ ] Evaluate transcription, AI cost controls, data retention and consent separately
- [ ] Document a second ruleset integration contract using fixtures (without necessarily shipping another ruleset)
- [ ] Plan any future D&D or other game-system content licensing

## MVP release gate

A DM and a player can securely join the same campaign/session, view role-appropriate data, update combat state across two devices, reconnect without losing truth, and share a simple battlemap. Advanced automation and AI are not required to meet the initial release gate.
