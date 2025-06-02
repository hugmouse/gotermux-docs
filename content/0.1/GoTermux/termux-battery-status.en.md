---
title: TermuxBatteryStatus()
date: 2025-04-30T17:56:20+02:00
draft: false
---

Returns information about the battery status of the device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    battery := t.TermuxBatteryStatus()
    fmt.Println(battery.Percentage)
}
<---->
Output: `38.0`
{{< /code >}}

## Struct

`TBattery` represents the return values from the `TermuxBatteryStatus` API.

{{< table >}}
| Field         | Type                      | Description                                                                                                                                             |
|---------------|---------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Health`      | `string`                  | Battery health status. Possible values: `COLD`, `DEAD`, `GOOD`, `OVERHEAT`, `OVER_VOLTAGE`, `UNKNOWN`, `UNSPECIFIED_FAILURE`.                           |
| `Percentage`  | `uint`                    | Current battery charge percentage.                                                                                                                      |
| `Plugged`     | `string`                  | Charging source. Possible values: `UNPLUGGED`, `PLUGGED_AC`, `PLUGGED_USB`, `PLUGGED_WIRELESS`, and `PLUGGED_<int>` (where `0` means it is on battery). |
| `Status`      | `string`                  | Charging status. Possible values: `CHARGING`, `DISCHARGING`, `FULL`, `NOT_CHARGING`, `UNKNOWN`.                                                         |
| `Temperature` | `Temperature` (`float64`) | Current battery temperature.                                                                                                                            |
{{< /table >}}

`Temperature` is a custom type representing battery temperature as a `float64`.

{{< hint "warning" >}}
Note: `Temperature` is a custom type due to changes in behavior in the Termux API. At some point Termux started to return a string instead of a float in JSON.
{{< /hint >}}

## Termux API reference

{{< pagelink title="termux-battery-status" href="/0.1/termux-api/termux-battery-status" >}}