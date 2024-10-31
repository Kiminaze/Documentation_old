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

    {% code fullWidth="false" %}
    ```lua
    ensure AdvancedParking
    ```
    {% endcode %}
5. Adding the [`Deleting vehicles`](installation.md#deleting-vehicles) function to your framework and other scripts, if they need to remove vehicle that are saved by AdvancedParking.

***

### Deleting vehicles

This has been made very easy thanks to the included file `fixDeleteVehicle.lua` that you will find inside the AdvancedParking folder. **You don´t need to use the exports!**

* Copy and paste the `fixDeleteVehicle.lua` file into the folder of your framework like  `es_extended` or `qb-core`. ( Directly in the framework folder, not in any sub folder. )
*   Then add the following line inside the fxmanifest of that framework resource:

    {% code fullWidth="false" %}
    ```lua
    shared_script "fixDeleteVehicle.lua"
    ```
    {% endcode %}
* Do a `refresh` or restart your server after adding the `fixDeleteVehicle.lua.`

{% hint style="danger" %}
<mark style="color:yellow;">If any other script does not delete a vehicle properly (The car gets deleted but appears instantly again.) then repeat these steps in the respective script.</mark>
{% endhint %}

{% hint style="info" %}
There might be some scripts out there where this will not work. If you find yourself in this situation, it might be best to simply ask for help in our support.
{% endhint %}

{% embed url="https://youtu.be/Kv-V1RktcTc" %}
