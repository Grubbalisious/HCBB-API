# 📊 **HCBB-API Documentation**

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
Roblox will strip out forwardslash (`/`) when exporting assets.

If your image paths already contain a forwardslash (`/`), **double it** wherever you see it to avoid errors.  
For example:

**Correct way**: `Images//BaseOn.png`  
**Wrong way**: `Images/BaseOn.png`

Always add an extra `/` when setting your `BaseOn` and `BaseEmpty` paths!

### Step 2: Load the API

After setting your variables, load the script using the following **loadstring**:

```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/Grubbalisious/HCBB-API/refs/heads/main/MAIN"))()
```

This will automatically set up the trackers and begin saving your data locally.

At the end it should look like: 

```lua
_G.User = "YOUR_USERNAME_HERE"
_G.BaseOn = "PATH/TO/YOUR/BASE/ON/IMAGE"
_G.BaseEmpty = "PATH/TO/YOUR/EMPTY/BASE/IMAGE"

loadstring(game:HttpGet("https://raw.githubusercontent.com/Grubbalisious/HCBB-API/refs/heads/main/MAIN"))()
```
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

## 📂 Overview of TXT Files

The **HCBB-API** system generates **four** main TXT files to track and log real-time game data. These files are regularly updated and stored locally for external usage, such as for overlays, broadcasts, or advanced analysis. The TXT files created are:

1. **`Base1.txt`**, **`Base2.txt`**, **`Base3.txt`**
   - Tracks base runner statuses for 1st, 2nd, and 3rd base.
2. **`CurrentCount.txt`**
   - Tracks the current ball and strike count.
3. **`TotalBalls.txt`** and **`TotalStrikes.txt`**
   - Tracks total balls and strikes throughout the game.
4. **`Pitcher.txt`**, **`PitcherBB.txt`**, **`PitcherERA.txt`**, **`PitcherWHIP.txt`**
   - Tracks pitcher stats, such as Walks, ERA, and WHIP.
5. **`Batter.txt`**, **`BatterHR.txt`**, **`BatterRBI.txt`**, **`BatterOPS.txt`**, **`BatterAVG.txt`**
   - Tracks batter stats like Home Runs, RBIs, OPS, and Batting Average.
6. **`HomeScore.txt`** and **`AwayScore.txt`**
   - Tracks the home and away team scores.

---

## 📂 File Descriptions

Each of these TXT files has its specific purpose and data they track. Here’s what each one does:

### 1. **`Base1.txt`, `Base2.txt`, `Base3.txt`**

- **Purpose**: These files track whether each of the bases (1st, 2nd, and 3rd) is occupied or empty. They also store the image path for visual representation, showing whether a base is occupied or not.
- **Usage**: These files are helpful for tracking base runner statuses during the game. They can be used for game overlays or game analysis.

---

### 2. **`CurrentCount.txt`**

- **Purpose**: This file tracks the **current ball and strike count** in the format `balls-strikes` (e.g., `3-2`).
- **Usage**: This file is useful for broadcasts or overlays, showing the current count of the batter.

---

### 3. **`TotalBalls.txt`** and **`TotalStrikes.txt`**

- **Purpose**: These files track the **total number of balls** and **total number of strikes** throughout the game.
- **Usage**: These files are important for providing a summary of the game's pitch statistics, useful for analysis or broadcasts.

---

### 4. **`Pitcher.txt`, `PitcherBB.txt`, `PitcherERA.txt`, `PitcherWHIP.txt`**

- **Purpose**: These files track **pitcher statistics**:
  - **`Pitcher.txt`**: Stores the name of the pitcher.
  - **`PitcherBB.txt`**: Tracks the number of walks issued by the pitcher.
  - **`PitcherERA.txt`**: Tracks the pitcher's ERA (Earned Run Average).
  - **`PitcherWHIP.txt`**: Tracks the pitcher's WHIP (Walks plus Hits per Inning Pitched).
- **Usage**: These files provide essential pitching data, useful for detailed game analysis, performance tracking, and broadcasts.

---

### 5. **`Batter.txt`, `BatterHR.txt`, `BatterRBI.txt`, `BatterOPS.txt`, `BatterAVG.txt`**

- **Purpose**: These files track **batter statistics**:
  - **`Batter.txt`**: Stores the name of the current batter.
  - **`BatterHR.txt`**: Tracks the number of home runs hit by the batter.
  - **`BatterRBI.txt`**: Tracks the number of RBIs (Runs Batted In) by the batter.
  - **`BatterOPS.txt`**: Tracks the batter's OPS (On-base Plus Slugging).
  - **`BatterAVG.txt`**: Tracks the batter's batting average.
