---
title: TermuxBrightness()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Sets the display brightness of the device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    t "github.com/hugmouse/gotermux"
)

func main() {
    // Set brightness to 50% (128 out of 255)
    result := t.TermuxBrightness(128)
    
    // Set brightness to maximum
    t.TermuxBrightness(255)
    
    // Set brightness to minimum
    t.TermuxBrightness(0)
}
{{< /code >}}

## Parameters

- `val uint8` - Brightness value from 0 (minimum) to 255 (maximum)

## Return Value

Returns `[]byte` containing the command output.

{{< hint "warning" >}}
Note: This may not work if automatic brightness control is enabled on the device.
{{< /hint >}}

## Termux API reference

{{< pagelink title="termux-brightness" href="/0.1/termux-api/termux-brightness" >}}