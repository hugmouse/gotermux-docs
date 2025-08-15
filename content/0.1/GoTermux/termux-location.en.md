---
title: TermuxLocation()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Gets the current device location using GPS or network providers.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    locationRequest := t.TLocation{
        Provider: "gps",
        Request:  "once",
    }
    
    location := t.TermuxLocation(locationRequest)
    fmt.Printf("Latitude: %f, Longitude: %f\n", 
        location.Latitude, location.Longitude)
    fmt.Printf("Accuracy: %f meters\n", location.Accuracy)
}
<---->
Output:
Latitude: 37.4219999, Longitude: -122.0840575
Accuracy: 10.0 meters
{{< /code >}}

## Parameters

- `location TLocation` - Location request configuration

## Struct TLocation

{{< table >}}
| Field      | Type     | Description                                |
|------------|----------|--------------------------------------------|
| `Provider` | `string` | Location provider ("gps", "network", etc.)|
| `Request`  | `string` | Request type ("once", "updates", etc.)    |
{{< /table >}}

## Return Value

Returns `TLocationResult` containing location information.

## Struct TLocationResult

{{< table >}}
| Field        | Type      | Description                      |
|--------------|-----------|----------------------------------|
| `Latitude`   | `float64` | Latitude coordinate              |
| `Longitude`  | `float64` | Longitude coordinate             |
| `Altitude`   | `float64` | Altitude in meters               |
| `Accuracy`   | `float64` | Location accuracy in meters      |
| `Bearing`    | `float64` | Direction of travel in degrees   |
| `Speed`      | `float64` | Speed in meters per second       |
| `Timestamp`  | `int64`   | Unix timestamp of location fix   |
| `Provider`   | `string`  | Provider used for location       |
{{< /table >}}

## Location Providers

- `gps` - GPS satellite positioning (more accurate, requires clear sky)
- `network` - Network-based positioning (faster, works indoors)
- `passive` - Use cached location from other apps

## Request Types

- `once` - Get location once and return
- `updates` - Get continuous location updates

{{< hint "warning" >}}
Location access requires appropriate permissions. The device may prompt for location permission when first used.
{{< /hint >}}