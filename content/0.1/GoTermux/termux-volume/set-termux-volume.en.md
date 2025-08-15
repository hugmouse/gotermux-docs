---
title: SetTermuxVolume()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Sets the volume for a specific audio stream.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    t "github.com/hugmouse/gotermux"
)

func main() {
    // Set music volume to 10
    musicStream := t.TAudioStream{
        Stream: "MUSIC",
        Volume: 10,
    }
    t.SetTermuxVolume(musicStream)
}
{{< /code >}}

## Parameters

- `v TAudioStream` - Audio stream configuration

## Audio Stream Types

Available audio streams (use these string values):
- `NOTIFICATION` - Notification sounds
- `ALARM` - Alarm sounds  
- `MUSIC` - Music and media playback
- `RING` - Ringtone sounds
- `SYSTEM` - System sounds
- `VOICE_CALL` - Voice call audio

{{< hint "info" >}}
You can also use the AudioStream constants and MapOfAudioStreams from the library for type-safe stream selection.
{{< /hint >}}