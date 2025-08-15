---
title: TermuxMediaPlayerScan()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Scans files and adds them to the media content provider.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    // Scan recursively with verbose output
    result := t.TermuxMediaPlayerScan(true, true)
    fmt.Println("Scan result:", result)
    
    // Simple scan without recursion or verbose output
    result2 := t.TermuxMediaPlayerScan(false, false)
    fmt.Println("Simple scan:", result2)
}
{{< /code >}}

## Parameters

- `recur bool` - Set to `true` to scan directories recursively
- `verbose bool` - Set to `true` for verbose output

## Return Value

Returns `string` containing scan results.