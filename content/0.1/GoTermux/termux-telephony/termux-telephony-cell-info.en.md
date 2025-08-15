---
title: TermuxTelephonyCellInfo()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Gets information about all observed cell towers from all radios on the device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    cellInfo := t.TermuxTelephonyCellInfo()
    for i, cell := range cellInfo {
        fmt.Printf("Cell %d: Type=%s, MCC=%d, MNC=%d\n", 
            i+1, cell.Type, cell.Mcc, cell.Mnc)
    }
}
{{< /code >}}

## Return Value

Returns `[]TCellInfo` - array of cell tower information.

## Struct TCellInfo

{{< table >}}
| Field        | Type     | Description                      |
|--------------|----------|----------------------------------|
| `Type`       | `string` | Cell type (GSM, LTE, WCDMA, etc.)|
| `Mcc`        | `int`    | Mobile Country Code              |
| `Mnc`        | `int`    | Mobile Network Code              |
| `Lac`        | `int`    | Location Area Code               |
| `Cid`        | `int`    | Cell ID                          |
| `SignalStrength` | `int` | Signal strength in dBm          |
{{< /table >}}