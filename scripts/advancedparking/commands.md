# Commands

## deleteSavedVehicles

This command allows admins to delete all vehicles from the database.\
Needs to be executed twice to take effect.

```
/deleteSavedVehicles
```

***

## AdvancedParking:log \[info|warning|error|debug]

Toggle individual log levels at runtime for e.g. quick debugging purposes. First and only argument is the log level you want toggled (not case-sensitive).\
You can permanently set them to the desired value in the provided Log.lua. By default `INFO`, `WARNING` and `ERROR` are set to `true`, only `DEBUG` is set to `false`.

```
/AdvancedParking:log debug
```
