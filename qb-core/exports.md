---
description: Learn how to use QBCore exports!
---

# ↗ QBCore Exports

## Shared

### GetCoreObject

Retrives the `QBCore` framework object, this is used to acces to all QBCore functions and shared data.

```lua
exports['qb-core']:GetCoreObject() -> table -- QBCore object
```

```lua
-- Example
QBCore = exports['qb-core']:GetCoreObject()
```

## Client

### DrawText

Displays a text in the screen in a specific position (Default: left).

```lua
exports['qb-core']:DrawText(string, string?)
```

```lua
-- Example
exports['qb-core']:DrawText('QBCore is amazing', 'left')
```

### ChangeText

Changes the text that is being drawn and its position (Default: left).

```lua
exports['qb-core']:ChangeText(string, string?)
```

```lua
-- Example
exports['qb-core']:ChangeText('QBCore is veeeery amazing', 'right')
```

### HideText

Hides the text that is being displayed

```lua
exports['qb-core']:HideText()
```

### KeyPressed

Send to NUI the message that a key has been pressed and hides the text in screen.

```lua
exports['qb-core']:KeyPressed()
```

## Server

### SetMethod

### SetField

### AddJob

### AddJobs

### RemoveJob

### UpdateJob

### AddItem

### UpdateItem

### AddItems

### RemoveItem

### AddGang

### AddGangs

### RemoveGang

### UpdateGang

### GetCoreVersion

### ExploitBan

```

```
