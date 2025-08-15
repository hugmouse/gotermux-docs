---
title: TermuxMediaPlayerInfo()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Gets information about the current playback.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    info := t.TermuxMediaPlayerInfo()
    fmt.Println("Playback info:", info)
}
<---->
Output: Playback info: {"current_position": 42000, "duration": 180000, "state": "playing"}
{{< /code >}}

## Return Value

Returns `string` containing JSON with playback information including current position, duration, and playback state.