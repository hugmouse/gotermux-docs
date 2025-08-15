---
title: TermuxTTSEngines()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Gets information about available text-to-speech engines on the device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    engines := t.TermuxTTSEngines()
    fmt.Printf("Default Engine: %s\n", engines.DefaultEngine)
    
    for _, engine := range engines.Engines {
        fmt.Printf("Engine: %s, Label: %s\n", engine.Name, engine.Label)
    }
}
<---->
Output:
Default Engine: com.google.android.tts
Engine: com.google.android.tts, Label: Google Text-to-speech Engine
{{< /code >}}

## Return Value

Returns `TTSEngine` containing information about available TTS engines.

## Struct TTSEngine

{{< table >}}
| Field           | Type           | Description                         |
|-----------------|----------------|-------------------------------------|
| `DefaultEngine` | `string`       | Default TTS engine package name     |
| `Engines`       | `[]TTSEngineInfo` | Array of available engines       |
{{< /table >}}

## Struct TTSEngineInfo

{{< table >}}
| Field   | Type     | Description                |
|---------|----------|----------------------------|
| `Name`  | `string` | Engine package name        |
| `Label` | `string` | Human-readable engine name |
{{< /table >}}