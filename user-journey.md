---
title: User Journey: A Night at The Master's Loom
description: Proposed D&D-first, web-based DM and player experience.
---

# User Journey — A Live D&D Session

> **Illustrative workflow, not a claim of implemented behavior.** The first playable experience targets D&D Fifth Edition (2024 revision); later rulesets should use the same campaign/session infrastructure with their own mechanics modules.

## 1. Before the game: set up the campaign

**DM:** Signs into the browser application, creates a campaign using the `dnd5e-2024` ruleset version, invites players, and creates an upcoming session. DM can view campaign notes and characters.

**Player:** Opens the invitation in a desktop or mobile browser, joins the campaign, and creates or claims a character. Their dashboard shows permitted campaign information and their character's D&D resources. Other campaigns and DM-only details remain inaccessible.

**V1 implementation:** authentication, membership, campaign, characters, and persisted sessions. Automated encounter suggestions are deferred.

## 2. Starting play: shared state

**DM:** Launches the session and opens the Combat Monitor, where authorized character and encounter information is displayed.

**Player:** Opens their Player HUD on a phone or second browser window. A presence indicator shows connected participants, and the player sees only permitted information.

**Live example:** DM applies 15 points of damage to a participating character. A trusted server operation validates the user's role, updates persistent HP, and appends a structured event. Other connected clients receive an update and reconcile against authoritative state. If the player's browser disconnects, the current HP is recovered after reconnection.

**V1 implementation:** HP/initiative transactions, shared live updates, session event history, and reconnect recovery. Full rules adjudication remains the DM's responsibility.

## 3. Shared battlemap

**DM:** Uploads a map image, configures a basic grid, and places tokens for the active encounter.

**Player:** Views the authorized map and tokens. During a permitted movement, the canvas can show ephemeral movement updates; the final token position is validated and saved. Hidden or DM-only tokens must not be sent to unauthorized clients.

**V1 implementation:** basic map, grid, token movement, and final coordinate persistence. Advanced fog of war is later work.

## 4. Private communication (later milestone)

**DM:** Sends a private whisper containing a story clue to one player.

**Player:** Receives the private message without it becoming visible to the rest of the party. Backend authorization must protect the message contents and notification channel, not merely hide them in UI.

## 5. After the session: history and chronicle (later milestone)

**DM:** Closes the session. The saved timeline and notes provide a structured record of what happened.

**Chronicle Engine (later):** Produces a draft recap from authorized session events and DM-approved notes or transcripts. The DM reviews and edits the draft before it appears in the campaign's published history. AI-created content is distinct from source records.

## Guiding UX principles

- Make the phone HUD immediately legible during live play.
- Avoid requiring a desktop browser for basic player actions.
- Minimize context switching between combat, map, and communications.
- Make synchronization and pending/failed changes obvious.
- Preserve DM discretion rather than forcing full automation of D&D mechanics.