- **Usage**: These files are useful for player performance tracking, game analysis, and overlays in live broadcasts.

---

### 6. **`HomeScore.txt`** and **`AwayScore.txt`**

- **Purpose**: These files track the **home** and **away** team scores during the game.
- **Usage**: These files are useful for displaying the score on overlays or for score tracking during broadcasts.

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
Roblox will strip out forwardslashes (`/`) when exporting assets.

If your image paths already contain a forwardslash (`/`), **double it** wherever you see it to avoid errors.  
For example:

**Correct way**: `Images//BaseOn.png`  
**Wrong way**: `Images/BaseOn.png`

Always add an extra `/` when setting your `BaseOn` and `BaseEmpty` paths!

### Step 2: Load the API

After setting your variables, load the script using the following **loadstring**:

```lua
loadstring(game:HttpGet("http://raw.githubusercontent.com/Grubbalisious/HCBB-API/refs/heads/main/TXT"))()
```

This will automatically set up the trackers and begin saving your data locally.

At the end it should look like:

```lua
_G.User = "YOUR_USERNAME_HERE"
_G.BaseOn = "PATH/TO/YOUR/BASE/ON/IMAGE"
_G.BaseEmpty = "PATH/TO/YOUR/EMPTY/BASE/IMAGE"

loadstring(game:HttpGet("http://raw.githubusercontent.com/Grubbalisious/HCBB-API/refs/heads/main/TXT"))()
```

---

## 📝 **What Will Be Created**

When you use the **HCBB-API**, it will generate and update several `.txt` files in your local folder:

| File Name              | Description                                                      |
| ---------------------- | ---------------------------------------------------------------- |
| **Base1.txt**           | Tracks the status of 1st base (occupied or empty).              |
| **Base2.txt**           | Tracks the status of 2nd base (occupied or empty).              |
| **Base3.txt**           | Tracks the status of 3rd base (occupied or empty).              |
| **CurrentCount.txt**    | Tracks the current ball-strike count for the current batter.    |
| **TotalBalls.txt**      | Tracks the total balls thrown throughout the game.              |
| **TotalStrikes.txt**    | Tracks the total strikes thrown throughout the game.            |
| **Pitcher.txt**         | Stores the name of the current pitcher.                         |
| **PitcherBB.txt**       | Tracks the number of walks issued by the current pitcher.      |
| **PitcherERA.txt**      | Tracks the ERA (Earned Run Average) of the current pitcher.     |
| **PitcherWHIP.txt**     | Tracks the WHIP (Walks plus Hits per Inning Pitched) of the pitcher. |
| **Batter.txt**          | Stores the name of the current batter.                          |
| **BatterHR.txt**        | Tracks the number of home runs by the current batter.           |
| **BatterRBI.txt**       | Tracks the number of RBIs by the current batter.                |
| **BatterOPS.txt**       | Tracks the OPS (On-base Plus Slugging) of the current batter.   |
| **BatterAVG.txt**       | Tracks the batting average of the current batter.               |
| **HomeScore.txt**       | Tracks the score of the home team.                              |
| **AwayScore.txt**       | Tracks the score of the away team.                              |

Each file is updated approximately **once every second**, ensuring near-real-time tracking.

Here’s the documentation for the modified script that integrates with the **HCBB-API** using the global `_G.User` variable:

---

## 📝 **Documentation for Hiding Player GUI Elements**

### 📂 **Purpose**
This script is used to target a player and hide all GUI elements within their `PlayerGui`. It is designed to work with the **HCBB-API**, dynamically using the global `_G.User` variable for the player's username.

### 🛠️ **How the Script Works**
- **Targeting the Player:** The script targets the player based on the username provided in the global `_G.User` variable.
- **Looping through GUI Elements:** It loops through all GUI elements in the player's `PlayerGui`, specifically searching for `ScreenGui` elements.
- **Hiding GUI Elements:** For every child GUI element within a `ScreenGui`, the script sets their `Visible` property to `false`, effectively hiding them from the player.

### 🏗️ **How to Use the Script**

1. **Set the Player’s Username**  
   Before running the script, make sure to set the `_G.User` variable to the username of the player you want to target. You can do this by adding the following line at the beginning of your script:
   
   ```lua
   _G.User = "your_player_username_here"
   ```

   ⚡ **IMPORTANT**: Replace `"your_player_username_here"` with the actual username of the player you want to target.

