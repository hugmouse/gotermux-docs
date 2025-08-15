---
title: TermuxToast()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Shows text in a Toast (a transient popup notification).

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "log"
    t "github.com/hugmouse/gotermux"
)

func main() {
    toast := t.TToast{
        Text:            "Hello from GoTermux!",
        BackgroundColor: t.Blue,
        TextColor:       t.White,
        ToastPosition:   t.Top,
        Short:           true,
    }
    
    err := t.TermuxToast(toast)
    if err != nil {
        log.Println("Toast error:", err)
    }
}
{{< /code >}}

## Parameters

- `t TToast` - Toast configuration structure

## Struct TToast

{{< table >}}
| Field                    | Type     | Description                                      |
|--------------------------|----------|--------------------------------------------------|
| `Text`                   | `string` | Text to display in the toast                     |
| `BackgroundColor`        | `Color`  | Background color using predefined colors        |
| `BackgroundColorAARRGGBB`| `string` | Background color using hex format (#AARRGGBB)   |
| `TextColor`              | `Color`  | Text color using predefined colors              |
| `TextColorAARRGGBB`      | `string` | Text color using hex format (#AARRGGBB)         |
| `ToastPosition`          | `Position`| Position on screen (Top, Middle, Bottom)       |
| `Short`                  | `bool`   | Show toast for a short duration if true         |
{{< /table >}}

## Color Constants

Available predefined colors:
- `Black`, `Blue`, `Cyan`, `DarkGray`, `Gray`, `Green`
- `LightGray`, `Magenta`, `Red`, `Transparent`, `White`, `Yellow`

## Position Constants

- `Top` - Display at top of screen
- `Middle` - Display in middle of screen (default)
- `Bottom` - Display at bottom of screen

## Return Value

Returns `error` - nil on success, error message on failure.

{{< hint "info" >}}
You can use either predefined colors (BackgroundColor/TextColor) or hex colors (BackgroundColorAARRGGBB/TextColorAARRGGBB), but not both for the same color type.
{{< /hint >}}