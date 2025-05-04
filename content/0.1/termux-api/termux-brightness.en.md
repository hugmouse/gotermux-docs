---
title: "termux-brightness"
date: 2025-05-04T15:31:27+02:00
draft: false
---

Control the device screen brightness.

## Usage

This API allows you to control the screen brightness and toggle between automatic and manual brightness modes. You can specify the desired brightness level or enable automatic brightness adjustment.

## Arguments

| Argument        | Type    | Description                                                                                     |
|-----------------|---------|-------------------------------------------------------------------------------------------------|
| `brightness`    | Integer | Optional. The desired screen brightness level (0-255).                                         |
| `auto`          | Boolean | Optional. Set to `true` to enable automatic brightness mode or `false` for manual mode.        |

## Example

### Set Brightness Level to 100
{{< code lang="shell" >}}
~/ $ termux-brightness --brightness 100
<---->
Output:
Brightness set to 100.
{{< /code >}}

### Enable Automatic Brightness
{{< code lang="shell" >}}
~/ $ termux-brightness --auto true
<---->
Output:
Automatic brightness enabled.
{{< /code >}}

## Behavior

- If no arguments are provided, the brightness level defaults to `0`.
- Brightness levels are clamped between `0` (minimum brightness) and `255` (maximum brightness).
- The `auto` mode determines whether the screen brightness is manually set or automatically adjusted based on ambient light.

## Related

{{< pagelink title="Termux API: BrightnessAPI.java"
href="https://github.com/termux/termux-api/blob/master/app/src/main/java/com/termux/api/apis/BrightnessAPI.java" >}}