# Installation

## Requirements

* OneSync
* [MySQL Async Library](https://forum.cfx.re/t/release-mysql-async-library-3-3-2/21881) or [OxMySQL](https://forum.cfx.re/t/standalone-oxmysql-lightweight-mysql-wrapper/4755120)
* [kimi\_callbacks](https://github.com/Kiminaze/kimi\_callbacks/releases/latest)

## Instructions

**Note:** Updating from any release before v3.0.0 requires you to delete the database table `vehicle_parking` once! Saved data is **not** compatible with the new version.

1. Download the script from your keymaster website and extract it into your resources folder.
2. Download and install mysql-async or OxMySQL (can be skipped if using ESX or QB).
3. Download [kimi\_callbacks.zip](https://github.com/Kiminaze/kimi\_callbacks/releases/latest) and extract it into your resources folder.
4.  Start the resource in your server.cfg:

    ```
    ensure AdvancedParking
    ```

***

## Compatibility

### Deleting vehicles

The vehicle persistence might require you to edit some scripts in order to delete vehicles properly. This has been made very easy thanks to the included file `fixDeleteVehicle.lua`.

* Drop it into the folder of a resource that does not delete vehicles properly (including `es_extended` or `qb-core`).
*   Then add the following line inside the fxmanifest of that resource:

    {% code fullWidth="false" %}
    ```lua
    shared_script "fixDeleteVehicle.lua"
    ```
    {% endcode %}

**Note:** There might be some scripts out there where this will not work. If you find yourself in this situation, it might be best to simply ask for help in our support.
