---
icon: key
---

# CX-VehicleKeys

### Overview

The system allows players to lock and unlock vehicles with full control over animations, effects, security, notifications, and server side ownership checks.

Everything is configurable inside `config.lua`.

***

### Configuration

#### Core Settings

```
Config.Debug = false
```

Enables or disables debug prints in the console.

***

```
Config.Keybind = 'L'
```

Defines the default key used to lock or unlock vehicles.

***

```
Config.LockDistance = 8.0
```

Maximum distance (in meters) to detect and interact with vehicles.

***

### Notifications

```
Config.Notify
```

Handles all in game notifications.

#### Options

* `enabled` → Enables or disables notifications
* `lock` → Message shown when vehicle is locked
* `unlock` → Message shown when vehicle is unlocked
* `noVehicle` → Message when no vehicle is nearby
* `noKey` → Message when player has no access

***

#### Custom Notification Function

```
func = function(msg)    ESX.ShowNotification(msg)end
```

Allows full customization of the notification system.

You can replace ESX notifications with:

* ox\_lib notifications
* okokNotify
* Your System

***

### Locale

```
Config.Locale.vehicleLock
```

Defines the label used for the keymapping text in settings.

***

### Animation

Controls the key fob animation when locking/unlocking vehicles.

* `enabled` → Enable or disable animation
* `dict` → Animation dictionary
* `anim` → Animation name
* `duration` → Animation duration in milliseconds

***

### Horn System

Controls horn feedback when locking/unlocking.

* `enabled` → Enable horn effect
* `duration` → Horn duration
* `mode` → Horn mode type

***

### Light System

Controls vehicle light flashing effects.

* `enabled` → Enable light effects
* `flashes` → Number of flashes
* `onTime` → Time lights stay on
* `offTime` → Time lights stay off

***

### Security System

Handles vehicle protection while locked.

* `enabled` → Enable security system
* `sleep` → Loop delay in milliseconds
* `blockExit` → Prevent exiting locked vehicles
* `engineOff` → Force engine off when locked
* `forceLock` → Force door lock state
* `blockDragOut` → Prevent player being pulled out

***

### Server Settings

Controls backend logic and security validation.

* `requireOwnerCheck` → Only vehicle owners can lock/unlock
* `antispam` → Prevent request spam
* `cooldown` → Time between requests (seconds)
* `debugLogs` → Enable server-side logs

***

### Summary

This system is designed to be:

* Fully configurable
* Framework compatible (ESX ready)
* Lightweight and optimized
* Easy to extend

You can customize every major feature directly from `config.lua` without editing core files.
