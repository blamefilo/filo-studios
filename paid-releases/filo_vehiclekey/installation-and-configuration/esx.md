# esx

{% stepper %}
{% step %}
## Install dependencies

check [dependencies-and-minigames.md](dependencies-and-minigames.md "mention") for dependencies and install them.
{% endstep %}

{% step %}
## Add inventory items

Add items to your inventory items list, check below.
{% endstep %}

{% step %}
### Add to server.cfg

<pre><code><strong>ensure oxmysql
</strong>ensure ox_lib
ensure es_extended
ensure ox_target
ensure ox_inventory
ensure filo_vehiclekey
</code></pre>
{% endstep %}

{% step %}
### Configure config/shared.lua

Set OldESX to true if you're using old version of es\_extended
{% endstep %}
{% endstepper %}

<details>

<summary>ox_inventory</summary>

{% code title="ox_inventory/data/items.lua" overflow="wrap" %}
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
