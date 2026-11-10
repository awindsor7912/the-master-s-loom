---
title: Home
description: The Master's Loom project overview, proposed architecture, development milestones, and tabletop RPG product direction.
---

<section class="home-intro">
  <p class="section-label">PROJECT OVERVIEW · NOVEMBER 2026</p>
  <h1>A shared command center for tabletop campaigns.</h1>
  <p class="lead">The Master's Loom is a planned web-first platform for Dungeon Masters and players to organize campaigns, run synchronized sessions, and interact on a shared battlemap.</p>
  <p><strong>Starting point:</strong> Dungeons &amp; Dragons Fifth Edition (2024 revision). <strong>Long-term direction:</strong> support additional tabletop rulesets through versioned, modular integrations.</p>
  <p class="status-note"><strong>Current status:</strong> The initial Next.js frontend shell has been implemented and pushed to <a href="https://github.com/awindsor7912/masters-loom-app">the application repository</a>. Dashboard, Campaigns, Characters, and Sessions routes are available as early workspace screens. Authentication, persisted campaign data, multiplayer synchronization, and maps are planned, not implemented.</p>`
  <div class="action-row">
    <a class="action-link primary" href="{{ '/roadmap.html' | relative_url }}">View roadmap</a>
    <a class="action-link" href="{{ '/prototype/README.html' | relative_url }}">Prototype acceptance criteria</a>
  </div>
</section>

<h2>What the platform is designed to do</h2>
<div class="feature-grid">
  <section class="feature-card"><h3>DM Command Center</h3><p>Manage campaigns, notes, character access, encounters, and authoritative session controls from one workspace.</p></section>
  <section class="feature-card"><h3>Player HUD</h3><p>Show character resources, initiative, condition updates, and permitted session details on phones or desktop browsers.</p></section>
  <section class="feature-card"><h3>Live Combat Monitor</h3><p>Synchronize hit points, initiative, turns, and conditions across authenticated participants with persisted state.</p></section>
  <section class="feature-card"><h3>Shared Battlemap</h3><p>Render uploaded maps, grids, and movable tokens. Preserve final positions and enforce visibility permissions.</p></section>
  <section class="feature-card"><h3>Session History</h3><p>Record significant game events for reconnect recovery, auditability, and later session summaries.</p></section>
  <section class="feature-card"><h3>Ruleset Extensibility</h3><p>Keep campaign and multiplayer infrastructure independent from D&amp;D-specific calculations and character schemas.</p></section>
</div>

<h2>Selected technical direction</h2>
<p>The prototype will test a modular, browser-based architecture rather than relying on a game engine or native app builder.</p>

| Layer | Preferred technology | Planned responsibility |
|:---|:---|:---|
| Web application | Next.js / React / TypeScript | Responsive DM and player interfaces |
| UI components | Tailwind CSS / shadcn/ui | Accessible, reusable interface elements |
| Data and identity | Supabase PostgreSQL / Auth | Campaign records, roles, and account security |
| Live transport | Supabase Realtime | Notifications, presence, and state-change signals |
| Battlemap | React Konva | Interactive 2D maps, grids, and tokens |
| File storage | Supabase Storage | Map images and authorized assets |

<p class="small-note">Authoritative actions will be validated in trusted backend/database operations. Live messages alone are not treated as the source of truth. See <a href="{{ '/architecture/system-architecture.html' | relative_url }}">System Architecture</a> and <a href="{{ '/evaluations/tech-evaluations.html' | relative_url }}">Technology Decisions</a>.</p>

<h2>First prototype: release criteria</h2>
<p>The initial working slice must allow a DM to create a campaign, invite a player, start a session, update HP and initiative, and synchronize the resulting state between two authenticated browsers. Refreshing or reconnecting must restore persisted state. A simple shared map with durable token positions follows, with role-based access enforced throughout.</p>

<div class="milestone-strip">
  <div><span class="milestone-number">01</span><strong>Campaign foundation</strong><span>Accounts, roles, characters</span></div>
  <div><span class="milestone-number">02</span><strong>Live combat</strong><span>State sync, history, recovery</span></div>
  <div><span class="milestone-number">03</span><strong>Shared tabletop</strong><span>Map, grid, tokens</span></div>
</div>

<h2>Documentation</h2>
<ul class="doc-links">
  <li><a href="{{ '/roadmap.html' | relative_url }}">Development roadmap</a> — implementation phases and milestones</li>
  <li><a href="{{ '/user-journey.html' | relative_url }}">User journey</a> — a proposed live D&amp;D session</li>
  <li><a href="{{ '/architecture/system-architecture.html' | relative_url }}">System architecture</a> — modules, data flow, and authorization boundaries</li>
  <li><a href="{{ '/data/data-schema.html' | relative_url }}">Data schema</a> — persistent records and ruleset boundaries</li>
  <li><a href="{{ '/prototype/README.html' | relative_url }}">Prototype scope</a> — testable acceptance criteria</li>
  <li><a href="{{ '/evaluations/tech-evaluations.html' | relative_url }}">Technology evaluation</a> — platform tradeoffs and rationale</li>
  <li><a href="{{ '/devlogs/changelog.html' | relative_url }}">Development changelog</a> — project history and superseded approaches</li>
  <li><a href="{{ '/devlogs/2026-11-09-nextjs-foundation.html' | relative_url }}">Next.js foundation milestone</a> — implementation and troubleshooting notes</li>
  <li><a href="{{ '/learninglog/11-09-2026.html' | relative_url }}">Learning log: November 9</a> — Next.js routing, GitHub workflow, and VS Code troubleshooting</li>
</ul>

<p class="small-note">This site is an architectural portfolio and design journal. D&amp;D is a trademark of Wizards of the Coast; the project is not affiliated with or endorsed by Wizards of the Coast. Third-party game content is subject to its applicable license.</p>
