---
title: TermuxVibrate()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Vibrates the device for a specified duration.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    t "github.com/hugmouse/gotermux"
)

func main() {
    vibration := t.TVibrate{
        Duration:          1000, // 1 second
        SilentModeIgnore: true,  // Vibrate even in silent mode
    }
    
    t.TermuxVibrate(vibration)
}
{{< /code >}}

## Parameters

- `t TVibrate` - Vibration configuration structure

## Struct TVibrate

{{< table >}}
| Field              | Type   | Description                                    |
|--------------------|--------|------------------------------------------------|
| `Duration`         | `uint` | Vibration duration in milliseconds            |
| `SilentModeIgnore` | `bool` | If true, vibrate even when device is silent   |
{{< /table >}}

{{< hint "info" >}}
The vibration duration is specified in milliseconds. For example, 1000 means 1 second of vibration.
{{< /hint >}}