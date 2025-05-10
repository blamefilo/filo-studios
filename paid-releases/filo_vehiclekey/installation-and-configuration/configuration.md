---
description: default configuration for filo_vehiclekey
---

# configuration



{% code title="filo_vehiclekey/config/shared.lua" %}
```lua
return {
    Interaction = "qb-target", -- "ox_lib", "ox_target", "qb-target", "sleepless_interact"
    TextUI = "native", -- "ox_lib", "native", "custom"

    MaxDistance = 5.0, -- max distance to check for vehicle

    Keybinds = {
        Lock = "L",
        Engine = "G"
    },

	LockpickItem = "lockpick", -- lockpick item name
	AdvancedLockpickItem = "advancedlockpick", -- advanced lockpick item name
	ToolsItem = "tools", -- tools item name

    KeylessModels = { -- vehicle models which uses keyless fobs (must be in ticks)
        `voltic`,
		`voltic2`,
		`caddy`,
		`caddy2`,
		`caddy3`,
		`surge`,
		`iwagen`,
		`raiden`,
		`airtug`,
		`neon`,
		`omnisegt`,
		`cyclone`,
		`tezeract`,
		`rcbandito`,
		`imorgon`,
		`dilettante`,
		`dilettante2`,
		`khamelion`,
    },
}
```
{% endcode %}
