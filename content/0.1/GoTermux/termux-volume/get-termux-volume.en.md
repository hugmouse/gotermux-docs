---
title: GetTermuxVolume()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Returns information about all audio streams on the device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    audioStreams := t.GetTermuxVolume()
    for _, stream := range audioStreams {
        fmt.Printf("Stream: %s, Volume: %d, Max: %d\n", 
            stream.Stream, stream.Volume, stream.MaxVolume)
    }
}
<---->
Output:
Stream: NOTIFICATION, Volume: 7, Max: 15
Stream: ALARM, Volume: 10, Max: 15
Stream: MUSIC, Volume: 12, Max: 15
{{< /code >}}

## Return Value

Returns `[]TAudioStream` - array of audio stream information.

## Struct TAudioStream

{{< table >}}
| Field       | Type     | Description                           |
|-------------|----------|---------------------------------------|
| `Stream`    | `string` | Audio stream name                     |
| `Volume`    | `uint`   | Current volume level                  |
| `MaxVolume` | `uint`   | Maximum volume for this stream        |
{{< /table >}}