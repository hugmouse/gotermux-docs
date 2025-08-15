---
title: TermuxMediaPlayerPlayFile()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Plays a specified media file.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    t "github.com/hugmouse/gotermux"
)

func main() {
    // Play a music file
    t.TermuxMediaPlayerPlayFile("/storage/emulated/0/Music/song.mp3")
}
{{< /code >}}

## Parameters

- `path string` - Full path to the media file to play

{{< hint "info" >}}
The media player supports common audio formats like MP3, AAC, OGG, and FLAC.
{{< /hint >}}