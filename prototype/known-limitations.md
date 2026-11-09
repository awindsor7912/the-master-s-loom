# Known Limitations and Open Risks

> These describe the **planned** web prototype. No live browser application, deployed database, or test results are included in this public documentation repository.

- **Implementation pending:** architecture and acceptance tests are documented; product functionality is not represented as complete.
- **Real-time transport is not authority:** ephemeral realtime notifications require reconciliation with persistent database state after reconnect.
- **Authorization needs verification:** DM-only notes, hidden tokens, private whispers, storage assets, and campaign memberships require policy and negative-access tests.
- **Ruleset scope:** only D&D 2024 is targeted for initial mechanics; a versioned module boundary does not mean other systems are implemented.
- **Rules content:** official D&D text, assets, and compendium data cannot be redistributed without applicable authorization or licenses.
- **Canvas usability:** touch dragging, zoom, accessibility, and performance must be evaluated on actual phones and tablets.
- **Concurrency:** HP edits and initiative turns need atomic, idempotent operations to avoid duplicate or lost changes.
- **Cost and deployment:** Supabase and hosting usage limits, rate controls, and operational costs need measurement before general availability.
- **AI and transcript consent:** Chronicle inputs, retention and review policy remain later design decisions.
