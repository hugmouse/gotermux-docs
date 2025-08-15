---
title: TermuxDialogSpeech()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Displays a dialog window with speech widget

## Usage

Let's create a speech dialog that captures voice input from the user.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    result := gotermux.TermuxDialogSpeech(
        gotermux.TDialogSpeech{
            gotermux.TDialogConfirm{
                Hint:  "Say something...",
                Title: "Voice Input",
            }
    })
    fmt.Printf("%+v", result)
}
{{< /code >}}

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}