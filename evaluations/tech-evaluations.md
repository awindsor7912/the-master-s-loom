# Technology Evaluation & Decision Record

## Decision — November 9, 2026

**Adopt a web-first prototype direction.** Preferred stack: **Next.js + React + TypeScript + Supabase (PostgreSQL, Auth, Realtime, Storage)**, with **React Konva** when implementing the shared battlemap. Tailwind CSS and shadcn/ui are proposed for the interface. This is the selected development direction, not a statement that implementation is complete.

### Why the decision changed

The product's central requirement is a persistent, role-aware, multiuser campaign workspace with real-time D&D session capabilities. It does not need game-engine physics, advanced 2D graphics, or a native-only client. Browser deployment and relational campaign data make a web stack the more direct fit.

### Decision criteria

1. **Real-time correctness:** authoritative updates, concurrent participants, offline/reconnect recovery, controlled visibility.
2. **Relational data and security:** campaign membership, characters, sessions, events, and database-enforced access restrictions.
3. **Practical web delivery:** desktop DM console, phone-friendly player HUD, no required client installation.
4. **Extensibility:** multiple ruleset versions, third-party APIs, and eventual AI services.
5. **Learning and maintainability:** transferable TypeScript, SQL, component-based UI, version-controlled schema.
6. **Cost and licensing:** low-cost development with measured production limits; avoid unnecessary platform lock-in.

An unconditional `<100ms` synchronization guarantee is **not** a valid selection criterion: latency depends on geography, networks, client load, and service conditions. Set measurable targets after prototype tests.

## Compared alternatives

| Option | Strength | Primary tradeoff | Outcome |
|---|---|---|---|
| Next.js + Supabase | Strong relational model, authentication, real-time and familiar SQL | Must build sync/auth boundaries carefully | **Preferred** |
| React/Next.js + Convex | Reactive queries and simpler live data flow | Different persistence/query model from PostgreSQL | Backup candidate |
| SvelteKit + Supabase | Lean frontend development | Smaller ecosystem for particular collaborative canvas integrations | Viable alternative |
| React + Firebase | Mature realtime and deployment ecosystem | Firestore's document design and usage-based billing need deliberate modeling | Not selected |
| React + Liveblocks | Powerful shared-state collaboration | Additional service; does not replace core campaign persistence | Optional later integration |
| Godot 4 | Excellent interactive visuals and scenes | More effort for document-heavy web app; browser/mobile constraints | Not primary platform |
| Foundry VTT module | Existing VTT features available immediately | Product tied to a third-party host and system constraints | Research reference, not independent app foundation |
| FlutterFlow + Firebase/Supabase | Rapid low-code UI prototyping | Less control over custom canvas and complete web app architecture | Superseded |
| MIT App Inventor | Very accessible learning experiments | No longer matches primary web-first, multiplayer target | Historical experiment |

### Battlemap rendering

Use **React Konva** for uploaded map backgrounds, a grid, draggable tokens, and simple overlays. Application services—not the canvas—own the authoritative positions and permissions. Consider tldraw or Excalidraw only if collaborative freeform drawing becomes a major requirement, taking account of licenses and integration complexity.

### Backend boundary

Supabase Realtime is for **presence, notifications, and transport**; trusted database transactions are authoritative for HP, turns, token final positions, and private messages. RLS, token/asset access controls, and secure server-side operations are mandatory for anything intended to be private.

## Prior decisions (historical)

- **March 2026:** FlutterFlow/Firebase UI and sync concepts explored; see [development log](../devlogs/changelog.md).
- **Later prototype exploration:** MIT App Inventor/local storage explored as an inexpensive learning route; not the current plan.
- **November 2026:** web-first, D&D-first / ruleset-extensible design chosen. Full platform rebuilding from the earlier experiment is no longer an explicit planned phase.

## Validation gates before production commitment

- Two authenticated browsers can observe correct, persisted live combat changes.
- RLS tests demonstrate no access to another campaign or DM-private material.
- Refresh/reconnect reconstructs an authoritative current view.
- Token movement works on desktop and a representative phone, without flooding database writes.
- Baseline operating cost and responsiveness can be measured with real sessions.

**Next decision checkpoint:** review results of these tests; reassess Supabase/Convex only if observed limitations justify a switch.
