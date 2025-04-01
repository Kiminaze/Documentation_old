# Exports (client)

## Enable

Enable/disable automatic saving of vehicles for a client.

<mark style="color:red;">**Parameters:**</mark>\
**enable** - `bool` - true to enable, false to disable

```lua
exports["AdvancedParking"]:Enable(false)
```



***

## UpdateVehicle

Allows manually updating a vehicle if necessary.

<mark style="color:red;">**Parameters:**</mark>\
**vehicle** - `int` - Valid vehicle entity handle

```lua
exports["AdvancedParking"]:UpdateVehicle(vehicle)
```



***

## GetVehiclePosition

Returns the position of a single vehicle.

<mark style="color:red;">**Parameters:**</mark>\
**plate** - `string` - The license plate text of a vehicle.

<mark style="color:green;">**Returns:**</mark>\
`vector3?` - The position of the vehicle or nil.

```lua
local position = exports["AdvancedParking"]:GetVehiclePosition(plate)
```



***

## GetVehiclePositions

Returns the positions of several given vehicles.

<mark style="color:red;">**Parameters:**</mark>\
&#xNAN;**...** - `string` - The license plates of several vehicles as parameters.

<mark style="color:green;">**Returns:**</mark>\
`dictionary<plate, position>` - The positions of the vehicles. Can be empty if none was found.

```lua
local positions = GetVehiclePositions(plate1, plate2, plate3)
for plate, position in pairs(positions) do
    print(plate .. ": " .. tostring(position))
end
```



***

## DeleteVehicle

Deletes a vehicle from the world and the internal table so that it doesn't respawn.

<mark style="color:red;">**Parameters:**</mark>\
**vehicle** - `int` - The vehicle to delete.\
**keepInWorld?** - `bool` - If the vehicle should stay in the world.

```lua
exports["AdvancedParking"]:DeleteVehicle(vehicle, false)
```



***

## DeleteVehicleOnServer

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

exports["AdvancedParking"]:DeleteVehicleOnServer(identifier, networkId, plate, true)
```
