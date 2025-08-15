---
title: TermuxTelephonyCall()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Makes a phone call to the specified number.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    result := t.TermuxTelephonyCall("+1234567890")
    fmt.Printf("Call result: Code=%d, Text=%s\n", result.Code, result.Text)
}
{{< /code >}}

## Parameters

- `number string` - Phone number to call (include country code)

## Return Value

Returns `TResult` with call status information.

{{< hint "warning" >}}
This function requires the CALL_PHONE permission and will prompt the user for permission when first used.
{{< /hint >}}