2. **Integrating the Script**  
   Once the username is set, use the script below to hide the GUI elements of the specified player. This will automatically reference the player based on the `_G.User` value.

   ```lua
   -- Use the global _G.User variable to get the player's username from the HCBB-API settings
   local player = game:GetService("Players")[_G.User]

   -- Check if the player exists
   if player then
       -- Loop through all GUI elements in the player's PlayerGui
       for i, v in pairs(player.PlayerGui:GetChildren()) do
           -- Check if the element is a ScreenGui
           if v:IsA("ScreenGui") then
               -- Loop through all children of the ScreenGui and hide them
               for _, guiElement in pairs(v:GetChildren()) do
                   if guiElement:IsA("GuiObject") then
                       guiElement.Visible = false  -- Hide the GUI element
                   end
               end
           end
       end
   else
       print("Player '" .. _G.User .. "' not found")
   end
   ```

### 🚨 **Important Notes**
- **Setting the Username**: Be sure to set the `_G.User` variable to the correct player's username. This ensures the script targets the correct player and hides their GUI elements.
  
- **Compatibility with HCBB-API**: This script is designed to work seamlessly with the **HCBB-API**. It uses the `_G.User` global variable to retrieve the player's username, making it easy to integrate into your existing HCBB-API setup.

Sure! Here's the updated documentation with that clarification:

---

## 📄 **Documentation for Dynamic Camera Control Script (with HCBB-API Integration)**

### 📝 **Purpose**
This script allows you to control the camera angles and toggle a custom camera mode for a specific player. The player's username is dynamically retrieved using the **HCBB-API** by referencing the global `_G.User` variable, so you do not need to set the player’s username manually.

### 🛠️ **How the Script Works**

1. **Targeting the Player:**
   The script dynamically finds the player using the global `_G.User` variable. If you're using the **HCBB-API**, the player's username will already be set via the API, so there’s no need for you to manually set it.

2. **Setting Camera Views:**
   The script provides different camera views based on key presses:
   - Press `1` to focus on the home plate view.
   - Press `2`, `3`, `4`, `5`, or `6` to switch between different aerial, side, or custom views.
   - Press `z` to toggle a custom scriptable camera mode.

3. **Custom Camera Mode:**
   When toggled on, the camera becomes scriptable, and its position updates according to the selected viewpoint. The camera will continue to focus on the `HomePlate` or any other target you choose.

4. **Real-Time Updates:**
   The camera position is updated in real-time using `RenderStepped`, ensuring smooth transitions as the player switches camera views.

### 🏗️ **How to Use**

1. **Running the Script:**
   Since the **HCBB-API** already handles setting the `_G.User` variable, you do not need to manually specify the player's username.

   To run the script, you can simply load it using **loadstring** to execute it dynamically:

   ```lua
   loadstring(game:HttpGet("https://raw.githubusercontent.com/Grubbalisious/HCBB-API/refs/heads/main/CAMERA"))()
   ```

   This will load and execute the script that allows you to control the camera in real-time for the specified player.

### 🚨 **Important Notes**
- **Player Must Be Online:** The script only works if the player with the username set in `_G.User` is currently in the game.
- **Camera Updates in Real-Time:** The script continuously updates the camera's position using `RenderStepped`, ensuring that the camera follows the selected viewpoint dynamically.

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

Thanks for the correction! Here’s the updated version with the proper terminology:

---

## 🐞 **Reporting Bugs and Getting Support**

If you encounter any issues, bugs, or need support with the **HCBB-API**, **HCBB game**, or **HCBB league**, you can reach out through the following channels:

### 📢 **Bug Reports**
If you find any bugs or issues with the **HCBB-API** or related scripts, please report them in our **Bug Reporting Discord**. You can join the server using the link below:
- [**Bug Reporting Discord**](https://discord.gg/bZayTrQGAJ)

### ⚾ **HCBB Game**
If you're looking to play the **HCBB 9v9 2.0** game, which integrates features from the API, you can join and play the game on Roblox by visiting the following link:
- [**Play HCBB Game**](https://www.roblox.com/games/7830150255/HCBB-9v9-2-0)

### ⚾ **HCBB League**
To learn more about the **HCBB League**, its teams, and gameplay mechanics, or if you're interested in joining the league, you can check out the official **HCBB League Discord**:
- [**HCBB League Discord**](https://discord.gg/J3tprJY6aQ)

---

Feel free to report any issues, stay updated on new features, or simply join the community to connect with other players and developers!


