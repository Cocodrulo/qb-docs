---
description: Use our predefined functions to make more efficient your coding
---

# 📜 Shared Functions

{% hint style="info" %}
All of the functions below are part of the QBCore.Shared module, so you must have imported QBCore before using them.
{% endhint %}

### RandomStr

Returns a new string with the length specified containing random characters.

```lua
QBCore.Shared.RandomStr(number) -> string
```

```lua
-- Example
local text = QBCore.Shared.RandomStr(3)
text -- 'dhl'
```

### RandomInt

Returns a new and random integer number with the length specified containing.

```lua
QBCore.Shared.RandomInt(number) -> number
```

```lua
-- Example
local number = QBCore.Shared.RandomInt(5)
number -- '13792'
```

### SplitStr

Divides a string, by a delimiter, into an ordered list of substrings returning and array-like table.

```lua
QBCore.Shared.SplitStr(string) -> string[]
```

```lua
-- Example
local strings = QBCore.Shared.SplitStr('tomato, lemon, potatoe, orange, apple')
strings -- { 'tomato', 'lemon', 'potatoe', 'orange', 'apple' }
```

### Trim

Removes any trailing whitespace in a string.

```lua
QBCore.Shared.Trim(string) -> string
```

```lua
-- Example
local string = QBCore.Shared.Trim('Hello, my name is Peter    ')
string -- 'Hello, my name is Peter'
```

### Round

Returns the value of a number rounded to the nearest number with the quantity of decimal places specified.

```lua
QBCore.Shared.Trim(number, number?) -> number
```

```lua
-- Example 1
local integer = QBCore.Shared.Round(19.3)
integer -- 19

-- Example 2
local decimal = QBCore.Shared.Round(19.385, 1)
decimal -- 19.4
```

### ChangeVehicleExtra

Enables/Disables a vehicle extra.

```lua
QBCore.Shared.ChangeVehicleExtra(vehicle, number, boolean)
```

```lua
-- Example 1
QBCore.Shared.ChangeVehicleExtra(GetVehiclePedIsIn(PlayerPedId(), false), 1, true)

-- Example 2
QBCore.Shared.ChangeVehicleExtra(GetVehiclePedIsIn(PlayerPedId(), false), 3, false)
```

### SetDefaultVehicleExtras

Sets extras of vehicle as specified in the parameter.

```lua
QBCore.Shared.ChangeVehicleExtra(vehicle, boolean[])
```

```lua
-- Example 1
QBCore.Shared.SetDefaultVehicleExtras(GetVehiclePedIsIn(PlayerPedId(), false), { true, false, true})
-- The above will enable the first and third extra and disable all the others
```
