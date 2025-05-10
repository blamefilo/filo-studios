# jg-advancedgarages

{% code title="jg-advancedgarages/config/config.lua" overflow="wrap" %}
```lua
Config.VehicleKeys = "filo_vehiclekey" -- or "qb-vehiclekeys", "MrNewbVehicleKeys", "jaksam-vehicles-keys", "qs-vehiclekeys", "mk_vehiclekeys", "wasabi_carlock", "cd_garage", "okokGarage", "t1ger_keys", "Renewed", "tgiann-hotwire", "filo_vehiclekey", "none"
```
{% endcode %}

{% code title="jg-advancedgarages/framework/cl-functions.lua" %}
```lua
---@param plate string
---@param vehicleEntity integer
---@param origin "personal" | "job" | "gang"
function Framework.Client.VehicleGiveKeys(plate, vehicleEntity, origin)
  if not DoesEntityExist(vehicleEntity) then return false end
  if not plate or plate == "" then
    print("^1[ERROR] No plate provided to VehicleGiveKeys function^0")
    return false
  end

  plate = plate:upper()

  if Config.VehicleKeys == "qb-vehiclekeys" then
    TriggerEvent("vehiclekeys:client:SetOwner", plate)
  elseif Config.VehicleKeys == "jaksam-vehicles-keys" then
    TriggerServerEvent("vehicles_keys:selfGiveVehicleKeys", plate)
  elseif Config.VehicleKeys == "mk_vehiclekeys" then
    exports["mk_vehiclekeys"]:AddKey(vehicleEntity)
  elseif Config.VehicleKeys == "qs-vehiclekeys" then
    local model = GetDisplayNameFromVehicleModel(GetEntityModel(vehicleEntity))
    exports["qs-vehiclekeys"]:GiveKeys(plate, model)
  elseif Config.VehicleKeys == "wasabi_carlock" then
    exports.wasabi_carlock:GiveKey(plate)
  elseif Config.VehicleKeys == "cd_garage" then
    TriggerEvent("cd_garage:AddKeys", plate)
  elseif Config.VehicleKeys == "okokGarage" then
    TriggerServerEvent("okokGarage:GiveKeys", plate)
  elseif Config.VehicleKeys == "t1ger_keys" then
    if origin == "job" then
      local vehicleName = GetDisplayNameFromVehicleModel(GetEntityModel(vehicleEntity))
      exports['t1ger_keys']:GiveJobKeys(plate, vehicleName, true)
    else
      TriggerServerEvent("t1ger_keys:updateOwnedKeys", plate, true)
    end
  elseif Config.VehicleKeys == "MrNewbVehicleKeys" then
    exports.MrNewbVehicleKeys:GiveKeys(vehicleEntity)
  elseif Config.VehicleKeys == "Renewed" then
    exports["Renewed-Vehiclekeys"]:addKey(plate)
  elseif Config.VehicleKeys == "tgiann-hotwire" then
    exports["tgiann-hotwire"]:CheckKeyInIgnitionWhenSpawn(vehicleEntity, plate)
  elseif Config.VehicleKeys == "filo_vehiclekey" then
    if origin == "job" then
      exports.filo_vehiclekey:GiveJobKeys(plate)
    else
      exports.filo_vehiclekey:GiveKeys(plate)
    end
  end
end
```
{% endcode %}
