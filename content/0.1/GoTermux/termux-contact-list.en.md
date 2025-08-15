---
title: TermuxContactList()
date: 2025-08-04T13:57:00+02:00
draft: false
---

Returns a list of all contacts stored on the device.

## Usage

{{< code lang="go" example=true >}}
package main

import (
    "fmt"
    t "github.com/hugmouse/gotermux"
)

func main() {
    contacts := t.TermuxContactList()
    
    for _, contact := range contacts {
        fmt.Printf("Name: %s\n", contact.Name)
        fmt.Printf("Phone: %s\n", contact.Number)
        fmt.Println("---")
    }
}
<---->
Output:
Name: John Doe
Phone: +1234567890
---
Name: Jane Smith
Phone: +9876543210
---
{{< /code >}}

## Return Value

Returns `[]TContact` - array of contact information.

## Struct TContact

{{< table >}}
| Field    | Type     | Description           |
|----------|----------|-----------------------|
| `Name`   | `string` | Contact display name  |
| `Number` | `string` | Phone number          |
| `Email`  | `string` | Email address         |
{{< /table >}}

{{< hint "warning" >}}
Accessing contacts requires the READ_CONTACTS permission. The device may prompt for this permission when first used.
{{< /hint >}}