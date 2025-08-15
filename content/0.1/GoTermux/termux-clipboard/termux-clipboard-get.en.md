---
title: TermuxClipboardGet()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Gets the current system clipboard text.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    clipboardText := t.TermuxClipboardGet()
    fmt.Println("Clipboard contains:", clipboardText)
}
<---->
Output: `Clipboard contains: Hello World`
{{< /code >}}

## Return Value

Returns `string` containing the current clipboard text.