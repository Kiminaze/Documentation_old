# Events (client)

### AP:vehicleSpawned

Triggered when a vehicle has been spawned by AdvancedParking. This is also triggered for players outside of scope, so you need to check if the entity exists.

<mark style="color:red;">**Parameters:**</mark>\
**vehicleNetworkId** - `int` - The vehicle's network id.

```lua
AddEventHandler("AP:vehicleSpawned", function(vehicleNetworkId)
    if (not NetworkDoesEntityExistWithNetworkId(vehicleNetworkId)) then return end
    
    local vehicle = NetworkGetEntityFromNetworkId(vehicleNetworkId)
    print("Vehicle " .. GetVehicleNumberPlateText(vehicle) .. " spawned")
end)
```
