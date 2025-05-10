# exports

## Client Exports

***

### GiveKeys

Give keys to player.

```lua
exports.filo_vehiclekey:GiveKeys(entity|plate)
```

### GiveJobKeys

Give job keys to player.

```lua
exports.filo_vehiclekey:GiveJobKeys(entity|plate)
```

### RemoveKeys

Remove keys from player.

```lua
exports.filo_vehiclekey:RemoveKeys(entity|plate)
```

### HasKeys

Returns true if player has keys.

<pre class="language-lua"><code class="lang-lua"><strong>local hasKey = exports.filo_vehiclekey:HasKeys(entity|plate)
</strong>return hasKey
</code></pre>



## Server Exports

***

### GiveKeys

Give keys to player.

```lua
exports.filo_vehiclekey:GiveKeys(playerId, netId|entity|plate)
```

### RemoveKeys

Remove keys from player.

```lua
exports.filo_vehiclekey:RemoveKeys(playerId, netId|entity|plate)
```
