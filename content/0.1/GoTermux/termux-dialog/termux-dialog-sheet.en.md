---
title: TermuxDialogSheet()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Displays sheet dialog

## Usage

Let's create a sheet dialog where user can select an action from a bottom sheet.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    result := gotermux.TermuxDialogSheet(
        gotermux.TDialogSheet{
            gotermux.TDialogCheckbox{
                Values: []string{"Share", "Edit", "Delete", "Copy"},
                Title:  "Choose an action", 
            }
        })
    fmt.Printf("%+v", result)
}
{{< /code >}}

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}