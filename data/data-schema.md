# Data Schema & Relationships

> Note: This schema is split between the current prototype model and the future-state model.  
> The prototype schema is intentionally simplified for MIT App Inventor development.  
> Future versions may normalize these entities further when rebuilt on a cloud backend.

---

## 1. Schema Overview

The initial schema is centered around three core entities:

- **Campaigns** – top-level containers for a game world or play group
- **Characters** – player or game-controlled entities associated with a campaign
- **Sessions** – records of individual play sessions associated with a campaign

These three entities define the minimum viable structure needed to validate the app’s workflow.

---

## 2. Prototype V1 Tables

## Campaigns

**Purpose:** Stores the top-level campaign record.

| Field | Type | Description |
|---|---|---|
| CampaignID | String | Unique identifier for the campaign |
| CampaignName | String | Name of the campaign |
| DMName | String | Name of the Dungeon Master or primary organizer |
| RulesetType | String | Ruleset or system used by the campaign |
| WorldNotes | Text | General notes about the world, setting, or campaign context |

### Relationships
- One campaign can have many characters
- One campaign can have many sessions

---

## Characters

**Purpose:** Stores character records associated with a campaign.

| Field | Type | Description |
|---|---|---|
| CharacterID | String | Unique identifier for the character |
| CampaignID | String | Foreign key linking the character to a campaign |
| CharacterName | String | Character name |
| PlayerName | String | Name of the player controlling the character |
| HP | Number | Current hit points |
| MaxHP | Number | Maximum hit points |
| ArmorClass | Number | Character armor class |
| Notes | Text | Freeform notes about the character |

### Relationships
- Many characters belong to one campaign

### Prototype Notes
For the prototype, this table may include both player characters and other tracked actors if that simplifies development.

---

## Sessions

**Purpose:** Stores session-level records tied to a campaign.

| Field | Type | Description |
|---|---|---|
| SessionID | String | Unique identifier for the session |
| CampaignID | String | Foreign key linking the session to a campaign |
| SessionDate | Date/String | Date of the play session |
| SessionNotes | Text | Raw notes captured during or after the session |
| Summary | Text | Condensed recap of the session |

### Relationships
- Many sessions belong to one campaign

### Prototype Notes
In the early prototype, `Summary` may be manually written. In future phases it may also store AI-assisted outputs.

---

## 3. Prototype Relationship Model

### Campaign → Characters
One-to-many

A single campaign contains multiple characters.

### Campaign → Sessions
One-to-many

A single campaign contains multiple sessions.

### Character ↔ Sessions
Not directly linked in Prototype V1.

For simplicity, character activity is inferred through notes rather than a dedicated join table.

---

## 4. Future-State Tables

These entities are not required for the first MIT App Inventor build, but they represent likely expansion points.

## Communications

**Purpose:** Stores private or targeted messages, notifications, or whisper-style communication.

Possible fields:
- CommunicationID
- CampaignID
- SessionID
- SenderActorID
- RecipientActorID
- MessageBody
- MessageType
- Timestamp

---

## BattlemapActors

**Purpose:** Stores positional and tactical state for characters, NPCs, enemies, or tokens shown on a battlemap.

Possible fields:
- ActorID
- CampaignID
- SessionID
- LinkedCharacterID
- ActorType
- PosX
- PosY
- HP
- StatusEffects
- VisibilityState

---

## AIChroniclePipeline

**Purpose:** Stores processing records for AI-assisted summarization and campaign history generation.

Possible fields:
- ChronicleID
- CampaignID
- SessionID
- SourceType
- RawInput
- ContextReferences
- GeneratedSummary
- ReviewStatus
- CreatedAt

---

## 5. Future Normalization Opportunities

As the project matures, the schema may split into more specialized entities such as:
- NPCs
- inventory items
- world locations
- quests
- encounters
- conditions/status effects
- users/auth identities
- session event logs

This should only happen after the core workflow is validated.

---

## 6. Design Principles

This schema is being developed around a few practical principles:
- keep prototype entities simple
- prefer clear relationships over premature complexity
- separate campaign history from live tactical state
- allow future migration from local storage to cloud-backed structured tables

---

## 7. Summary

Prototype V1 uses a deliberately small schema built around campaigns, characters, and sessions.

That structure is enough to validate the app’s core workflow now, while leaving room for future expansion into communications, battlemap state, and AI-assisted chronicle features.
