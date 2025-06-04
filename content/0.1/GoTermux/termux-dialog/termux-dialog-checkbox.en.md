---
title: TermuxDialogCheckbox()
date: 2025-06-02T16:01:44+02:00
draft: false
---

Displays a dialog window with checkbox widget

## Usage

Let's create a dialog where user can check `balls` and/or `ducks`.

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    result := gotermux.TermuxDialogCheckbox(gotermux.TDialogCheckbox{
        Values:       []string{"balls", "ducks"},
        TDialogTitle: gotermux.TDialogTitle{
            Title: "Balls or ducks?",
        },
    })
    fmt.Printf("%+v", result)
}
<---->
If user selects `balls` and `ducks` option, then output looks like this:

```
{
    Code:-1 
    Text:[balls, ducks] 
    Index:0 
    Values:[{Index:0 Text:balls} {Index:1 Text:ducks}] 
    Error:
}
```

If user selects only `ducks`:

```
{
    Code:-1 
    Text:[ducks] 
    Index:0 
    Values:[{Index:1 Text:ducks}] 
    Error:
}
```
{{< /code >}}

## Termux API reference

{{< pagelink title="termux-dialog" href="/0.1/termux-api/termux-dialog" >}}