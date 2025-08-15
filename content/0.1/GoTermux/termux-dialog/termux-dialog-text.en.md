---
title: TermuxDialogText()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Displays a dialog window with text

## Usage

Let's create a text input dialog where user can enter their name.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    result := gotermux.TermuxDialogText(gotermux.TDialogText{
        Hint:  "Enter your name",
        Title: "What's your name?",
    })
    fmt.Printf("%+v", result)
}
{{< /code >}}

### Multiline Text Input

You can also create a multiline text dialog:

```go
result := gotermux.TermuxDialogText(gotermux.TDialogText{
    Hint:         "Enter your bio",
    Title:        "Tell us about yourself",
    MultipleLine: true,
})
```

### Number Input

For numeric input only:

```go
result := gotermux.TermuxDialogText(gotermux.TDialogText{
    Hint:        "Enter your age",
    Title:       "How old are you?",
    NumberInput: true,
})
```

Note: You cannot use both `MultipleLine` and `NumberInput` at the same time.

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}