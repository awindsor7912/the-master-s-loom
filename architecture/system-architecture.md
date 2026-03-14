# System Architecture & Data Logic

## 📡 Real-Time State Synchronization
To achieve the "Command Center" feel, The Master's Loom utilizes a **Real-Time Subscription Model**. 

* **The Logic:** Instead of the DM "polling" for updates, the Player's client "pushes" changes to a central cloud state. Any change to a Character's health or position triggers an instant update to the DM's view via a persistent data connection (WebSockets or Real-time DB listeners).

## 🧠 AI Integration Pipeline
The "Chronicle Engine" follows a three-stage logic flow:
1. **Capture:** Raw audio or text notes are streamed to a processing buffer.
2. **Contextualization:** The AI compares the session data against the existing **World Lore** and **NPC** tables to ensure accuracy.
3. **Synthesis:** A narrative summary is generated and committed to the **Session History** table.

---

## 📊 Core Data Schema (Conceptual)

| Entity | Primary Keys & Relationships | Key Attributes |
| :--- | :--- | :--- |
| **Campaign** | `Campaign_ID` (PK) | Ruleset, World Lore, Active DM |
| **Participant** | `User_ID` (PK), `Campaign_ID` (FK) | Role (DM/Player), Permissions |
| **Character** | `Char_ID` (PK), `User_ID` (FK) | Current_HP, AC, Stat_Block (JSON), Inventory |
| **Session** | `Sess_ID` (PK), `Campaign_ID` (FK) | Date, Transcript, AI_Summary, Active_Map |
| **Interaction** | `Msg_ID` (PK), `Sess_ID` (FK) | Sender_ID, Receiver_ID, Content, Timestamp |

---

## 🗺️ Interactive Map Logic
Maps are treated as "Dynamic Canvas" objects. 
* **Layer 1:** The Background (AI-generated or uploaded JPG).
* **Layer 2:** The Grid (Calculated based on map scale).
* **Layer 3:** The Figurines (Coordinate-based icons linked to the `Character` table).
