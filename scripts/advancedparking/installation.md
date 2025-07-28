# Installation

## Requirements

* OneSync
* [MySQL Async Library](https://forum.cfx.re/t/release-mysql-async-library-3-3-2/21881) or [OxMySQL](https://forum.cfx.re/t/standalone-oxmysql-lightweight-mysql-wrapper/4755120)
* [kimi\_callbacks](https://github.com/Kiminaze/kimi_callbacks/releases/latest)

## Instructions

1. Download the script from [Portal](https://portal.cfx.re/assets/created-assets) and extract it into your resources folder.\
   (do _**not**_ use the experimental version unless you explicitly want to)
2. Download and install OxMySQL (can be skipped if you are already using it).
3. Download [kimi\_callbacks.zip](https://github.com/Kiminaze/kimi_callbacks/releases/latest) and extract it into your resources folder.
4.  Start the resource in your server.cfg:

    {% code fullWidth="false" %}
    ```lua
    ensure AdvancedParking
    ```
    {% endcode %}
5. Make sure to implement [the fix below](https://docs.kiminaze.de/scripts/advancedparking/installation#deleting-vehicles) if you still need to delete vehicles!

***

### Deleting vehicles

This has been made very easy thanks to the included file `fixDeleteVehicle.lua` that you will find inside the AdvancedParking folder. **You don´t need to use the exports!**

This fix should be added to your framework resource (`es_extended`, `qb-core`, etc) first and foremost!

*   Simply add the following line inside the fxmanifest of the respective resource:

    {% code fullWidth="false" %}
    ```lua
    shared_script "@AdvancedParking/fixDeleteVehicle.lua"
    ```
    {% endcode %}
* Refresh the resource list and restart the respective resource or restart your server after adding the line.

{% hint style="danger" %}
<mark style="color:yellow;">If any other script does not delete a vehicle properly (it gets deleted but appears again) then repeat this step in the respective script.</mark>
{% endhint %}

{% hint style="info" %}
There might be some scripts out there where this will _not_ work. If you find yourself in this situation, it might be best to simply ask for help in our support.
{% endhint %}

{% embed url="https://www.youtube.com/watch?v=Re2zKc_FpCk" %}
