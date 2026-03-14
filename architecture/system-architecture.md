# System Architecture

## Real-Time Data Flow
The Master's Loom relies on a "Push-Sync" architecture to ensure zero-latency updates during live combat.

1. **User Action:** A Player updates their current HP on their mobile Power App.
2. **Data Trigger:** The change is committed to the **Dataverse Character Table**.
3. **DM Update:** The DM’s Dashboard utilizes a "Refresh-on-Change" property, instantly reflecting the new HP value without a manual page reload.

## AI Integration Layer
* **Transcription:** Audio is captured via the Power Apps microphone control and sent to an AI logic flow for text conversion.
* **Summarization:** At session close, the "Chronicle Engine" parses the transcript and DM notes to generate a narrative summary stored in the **Session History** table.
* **Vision:** AI prompts generate tactical maps based on DM descriptions (e.g., "A damp cavern with a glowing pool in the center").
