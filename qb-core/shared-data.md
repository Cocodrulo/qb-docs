---
description: View the data that you can access with your QBCore object
---

# 📄 Shared Data

{% hint style="info" %}
This data can be modified through the files them selvers (and then restarting the server) or through the exports mentioned in [exports](/qb-core/exports.md) for this purpose.
{% endhint %}

### Items

-   Found in qb-core/shared/items.lua

An item has different properties following always this scheme:

```lua
[string] = {
    name = string,              -- Actual item name for spawning/giving/removing
    label = string,             -- Label of item that is shown in inventory slot
    weight = number,            -- How much the items weighs
    type = 'item' | 'weapon',   -- What type the item is
    image = string,             -- This item image that is found in qb-inventory/html/image
    unique = boolean,           -- Is the item unique (true|false) - Cannot be stacked & accepts item info to be assigned
    useable = boolean,          -- Is the item useable (true|false) - Must still be registered as useable
    shouldClose = boolean,      -- This is refered to "Should close when item is used"
    combinable = nil | table,   -- Is the item able to be combined with another? (nil|table)
    description = string        -- Description of time in inventory
}
```

A combinable table must like like:

```lua
{
    accept = string[],      -- The other item that can be it can be combined with
    reward = string,        -- The item that is rewarded upon successful combine
    anim = {                -- Set the animation, progressbar text and length of time it takes to combine
        dict = string,      -- The animation dictionary
        lib = string,       -- The animation library
        text = string,      -- Text that will be displayed in the progress bar
        timeOut = number,   -- How long the animation should take to complete
    }
}
```

### Jobs

-   Found in qb-core/shared/jobs.lua

A job has different properties following always this scheme:

```lua
[string] = {                        -- Job name
    label = string,                 -- Job label
    type = string,                  -- Job type
    defaultDuty = boolean,          -- Enable/disable player being auto clocked-in
    offDutyPay = boolean,           -- Enable/disable player being paid when not on duty
    grades = {
        [string] = {                -- Job grade
            name = string,          -- Job grade name
            payment = number        -- Paycheck amount
            isboss = boolean?       -- Whether that rank is a boss or not (if not boss property can be ommited)
        }
    }
}
```

### Vehicles / VehicleHashes

-   Found in qb-core/shared/vehicles.lua

A vehicle has different properties following always this scheme:

```lua
{
    model = string,                                             -- Vehicle model/spawn name
    name = string,                                              -- Vehicle label
    brand = string,                                             -- Vehicle brand name
    price = number,                                             -- Vehicle price in shop
    category = string,                                          -- Vehicle category in dealership
    type = 'automobile' | 'bike' | 'plane' | 'heli' | 'boat',   -- Vehicle type
    shop = string,                                              -- Shop where the vehicle is available for sale
}
```

QBCore adds automaticly to this table the `hash` and `spawncode` properties. Also QBCore make the model name the key of that table, so for seaching a vehicle by the model name will be like this:

```lua
local vehicle_data = QBCore.Shared.Vehicles['adder']
```

Also the framework have introduced another vehicle-related table called `VehicleHashes` which instead of using the vehicle model to search for a vehicle, now the hash will be used. You will have access to the same information but with an easier to obtain data in real situations.

```lua
local vehicle_hash = GetEntityModel(GetVehiclePedIsIn(PlayerPedId(), false))
local vehicle_data = QBCore.Shared.VehicleHashes[vehicle_hash]
```

### Gangs

-   Found in qb-core/shared/gangs.lua

A gang has different properties following always this scheme:

```lua
[string] = {                    -- Name of the gang
    label = string,             -- Label of the gang
    grades = {
        [string] = {            -- Rank grade
            name = string,      -- Rank visible name
            isboss = boolean?   -- Whether that rank is a boss or not (if not boss property can be ommited)
        },
    },
}
```

### Weapons

-   Found in qb-core/shared/weapons.lua

{% hint style="warning" %}
Weapons must be added in qb-core/shared/items.lua as well!
{% endhint %}

A weapon has different properties following always this scheme:

```lua
[hash] = {                  -- Weapon hash (uses compile-time Jenkins hashes | joaat() or GetHashKey())
    name = string,          -- Actual item name for spawning/giving/removing
    label = string,         -- Label of item that is shown in inventory slot
    weapontype = string,    -- The type weapon (Melee / Pistol / Submachine Gun...)
    ammotype = string?,     -- The type of ammo this weapon accepts (AMMO_PISTOL / AMMO_STUNGUN / AMMO_SMG...)
    damagereason = string   -- If damaged with this weapon what would be the message of death cause
},
```
