# Exports (client)

### StartOrbitCam(position, entity, minRadius, maxRadius)

Starts the orbit camera.

<mark style="color:red;">**Parameters:**</mark>\
**position** - `vector3` - The initial position to focus on.\
**entity** - `integer?` - The entity to follow. If set, **position** will be the offset to the entity. Can be omitted.\
**minRadius** - `float?` - The minimum radius the camera will orbit at. Can be omitted.\
**maxRadius** - `float?` - The maximum radius the camera will orbit at. Can be omitted.

***

### EndOrbitCam()

Stops the orbit camera.

***

### UpdateCamPosition(position, entity, minRadius, maxRadius)

Sets the camera focus to a different position (or updates other values).

<mark style="color:red;">**Parameters:**</mark>\
**position** - `vector3` - The position to focus on.\
**entity** - `integer?` - The entity to follow. If set, **position** will be the offset to the entity. Can be omitted.\
**minRadius** - `float?` - The minimum radius the camera will orbit at. Can be omitted.\
**maxRadius** - `float?` - The maximum radius the camera will orbit at. Can be omitted.

***

### IsOrbitCamActive()

Check if the orbit cam is currently active.

<mark style="color:green;">**Returns:**</mark>\
`bool` - True if the camera is currently active.

***

### IsEntityBeingTracked(entity)

Checks if an entity is being tracked. Omitting **entity** parameter checks for any entity.

<mark style="color:red;">**Parameters:**</mark>\
**entity** - `integer?` - Entity to check. Can be omitted.

<mark style="color:green;">**Returns:**</mark>\
`bool` - If the/any entity is being tracked.

***

### GetTrackedEntity()

Returns the currently tracked entity

<mark style="color:green;">**Returns:**</mark>\
`integer?` - The handle of the tracked entity or nil if there is none.
