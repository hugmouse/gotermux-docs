---
title: TermuxWifiConnectionInfo()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Gets information about the current WiFi connection.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    connection := t.TermuxWifiConnectionInfo()
    fmt.Printf("SSID: %s\n", connection.SSID)
    fmt.Printf("BSSID: %s\n", connection.BSSID)
    fmt.Printf("IP: %s\n", connection.IP)
    fmt.Printf("Signal Strength: %d\n", connection.Rssi)
}
<---->
Output:
SSID: MyWiFiNetwork
BSSID: aa:bb:cc:dd:ee:ff
IP: 192.168.1.100
Signal Strength: -45
{{< /code >}}

## Return Value

Returns `TConnection` with current WiFi connection details.

## Struct TConnection

{{< table >}}
| Field          | Type     | Description                        |
|----------------|----------|------------------------------------|
| `SSID`         | `string` | Network name                       |
| `BSSID`        | `string` | Router MAC address                 |
| `IP`           | `string` | Device IP address                  |
| `Rssi`         | `int`    | Signal strength in dBm             |
| `LinkSpeed`    | `int`    | Connection speed in Mbps           |
| `Frequency`    | `int`    | WiFi frequency in MHz              |
| `NetworkId`    | `int`    | Network identifier                 |
| `Hidden`       | `bool`   | Whether network is hidden          |
{{< /table >}}