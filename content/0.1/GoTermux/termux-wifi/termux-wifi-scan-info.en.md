---
title: TermuxWifiScanInfo()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Retrieves information from the last WiFi scan performed by the Android system.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    scanResults := t.TermuxWifiScanInfo()
    for _, network := range scanResults {
        fmt.Printf("SSID: %s, Signal: %d dBm, Security: %s\n", 
            network.SSID, network.Rssi, network.Capabilities)
    }
}
<---->
Output:
SSID: HomeNetwork, Signal: -42 dBm, Security: WPA2
SSID: OfficeWiFi, Signal: -67 dBm, Security: WPA3
SSID: PublicWiFi, Signal: -78 dBm, Security: Open
{{< /code >}}

## Return Value

Returns `[]TConnectionScan` - array of available WiFi networks from last scan.

## Struct TConnectionScan

{{< table >}}
| Field          | Type     | Description                        |
|----------------|----------|------------------------------------|
| `SSID`         | `string` | Network name                       |
| `BSSID`        | `string` | Router MAC address                 |
| `Rssi`         | `int`    | Signal strength in dBm             |
| `Frequency`    | `int`    | WiFi frequency in MHz              |
| `Capabilities` | `string` | Security capabilities              |
| `Timestamp`    | `int64`  | When this network was last seen    |
{{< /table >}}

{{< hint "warning" >}}
Note: This function does not perform a new scan. It retrieves results from the last scan performed by the Android system.
{{< /hint >}}