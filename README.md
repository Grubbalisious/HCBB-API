# 📊 **HCBB-API CSV Documentation**

---

## 📂 Overview of CSV Files

The **HCBB-API** system generates **three** main CSV files to track and log real-time game data. These files are regularly updated and stored locally for external usage, such as for overlays, broadcasts, or advanced analysis. The CSV files created are:

1. **`HCBB-API-Stats.csv`**  
   - Tracks live player stats (batters & pitchers).
2. **`HCBB-API-Bases.csv`**  
   - Tracks base runner statuses (1st, 2nd, and 3rd base).
3. **`HCBB-API-Counts.csv`**  
   - Tracks ball and strike counts during the game.

---

## 📂 File Descriptions

Each of these CSV files has its specific purpose and data they track. Here’s what each one does:

### 1. **`HCBB-API-Stats.csv`**

- **Purpose**: This file tracks and records **live player statistics**. It includes both **batting** and **pitching** stats, such as a player's power, contact, speed, and stamina. For pitchers, it also tracks the number of pitches thrown during the game.
- **Usage**: This file is essential for monitoring individual player performance and can be used for game analysis, statistical overlays, or player performance tracking in live broadcasts.

---

### 2. **`HCBB-API-Bases.csv`**

- **Purpose**: This file records the status of the bases during the game. It tracks whether a base is occupied or empty and how long it has been occupied. It also includes the file path for visual representation images (e.g., images showing whether a base is occupied or not).
- **Usage**: This file is useful for tracking base runner statuses in real-time. The data can be used for game overlays, to display base occupancy during broadcasts, or for game analysis.

---

### 3. **`HCBB-API-Counts.csv`**

- **Purpose**: This file tracks the **ball and strike counts** for the current batter, along with cumulative totals for balls and strikes throughout the game. It keeps track of the current count (balls-strikes) and the total number of balls and strikes thrown by the pitcher.
- **Usage**: This file is valuable for analyzing the game's progression, keeping track of pitch counts, and providing up-to-date ball/strike information for use in broadcasts or overlays.

---

## 🛠️ **How to Use the HCBB-API**

### Step 1: Set Your Variables

Before loading the API, you’ll need to configure some global variables. This is done by setting these variables before calling the main script:

```lua
_G.User = "YOUR_USERNAME_HERE"
_G.BaseOn = "PATH/TO/YOUR/BASE/ON/IMAGE"
_G.BaseEmpty = "PATH/TO/YOUR/EMPTY/BASE/IMAGE"
```

⚡ **IMPORTANT**:  
Roblox will strip out backslashes (`\`) when exporting assets.

If your image paths already contain a backslash (`\`), **double it** wherever you see it to avoid errors.  
For example:

**Correct way**: `Images\\BaseOn.png`  
**Wrong way**: `Images\BaseOn.png`

Always add an extra `\` when setting your `BaseOn` and `BaseEmpty` paths!

### Step 2: Load the API

After setting your variables, load the script using the following **loadstring**:

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/Grubbalisious/HCBB-API/refs/heads/main/MAIN"))()
```

This will automatically set up the trackers and begin saving your data locally.

---

## 📝 **What Will Be Created**

When you use the **HCBB-API**, it will generate and update several `.csv` files in your local folder:

| File Name                | Description                                                      |
| ------------------------ | ---------------------------------------------------------------- |
| **HCBB-API-Bases.csv**    | Tracks base runner statuses (1st, 2nd, 3rd base).               |
| **HCBB-API-Counts.csv**   | Tracks balls, strikes, total balls, and total strikes.          |
| **HCBB-API-Stats.csv**    | Includes live batter and pitcher stats (power, contact, speed, stamina, etc.). |

Each file is updated approximately **once every second**, ensuring near-real-time tracking.

---

## 🛠️ **Known Issues**

While the HCBB-API is fully operational, there are a few bugs being addressed:

- **Pitcher and batter stats** might not always pull correctly after substitutions or player swaps.
- In some cases, **relief pitchers** or **pinch hitters** can cause stat overlaps.
- GUI elements might fail to load instantly at game start, especially if the player loads in late. The system will attempt to **re-check and recover** when this happens.

🛠️ **Fixes for these issues are in development.**  
The goal is to automatically detect swaps better and prevent wrong stats from displaying in future versions.

---

## 📢 **Why This Project Exists**

HCBB 9v9 is one of the most competitive and detailed baseball games on Roblox, but it has historically lacked advanced tools for **stat tracking**, **broadcasting**, or **live overlays**.

The **HCBB-API** was created to help change that — to build a bigger, more connected community around HCBB gameplay. We believe HCBB deserves **more awareness** and recognition!

As more tools like this become available, players will have even more reasons to dive deeper into **leagues**, **tournaments**, and the **competitive side** of the game.

This project is just getting started, and **more updates, features, and improvements** are coming soon!

Stay tuned for better pitcher/batter support, automatic player detection, improved base handling, and full game archiving features.

---

Let me know if you need further modifications or additional info!
