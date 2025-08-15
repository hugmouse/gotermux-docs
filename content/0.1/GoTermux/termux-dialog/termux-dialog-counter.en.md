---
title: TermuxDialogCounter()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Displays a dialog window with counter widget

## Usage

Let's create a counter dialog where user can select a number between 1 and 10, starting at 5.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    result := gotermux.TermuxDialogCounter(gotermux.TDialogCounter{
        Min:   1,
        Max:   10,
        Start: 5,
        Title: "Pick a number",
    })
    fmt.Printf("%+v", result)
}
{{< /code >}}

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}