# Data Schema & Relationships

## Core Tables

### 1 Campaigns
* **CampaignID (Primary Key)**
* **DM_UserID**
* **Ruleset_Type** (e.g., D&D 5e, Pathfinder)
* **World_Lore_Blob** (Stored as Markdown)

### 2 Characters
* **CharacterID (Primary Key)**
* **CampaignID (Foreign Key)**
* **Player_UserID**
* **Current_HP / Max_HP**
* **Armor_Class**
* **Stat_Block** (JSON Object)

### 3 Sessions
* **SessionID (Primary Key)**
* **CampaignID (Foreign Key)**
* **Session_Date**
* **Raw_Transcript**
* **AI_Summary**
* **Active_Map_URL**

### 4 Communications (Whispers)
* **MessageID (Primary Key)**
* **SessionID (Foreign Key)**
* **SenderID / ReceiverID**
* **Message_Content**
