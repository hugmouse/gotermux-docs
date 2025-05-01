---
title: "termux-battery-status"
date: 2025-04-30T17:56:20+02:00
draft: false
---

Get the status of the device battery.

## Usage

This program does not take any arguments.
Output is returned in JSON format.

## Example

{{< code lang="shell" >}}
~/ $ termux-battery-status
<---->
Output:

```
{
  "present": true,
  "technology": "Li-ion",
  "health": "GOOD",
  "plugged": "UNPLUGGED",
  "status": "DISCHARGING",
  "temperature": "22.3",
  "voltage": 4099,
  "current": -820000,
  "current_average": -576,
  "percentage": 85,
  "level": 85,
  "scale": 100,
  "charge_counter": 3194654,
  "energy": null
}
```

{{< /code >}}

## Types

| JSON Key          | Type          | Description                                                                                          |
|-------------------|---------------|------------------------------------------------------------------------------------------------------|
| `present`         | Boolean       | Indicates if the battery is present                                                                  |
| `technology`      | String        | The battery technology (e.g., Lithium-ion)                                                           |
| `health`          | String        | The health of the battery (e.g., COLD, DEAD, GOOD, OVERHEAT, etc.)                                   |
| `plugged`         | String        | The type of power source the device is plugged into (e.g., UNPLUGGED, PLUGGED_AC, PLUGGED_USB, etc.) |
| `status`          | String        | The charging status of the battery (e.g., CHARGING, DISCHARGING, FULL, NOT_CHARGING, etc.)           |
| `temperature`     | Double/String | The battery temperature in degrees Celsius, rounded to 1 decimal place                               |
| `voltage`         | Integer       | The battery voltage in millivolts (mV)                                                               |
| `current`         | Integer       | The instantaneous battery current in microamperes (µA)                                               |
| `current_average` | Integer       | The average battery current in microamperes (µA)                                                     |
| `percentage`      | Integer       | The battery charge percentage (0-100)                                                                |
| `level`           | Integer       | The battery charge level                                                                             |
| `scale`           | Integer       | The maximum battery charge level                                                                     |
| `charge_counter`  | Integer       | The charge counter in microampere-hours (µAh)                                                        |
| `energy`          | Long          | The energy counter in nanowatt-hours (nWh)                                                           |
| `cycle`           | Integer       | The battery cycle count (optional, available since Android 14)                                       |

## Related

{{< pagelink title="Termux API: BatteryStatusAPI.java"
href="https://github.com/termux/termux-api/blob/master/app/src/main/java/com/termux/api/apis/BatteryStatusAPI.java" >}}