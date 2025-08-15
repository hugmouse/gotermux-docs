---
title: TermuxDialogRadio()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Displays a dialog window with radio widget

## Usage

Let's create a radio dialog where user can select one option from a list of programming languages.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    result := gotermux.TermuxDialogRadio(
        gotermux.TDialogRadio{
            gotermux.TDialogCheckbox{
                Values: []string{"Go", "Python", "JavaScript", "Rust"},
                Title:  "Choose your favorite language",
    }})
    fmt.Printf("%+v", result)
}
{{< /code >}}

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}