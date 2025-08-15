---
title: TermuxTTSSpeak()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Speaks text using the system text-to-speech engine.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "log"
    t "github.com/hugmouse/gotermux"
)

func main() {
    ttsConfig := t.TTSSpeak{
        Engine:        "com.google.android.tts",
        Lang:          "en",
        Region:        "US", 
        Variant:       "",
        Rate:          1.0,
        Stream:        t.Music,
        TextToSpeech: "Hello from GoTermux! This is a text-to-speech demonstration.",
    }
    
    err := t.TermuxTTSSpeak(ttsConfig)
    if err != nil {
        log.Printf("TTS error: %v", err)
    }
}
{{< /code >}}

## Parameters

- `t TTSSpeak` - Text-to-speech configuration

## Return Value

Returns `error` - nil on success, error message on failure.

## Struct TTSSpeak

{{< table >}}
| Field          | Type          | Description                           |
|----------------|---------------|---------------------------------------|
| `Engine`       | `string`      | TTS engine to use                     |
| `Lang`         | `string`      | Language code (e.g., "en", "es")     |
| `Region`       | `string`      | Region code (e.g., "US", "GB")       |
| `Variant`      | `string`      | Language variant                      |
| `Rate`         | `float64`     | Speech rate (0.1 to 4.0)             |
| `Stream`       | `AudioStream` | Audio stream for playback             |
| `TextToSpeech` | `string`      | Text to convert to speech             |
{{< /table >}}

## Audio Stream Constants

You can use these constants for the `Stream` field:
- `Notification` - Notification audio stream
- `Alarm` - Alarm audio stream
- `Music` - Music audio stream (recommended for TTS)
- `Ring` - Ringtone audio stream
- `System` - System audio stream
- `VoiceCall` - Voice call audio stream

## Language Examples

Common language/region combinations:
- English (US): `Lang: "en", Region: "US"`
- English (UK): `Lang: "en", Region: "GB"`
- Spanish: `Lang: "es", Region: "ES"`
- French: `Lang: "fr", Region: "FR"`
- German: `Lang: "de", Region: "DE"`

{{< hint "info" >}}
The speech rate should be between 0.1 (very slow) and 4.0 (very fast). A rate of 1.0 is normal speaking speed.
{{< /hint >}}