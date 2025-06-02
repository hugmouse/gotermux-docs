---
title: "termux-dialog"
date: 2025-06-02T16:37:05+02:00
draft: false
---

Display a dialog with widgets and receive user input in JSON.

## Usage

```shell
termux-dialog [options]
```

The command displays a dialog (text input by default) and waits for user interaction. The result is returned in JSON format.

### Available options

| Option              | Description                                                   |
|---------------------|---------------------------------------------------------------|
| `-t <title>`        | Set the dialog title.                                         |
| `-i <hint>`         | Set the input field hint (text input only).                   |
| `-m`                | Allow multiple lines in text input.                           |
| `-n`                | Numeric-only input (text input only).                         |
| `-p`                | Mask input (text input only).                                 |
| `-v <v1,v2,..>`     | Comma-separated values (for checkbox, radio, spinner, sheet). |
| `-r <min,max,init>` | Set counter range (for counter input).                        |
| `-d <fmt>`          | Set date format for date input.                               |

Supported widgets vary from android versions, but the following ones are usually available:

- `confirm` - Show confirmation dialog
- `checkbox` - Select multiple values using checkboxes
- `counter` - Pick a number in specified range
- `date` - Pick a date
- `radio` - Pick a single value from radio buttons
- `sheet` - Pick a value from sliding bottom sheet
- `spinner` - Pick a single value from a dropdown spinner
- `speech` - Obtain speech using device microphone
- `text` - Input text (default if no widget specified)

### Confirm options

- `-i <hint>` - text hint

### Checkbox options

- `-v ",,,"` - comma delim values to use (required)

### Counter options

- `-r min,max,start` - comma delim of (3) numbers to use

### Date options

- `-d "dd-MM-yyyy k:m:s` - SimpleDateFormat Pattern for date widget output

### Radio options

- `-v ",,,"` - comma delim values to use (required)

### Sheet options

- `-v ",,,"` - comma delim values to use (required)

### Speech options

- `-i <hint>` - text hint

### Text options (default)

- `-i <hint>` - text hint
- `-m` - allow multiple lines
- `-n` - enter input as numbers
- `-p` - enter input as password (will be logged in the output as plaintext)

You can't use `-m` with `-n`.

## Related

{{< pagelink title="Termux API: DialogAPI.java"
href="https://github.com/termux/termux-api/blob/master/app/src/main/java/com/termux/api/apis/DialogAPI.java" >}}