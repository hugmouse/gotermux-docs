---
title: TermuxTorch()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Toggles the LED torch (flashlight) on the device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    t "github.com/hugmouse/gotermux"
)

func main() {
    // Turn on the torch
    t.TermuxTorch(true)
    
    // Turn off the torch
    t.TermuxTorch(false)
}
{{< /code >}}

## Parameters

- `on bool` - Set to `true` to enable torch, `false` to disable

{{< hint "info" >}}
The function will log "Turning on the LED torch" or "Turning off the LED torch" to indicate the action being performed.
{{< /hint >}}