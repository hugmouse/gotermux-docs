---
title: TermuxWifiEnable()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Toggles WiFi on or off.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    t "github.com/hugmouse/gotermux"
)

func main() {
    // Enable WiFi
    t.TermuxWifiEnable(true)
    
    // Disable WiFi
    t.TermuxWifiEnable(false)
}
{{< /code >}}

## Parameters

- `on bool` - Set to `true` to enable WiFi, `false` to disable