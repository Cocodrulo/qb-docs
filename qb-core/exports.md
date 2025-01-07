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

Adds a new method to `QBCore.Functions`. Returns whether addition was succesfully made and a info message.

```lua
exports['qb-core']:SetMethod(string, function) -> boolean, string
```

```lua
-- Example
exports['qb-core']:SetMethod('DoSmth', function(action)
    print('You have done: '..action)
end)

QBCore.Functions.DoSmth('eating') -- You have done: eating
```

### SetField

Adds a new field to `QBCore` object. Returns whether addition was succesfully made and a info message.

```lua
exports['qb-core']:SetField(string, any) -> boolean, string
```

```lua
-- Example
exports['qb-core']:SetField('Server', {
    version = '1.2.4',
    name = 'QBCore Server'
})

QBCore.Server.version -- '1.2.4'
```

### AddJob

Adds a new job to `QBCore.Shared.Jobs`. Return whether the addition was succesfully made and a info message.

{% hint style="info" %}
You should see how a job is defined in [shared data](/qb-core/shared-data.md#jobs).
{% endhint %}

```lua
exports['qb-core']:AddJob(string, jobtable) -> boolean, string
```

```lua
-- Example
exports['qb-core']:AddJob('sheriff', {
    label = 'Sheriff',
    defaultDuty = true,
    offDutyPay = false,
    grades = {
        ['0'] = {
            name = 'Officer',
            payment = 80
        },
        ['1'] = {
            name = 'Sheriff',
                isboss = true,
            payment = 100
        }
    }
})
```

### AddJobs

Adds multiple jobs to `QBCore.Shared.Jobs`. Return whether the additions were succesfully made and a info message.

{% hint style="info" %}
You should see how a job is defined in [shared data](/qb-core/shared-data.md#jobs).
{% endhint %}

```lua
exports['qb-core']:AddJobs(jobtable[]) -> boolean, string
```

```lua
-- Example
exports['qb-core']:AddJob({
    sheriff = {
        label = 'Sheriff',
        defaultDuty = true,
        offDutyPay = false,
        grades = {
            ['0'] = {
                name = 'Officer',
                payment = 80
            },
            ['1'] = {
                name = 'Sheriff',
                isboss = true,
                payment = 100
            }
        }
    },
    sandy_ambulance = {
        label = 'Sandy Shores Medical Center',
        defaultDuty = true,
        offDutyPay = false,
        grades = {
            ['0'] = {
                name = 'Medic',
                payment = 80
            },
            ['1'] = {
                name = 'Medic Chief',
                isboss = true,
                payment = 100
            }
        }
    }
})
```

### RemoveJob

Remove an existing job from `QBCore.Shared.Jobs`. Return whether removal was succesfully made and a info message.

```lua
exports['qb-core']:RemoveJob(string) -> boolean, string
```

```lua
-- Example
exports['qb-core']:RemoveJob('sheriff')
```

### UpdateJob

Updates an existing job from `QBCore.Shared.Jobs`. Return whether the update was succesfully made and a info message.

{% hint style="info" %}
You should see how a job is defined in [shared data](/qb-core/shared-data.md#jobs).
{% endhint %}

```lua
exports['qb-core']:UpdateJob(string, jobtable) -> boolean, string
```

```lua
-- Example
exports['qb-core']:UpdateJob('sheriff', {
    label = 'Sheriff',
    defaultDuty = true,
    offDutyPay = false,
    grades = {
        ['0'] = {
            name = 'Officer',
            payment = 80
        },
        ['1'] = {
            name = 'Sergeant',
            payment = 90
        },
        ['2'] = {
            name = 'Sheriff',
            isboss = true,
            payment = 100
        }
    }
})
```

### AddItem

Adds a new item to `QBCore.Shared.Items`. Return whether the addition was succesfully made and a info message.

{% hint style="info" %}
You should see how a item is defined in [shared data](/qb-core/shared-data.md#items).
{% endhint %}

```lua
exports['qb-core']:AddItem(string, itemtable) -> boolean, string
```

```lua
-- Example
exports['qb-core']:AddItem('repairkit', {
    name = 'repairkit',
    label = 'Repairkit'
    weight = 2500,
    type = 'item',
    image = 'repairkit.png',
    unique = false,
    useable = true,
    shouldClose = true,
    description = 'A nice toolbox with stuff to repair your vehicle'
})
```

### UpdateItem

Updates an existing item from `QBCore.Shared.Items`. Return whether the update was succesfully made and a info message.

{% hint style="info" %}
You should see how a item is defined in [shared data](/qb-core/shared-data.md#items).
{% endhint %}

```lua
exports['qb-core']:UpdateItem(string, itemtable) -> boolean, string
```

```lua
-- Example
exports['qb-core']:UpdateItem('repairkit', {
    name = 'repairkit',
    label = 'Repair kit from Mechanic'
    weight = 200,
    type = 'item',
    image = 'repairkit.png',
    unique = false,
    useable = true,
    shouldClose = false,
    description = 'A nice toolbox with stuff to repair your vehicle (or not)'
})
```

### AddItems

Adds new items to `QBCore.Shared.Items`. Return whether the additions were succesfully made and a info message.

{% hint style="info" %}
You should see how a item is defined in [shared data](/qb-core/shared-data.md#items).
{% endhint %}

```lua
exports['qb-core']:AddItems(itemtable[]) -> boolean, string
```

```lua
-- Example
exports['qb-core']:AddItems({
    repairkit =  {
        name = 'repairkit',
        label = 'Repairkit'
        weight = 2500,
        type = 'item',
        image = 'repairkit.png',
        unique = false,
        useable = true,
        shouldClose = true,
        description = 'A nice toolbox with stuff to repair your vehicle'
    },
    advancedrepairkit = {
        name = 'advancedrepairkit',
        label = 'Advanced Repairkit',
        weight = 4000,
        type = 'item',
        image = 'advancedkit.png',
        unique = false,
        useable = true,
        shouldClose = true,
        description = 'A nice toolbox with stuff to repair your vehicle'
    }
})
```

### RemoveItem

Remove an existing item from `QBCore.Shared.Items`. Return whether removal was succesfully made and a info message.

```lua
exports['qb-core']:RemoveItem(string) -> boolean, string
```

```lua
-- Example
exports['qb-core']:RemoveItem('repairkit')
```

### AddGang

Adds a new gang to `QBCore.Shared.Gangs`. Return whether the addition was succesfully made and a info message.

{% hint style="info" %}
You should see how a gang is defined in [shared data](/qb-core/shared-data.md#gangs).
{% endhint %}

```lua
exports['qb-core']:AddGang(string, gangtable) -> boolean, string
```

```lua
-- Example
exports['qb-core']:AddJob('lostmc', {
    label = 'The Lost MCs',
    grades = {
        ['0'] = { name = 'Recruit' },
        ['1'] = { name = 'Enforcer' },
        ['2'] = { name = 'Shot Caller' },
        ['3'] = { name = 'Boss', isboss = true },
    },
})
```

### AddGangs

Adds multiple gangs to `QBCore.Shared.Gangs`. Return whether the additions were succesfully made and a info message.

{% hint style="info" %}
You should see how a gang is defined in [shared data](/qb-core/shared-data.md#gangs).
{% endhint %}

```lua
exports['qb-core']:AddGangs(gangtable[]) -> boolean, string
```

```lua
-- Example
exports['qb-core']:AddGangs({
    lostmc = {
        label = 'The Lost MCs',
        grades = {
            ['0'] = { name = 'Recruit' },
            ['1'] = { name = 'Enforcer' },
            ['2'] = { name = 'Shot Caller' },
            ['3'] = { name = 'Boss', isboss = true },
        },
    },
    ballas = {
        label = 'Ballas',
        grades = {
            ['0'] = { name = 'Recruit' },
            ['1'] = { name = 'Enforcer' },
            ['2'] = { name = 'Shot Caller' },
            ['3'] = { name = 'Boss', isboss = true },
        },
    }
})
```

### RemoveGang

Remove an existing gang from `QBCore.Shared.Gangs`. Return whether removal was succesfully made and a info message.

```lua
exports['qb-core']:RemoveGang(string) -> boolean, string
```

```lua
-- Example
exports['qb-core']:RemoveGang('lostmc')
```

### UpdateGang

Updates an existing gang from `QBCore.Shared.Gangs`. Return whether the update was succesfully made and a info message.

{% hint style="info" %}
You should see how a gang is defined in [shared data](/qb-core/shared-data.md#gangs).
{% endhint %}

```lua
exports['qb-core']:UpdateGang(string, gangtable) -> boolean, string
```

```lua
-- Example
exports['qb-core']:UpdateGang('ballas', {
    label = 'Purple Ballas',
    grades = {
        ['0'] = { name = 'Recruit' },
        ['1'] = { name = 'Enforcer' },
        ['2'] = { name = 'Shot Caller bb' },
        ['3'] = { name = 'Boss, my man', isboss = true },
    },
})
```

### GetCoreVersion

Return the version of the QBCore framework.

```lua
exports['qb-core']:GetCoreVersion() -> string
```

```lua
-- Example
local version = exports['qb-core']:GetCoreVersion()
version -- '1.2.6'
```

### ExploitBan

Bans someone because of an script exploit.

```lua
exports['qb-core']:ExploitBan(number, string)
```

```lua
-- Example
exports['qb-core']:ExploitBan(2, "qb-banking")
```
