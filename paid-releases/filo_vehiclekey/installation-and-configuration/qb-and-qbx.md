# qb & qbx

#### qb-vehiclekeys & qbx\_vehiclekeys

Delete other vehicle keys script you are using. e.g. qb-vehiclekeys, qbx\_vehiclekeys

The script is made to handle qb-vehiclekeys and qbx\_vehiclekeys exports, so you don't need to change anything.

{% stepper %}
{% step %}
### Install dependencies

check [dependencies-and-minigames.md](dependencies-and-minigames.md "mention") for dependencies and install them.
{% endstep %}

{% step %}
### Add to server.cfg

<pre><code><strong>ensure oxmysql
</strong>ensure ox_lib
ensure framework -- qb-core / qbx_core
ensure ox_target
ensure ox_inventory
ensure filo_vehiclekey
</code></pre>
{% endstep %}

{% step %}
### Add inventory items

Add items to your inventory items list, check below.
{% endstep %}
{% endstepper %}

### QBCore

<details>

<summary>qb-inventory</summary>

{% code title="qb-core/shared/items.lua" %}
```
    lockpick                     = { name = 'lockpick', label = 'Lockpick', weight = 300, type = 'item', image = 'lockpick.png', unique = false, useable = true, shouldClose = true, description = 'Very useful if you lose your keys a lot.. or if you want to use it for something else...' },
    advancedlockpick             = { name = 'advancedlockpick', label = 'Advanced Lockpick', weight = 500, type = 'item', image = 'advancedlockpick.png', unique = false, useable = true, shouldClose = true, description = 'If you lose your keys a lot this is very useful... Also useful to open your beers' },
    vehiclekeys                  = { name = "vehiclekeys", label = "Car Keys", weight = 500, type = "item", image = "vehiclekeys.png", unique = true, useable = true, shouldClose = false, combinable = nil, description = "Keys for your car."},
    tools                        = { name = "tools", label = "Tools", weight = 500, type = "item", image = "tools.png", unique = true, useable = true, shouldClose = false, combinable = nil, description = "Multipurpose tools."},

```
{% endcode %}

</details>

<details>

<summary>ox_inventory</summary>

<pre class="language-lua" data-title="ox_inventory/data/items.lua"><code class="lang-lua"><strong>['advancedlockpick'] = {
</strong>    label = 'Advanced Lockpick',
    description = 'Used to pick locks obviously.',
    weight = 500
},

['lockpick'] = {
    label = 'Lockpick',
    description = 'Used to pick locks obviously.',
    weight = 160
},

["tools"] = {
    label = "Tools",
    description = "Maybe this can cut wires.",
    weight = 800,
    stack = true,
    close = true,
},

['vehiclekeys'] = {
    label = 'Vehicle Keys',
    weight = 220,
    stack = false,
    close = true,
},
</code></pre>

</details>

### QBOX

<details>

<summary>ox_inventory</summary>

{% code title="ox_inventory/data/items.lua" %}
```lua
['advancedlockpick'] = {
    label = 'Advanced Lockpick',
    description = 'Used to pick locks obviously.',
    weight = 500
},

['lockpick'] = {
    label = 'Lockpick',
    description = 'Used to pick locks obviously.',
    weight = 160
},

["tools"] = {
    label = "Tools",
    description = "Maybe this can cut wires.",
    weight = 800,
    stack = true,
    close = true,
},

['vehiclekeys'] = {
    label = 'Vehicle Keys',
    weight = 220,
    stack = false,
    close = true,
},
```
{% endcode %}

</details>

<pre class="language-lua" data-title="qbx_core/config/server.lua" data-overflow="wrap"><code class="lang-lua"><strong>giveVehicleKeys = function(src, plate, vehicle)
</strong>        return exports.filo_vehiclekey:GiveKeys(src, plate)
end,
</code></pre>

