---
title: TermuxDialogConfirm()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Displays a dialog window with confirm widget.

## Usage

This will prompt user with a dialog window with "NO" and "YES" buttons.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    result := gotermux.TermuxDialogConfirm(gotermux.TDialogConfirm{
        Hint:         "This is a hint",
        TDialogTitle: gotermux.TDialogTitle{
            Title: "My title",
        },
    })
    fmt.Printf("%+v", result)
}
<---->
(User clicked on "YES") Output: `{Code:0 Text:yes Index:0 Values:[] Error:}`

(User clicked on "NO") Output: `{Code:0 Text:no Index:0 Values:[] Error:}`

(User clicked outside the window) Output: `{Code:-2 Text: Index:0 Values:[] Error:}`
{{< /code >}}

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}