---
icon: presentation-screen
---

# CX-DiscordRPC

## CX-Modding — Discord Rich Presence Script

### Requirements

This script requires a working FiveM framework setup.

Supported frameworks:

* ESX Legacy
* QBCore (optional support depending on config)
* Standalone mode (no framework required)

***

### 1. General Settings

#### Config.EnableESX

Enables ESX framework support.

#### Config.EnableQBCore

Enables QBCore framework support.

#### Config.EnableStandalone

Runs the script without any framework dependency.

#### Config.ForceFramework

Forces a specific framework instead of auto-detection:

* `auto` → automatic detection
* `esx` → force ESX
* `qbcore` → force QBCore
* `standalone` → no framework

#### Config.JobRefreshInterval

Defines how often player job data is refreshed (in seconds).

***

### 2. Discord Setup

#### Config.AppId

Your Discord Application ID used for Rich Presence integration.

This is required for the script to work.

***

### 3. Server Configuration

#### Config.ServerName

The name of your server displayed in Discord.

#### Config.UseServerPlayerCount

If enabled, the script uses synced server player count instead of local values.

#### Config.ServerBroadcastInterval

Defines how often the server broadcasts player count updates (in seconds).

***

### 4. Presence System (Main Display)

#### Config.PresenceFormat

This is the main Discord status format.

You can use placeholders:

* `{job}` → Player job
* `{name}` → Player name
* `{players}` → Current online players
* `{maxplayers}` → Maximum server slots
* `{vehicle}` → Current vehicle (if enabled)
* `{status}` → Custom status
* `{id}` → Server ID

Example:

```lua
'{job} | {name} | {players}/{maxplayers} online'
```

***

#### Config.FallbackPresenceFormat

Used if the main format cannot be applied or fails.

***

### 5. Job System

#### Config.JobDisplayNames

Used to rename jobs shown in Discord.

Example:

```lua
['unemployed'] = 'Unemployed'
```

***

#### Config.JobCustomTexts

Custom Rich Presence text per job.

Supports placeholders like:

* `{players}`
* `{id}`
* `{job}`
* `{name}`

Example:

```lua
['unemployed'] = 'Unemployed | {players} Online | ID: {id}'
```

***

### 6. Images & Visuals

#### Large Image

* `Config.LargeImage` → Main Discord asset image key
* `Config.LargeImageText` → Hover text

#### Small Image

* `Config.SmallImage` → Small Discord asset image key
* `Config.SmallImageText` → Hover text

***

#### Dynamic Small Images by Job

You can assign different small images depending on the player job.

Example:

```lua
['unemployed'] = {
    key = 'job_unemployed_small',
    text = 'Unemployed'
}
```

***

### 7. Buttons

#### Config.Buttons

Adds clickable buttons to Discord Rich Presence.

Example:

```lua
{
    label = 'Discord',
    url = 'https://discord.gg/yourserver'
}
```

You can add multiple buttons if needed.

***

### 8. Update System

#### Config.UpdateInterval

Defines how often Rich Presence updates (in seconds).

#### Config.MinUpdateInterval

Minimum allowed update interval to prevent spam updates.

***

### 9. Display Options

#### Config.ShowVehicle

Shows the player’s current vehicle in Rich Presence.

#### Config.ShowJobGrade

Displays the player’s job grade/rank.

#### Config.ShowPlayerName

Shows the player’s name in Discord.

***

### 10. Debug System

#### Config.Debug

Enables debug mode for development and troubleshooting.

When enabled, the script prints detailed logs in the console.

***

### 11. Permissions

#### Config.AdminGroup

Defines the admin group name used for permission checks.

***

### Summary

This script allows full customization of Discord Rich Presence including:

* Job display system
* Dynamic player information
* Server syncing
* Custom images and buttons
* Framework support (ESX / QBCore / Standalone)

It is designed to be lightweight, flexible, and fully configurable without editing core logic.
