---
title: TermuxTelephonyDeviceInfo()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Gets information about the telephony device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    deviceInfo := t.TermuxTelephonyDeviceInfo()
    fmt.Printf("Device ID: %s\n", deviceInfo.DeviceId)
    fmt.Printf("Software Version: %s\n", deviceInfo.SoftwareVersion)
    fmt.Printf("Phone Type: %s\n", deviceInfo.PhoneType)
}
{{< /code >}}

## Return Value

Returns `TDevice` containing telephony device information.

## Struct TDevice

{{< table >}}
| Field               | Type     | Description                    |
|---------------------|----------|--------------------------------|
| `DeviceId`          | `string` | Unique device identifier       |
| `SoftwareVersion`   | `string` | Baseband software version      |
| `PhoneType`         | `string` | Phone type (GSM, CDMA, etc.)   |
| `NetworkOperatorName` | `string` | Network operator name        |
| `NetworkCountryIso` | `string` | Network country ISO code       |
| `SimOperatorName`   | `string` | SIM operator name              |
| `SimCountryIso`     | `string` | SIM country ISO code           |
{{< /table >}}