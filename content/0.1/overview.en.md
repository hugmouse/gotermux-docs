---
title: Overview
icon: coffee
weight: 1
date: 2025-04-30T17:56:20+02:00
---

Welcome to GoTermux documentation. GoTermux is a wrapper around termux-api CMD scripts.

## Convention

Function names in GoTermux follow the same naming style as Termux API commands, but without dashes (`-`):

{{< columns >}}
### GoTermux
{{< code lang="go" >}}
gotermux.TermuxBatteryStatus()
{{< /code >}}
<---->
### Termux API
{{< code lang="shell" >}}
~/ $ termux-battery-status
{{< /code >}}
{{< /columns >}}

## Quickstart

First of all, you need to install `termux-api` package:

```bash
pkg install termux-api
```

And also `Go`:

```bash
pkg install golang
```

And let's create an `example` folder inside of `~/go/src/`, then init a go module:

```bash
mkdir -r ~/go/src/example
cd ~/go/src/example
go mod init
```

Then we need to download `GoTermux` library:

```bash
go get github.com/hugmouse/gotermux
```

And now we can finally use it. Create `main.go` inside of `~/go/src/example/` folder and put the following code in there:

{{< code lang="go" >}}
package main

import (
    "fmt"
    "github.com/hugmouse/gotermux"
)

func main() {
    fmt.Println(gotermux.TermuxBatteryStatus()) 
}
<---->
This code will print the following: `{GOOD 77 UNPLUGGED DISCHARGING 22.8}`
{{< /code >}}

And then you can execute it using `go run main.go`.