# Exports (server)

### DeleteVehicle(vehicle, keepInWorld)

Deletes a vehicle from the world and the internal table so that it doesn't respawn.

<mark style="color:red;">**Parameters:**</mark>\
**vehicle** - `int` - The vehicle to delete.\
**keepInWorld?** - `bool` - If the vehicle should stay in the world.

```lua
exports["AdvancedParking"]:DeleteVehicle(vehicle, false)
```

***

<details>

<summary>GetVehiclePosition(plate)</summary>

Returns the position of a single vehicle.

<mark style="color:red;">**Parameters:**</mark>\
**plate** - `string` - The license plate text of a vehicle.

<mark style="color:green;">**Returns:**</mark>\
`vector3?` - The position of the vehicle or nil.

<pre class="language-lua"><code class="lang-lua"><strong>local position = exports["AdvancedParking"]:GetVehiclePosition(plate)
</strong></code></pre>

</details>

### GetVehiclePosition(plate)

Returns the position of a single vehicle.

<mark style="color:red;">**Parameters:**</mark>\
**plate** - `string` - The license plate text of a vehicle.

<mark style="color:green;">**Returns:**</mark>\
`vector3?` - The position of the vehicle or nil.

<pre class="language-lua"><code class="lang-lua"><strong>local position = exports["AdvancedParking"]:GetVehiclePosition(plate)
</strong></code></pre>

***

### GetVehiclePositions(...)

Returns the positions of several given vehicles.

<mark style="color:red;">**Parameters:**</mark>\
**...** - `string` - Variable number of license plates as arguments.

<mark style="color:green;">**Returns:**</mark>\
`dictionary<string, vector3>` - The positions of the vehicles. Can be empty if none was found.

```lua
local positions = GetVehiclePositions(plate1, plate2, plate3)
for plate, position in pairs(positions) do
    print(plate .. ": " .. tostring(position))
end
```

***

<details>

<summary>DeleteVehicleUsingData(identifier, networkId, plate, keepInWorld)</summary>



Delete a vehicle without having access to the entity directly. At least one of the first three parameters must be provided.

<mark style="color:red;">**Parameters:**</mark>\
**identifier?** - `string` - The unique identifier provided by AdvancedParking.\
**networkId?** - `int` - The vehicle entity's network id.\
**plate?** - `string` - The vehicles license plate text.\
**keepInWorld?** - `bool` - If the vehicle should stay in the world.

```lua
local identifier = Entity(vehicle).state.ap_id
local networkId = NetworkGetNetworkIdFromEntity(vehicle)
local plate = GetVehicleNumberPlateText(vehicle)

exports["AdvancedParking"]:DeleteVehicleUsingData(identifier, networkId, plate, true)
```

</details>

### DeleteVehicleUsingData(identifier, networkId, plate, keepInWorld)

Delete a vehicle without having access to the entity directly. At least one of the first three parameters must be provided.

<mark style="color:red;">**Parameters:**</mark>\
**identifier?** - `string` - The unique identifier provided by AdvancedParking.\
**networkId?** - `int` - The vehicle entity's network id.\
**plate?** - `string` - The vehicles license plate text.\
**keepInWorld?** - `bool` - If the vehicle should stay in the world.

```lua
local identifier = Entity(vehicle).state.ap_id
local networkId = NetworkGetNetworkIdFromEntity(vehicle)
local plate = GetVehicleNumberPlateText(vehicle)

exports["AdvancedParking"]:DeleteVehicleUsingData(identifier, networkId, plate, true)
```

***

### EnsureStateBag(vehicle, bagKey)

Ensures that a specific state bag on an entity is saved by AdvancedParking.

<mark style="color:red;">**Parameters:**</mark>\
**vehicle** - `int` - The vehicle to check the state bag.\
**bagKey** - `string` - The key of the state bag to check for.

<mark style="color:green;">**Returns:**</mark>\
`bool` - true on success, false when e.g. state bag was missing

```lua
local success = exports["AdvancedParking"]:EnsureStateBag(vehicle, "fuel")
```

***

### GetVehicleFromStateBagValue(bagKey, bagValue)

Tries to find a vehicle that has a specific state bag value attached.

<mark style="color:red;">**Parameters:**</mark>\
**bagKey** - `string` - The key to search for.\
**bagValue** - `any` - The value to search for.

<mark style="color:green;">**Returns:**</mark>\
`int?` - The vehicle handle if a match was found.

```lua
local vehicle = exports["AdvancedParking"]:GetVehicleFromStateBagValue(bagKey, bagValue)
```

***

### GetStateBagsFromVehicle(vehicle)

Gets all state bags from a vehicle that has been saved by AdvancedParking.

<mark style="color:red;">**Parameters:**</mark>\
**vehicle** - `int` - The vehicle handle.

<mark style="color:green;">**Returns:**</mark>\
`dictionary<bagKey, bagValue>` - A table containing all found state bag keys and values.

```lua
local stateBags = exports["AdvancedParking"]:GetStateBagsFromVehicle(vehicle)
```

***

### GetStateBagsFromPlate(plate)

Gets all state bags from a vehicle that has been saved by AdvancedParking given its plate.

<mark style="color:red;">**Parameters:**</mark>\
**plate** - `string` - The vehicle's license plate text.

<mark style="color:green;">**Returns:**</mark>\
`dictionary<bagKey, bagValue>` - A table containing all found state bag keys and values.

```lua
local stateBags = exports["AdvancedParking"]:GetStateBagsFromPlate("KIMINAZE")
```
