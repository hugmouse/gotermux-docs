---
title: TermuxDialogSpinner()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Displays a dialog window with spinner widget

## Usage

Let's create a spinner dialog where user can select a city from a dropdown list.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    result := gotermux.TermuxDialogSpinner(
        gotermux.TDialogSpinner{
            gotermux.TDialogCheckbox{
                Values: []string{"New York", "London", "Tokyo", "Paris", "Berlin"},
                Title:  "Select a city",
            }
    })
    fmt.Printf("%+v", result)
}
{{< /code >}}

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}