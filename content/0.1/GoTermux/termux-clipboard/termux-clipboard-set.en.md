---
title: TermuxClipboardSet()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Sets the system clipboard text.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    t "github.com/hugmouse/gotermux"
)

func main() {
    clipboard := t.TClipboard{
        Text: "Hello from GoTermux!",
    }
    t.TermuxClipboardSet(clipboard)
}
{{< /code >}}

## Parameters

- `clip TClipboard` - Clipboard data structure

## Struct TClipboard

{{< table >}}
| Field  | Type     | Description                    |
|--------|----------|--------------------------------|
| `Text` | `string` | Text to set in the clipboard   |
{{< /table >}}

{{< hint "info" >}}
If the text field is empty, the function will log "Clipboard is empty!" and do nothing.
{{< /hint >}}