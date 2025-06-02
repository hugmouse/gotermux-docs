---
title: TermuxDialog()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Creates a dialog with a specified title.

## Usage

Let's create a dialog with title "This is a test" and print out the result.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    result := t.TermuxDialog("This is a test")
    fmt.Printf("%+v", result)
}
<---->
![](/termux-dialog.en.jpg)
Output: `{Code:-1 Text:This is my answer Index:0 Values:[] Error:}`
{{< /code >}}

## Struct

Code descriptions:

- `Code` status `-1` means user pressed "OK" in a dialog window
- `Code` status `-2` means user pressed "CANCEL", pressed `ESC` or tapped out of the dialog window

Function returns `TResult`:

{{< table >}}
| Field    | Type       | Description                                                       |
| -------- | ---------- | ----------------------------------------------------------------- |
| `Code`   | `int8`     | `-2`, `-1` or `0`, error code description depends on the function |
| `Text`   | `string`   | Text that user wrote into a message dialog                        |
| `Index`  | `uint`     | Dialog window index                                               |
| `Values` | `[]TValue` | Unused for `TermuxDialog`                                         |
| `Error`  | `string`   | Unused for `TermuxDialog`                                         |
{{< /table >}}

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}