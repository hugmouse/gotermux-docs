---
title: TermuxShare()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Shares a file or text with other applications on the device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    // Share text with send action
    shareConfig := t.TShare{
        Action:  t.TShareSend,
        Title:   "Check this out!",
        Default: false,
    }
    
    result := t.TermuxShare(shareConfig)
    fmt.Println("Share result:", result)
}
{{< /code >}}

## Parameters

- `t TShare` - Share configuration structure

## Struct TShare

{{< table >}}
| Field     | Type          | Description                                |
|-----------|---------------|--------------------------------------------|
| `Action`  | `ShareAction` | Share action type                          |
| `Title`   | `string`      | Title for the share dialog                 |
| `Default` | `bool`        | Use default handler without showing dialog |
{{< /table >}}

## ShareAction Constants

- `TShareView` - Open content for viewing
- `TShareEdit` - Open content for editing  
- `TShareSend` - Send/share content with other apps

## Return Value

Returns `string` containing the result of the share operation.

## Examples

### Share with View Action

{{< code lang="go" example=true >}}
shareConfig := t.TShare{
    Action: t.TShareView,
    Title:  "View Document",
}
t.TermuxShare(shareConfig)
{{< /code >}}

### Share with Default Handler

{{< code lang="go" example=true >}}
shareConfig := t.TShare{
    Action:  t.TShareSend,
    Default: true, // Skip app chooser dialog
}
t.TermuxShare(shareConfig)
{{< /code >}}

{{< hint "info" >}}
This function can share files specified as arguments or text received on stdin. The specific content to share depends on how you invoke the underlying termux-share command.
{{< /hint >}}