# System Architecture & AI Integration

## 📡 Real-Time State Synchronization
To achieve a reactive "Command Center" experience, the system utilizes a **Real-Time Subscription Model**:
* **Push-Sync Logic:** Instead of traditional polling, player clients "push" changes to a central cloud state. 
* **Live Listeners:** Persistent data connections (WebSockets/Firestore) trigger instant updates across all connected clients whenever a character's vital stats or coordinates change.

## 🧠 The Chronicle Engine (AI Pipeline)
The session summarization follows a specialized three-stage logic flow:
1. **Capture:** Raw multimodal data (audio/text) is streamed to a processing buffer.
2. **Contextualization:** The engine cross-references session data against existing **World Lore** and **NPC** tables to ensure narrative consistency.
3. **Synthesis:** A cohesive narrative summary is generated and committed to the campaign’s historical record.

## 🗺️ Dynamic Canvas Logic
Maps are treated as multi-layered objects:
* **Background Layer:** AI-generated or uploaded imagery.
* **Grid Layer:** Mathematically calculated based on user-defined map scales.
* **Actor Layer:** Coordinate-based "Smart Figurines" linked directly to the `Character` data entity.
