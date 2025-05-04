---
title: "termux-call-log"
date: 2025-05-04T15:37:58+02:00
draft: false
---

Retrieve call log history information.

## Usage

This API allows you to access the call log history of the device. You can specify the number of records to retrieve and the starting point for the query.

## Arguments

| Argument  | Type    | Description                                                                                      |
|-----------|---------|--------------------------------------------------------------------------------------------------|
| `offset`  | Integer | Optional. The starting point for the query. Defaults to `0` (first record).                      |
| `limit`   | Integer | Optional. The maximum number of call log records to retrieve. Defaults to `50`.                  |

## Example

### Retrieve the Last 10 Call Logs
{{< code lang="shell" >}}
~/ $ termux-call-log --limit 10
<---->
Output:
```
[
  {
    "name": "John Doe",
    "phone_number": "+1234567890",
    "type": "INCOMING",
    "date": "2025-05-04 10:15:30",
    "duration": "00:02:45",
    "sim_id": "SIM1"
  },
  {
    "name": "UNKNOWN_CALLER",
    "phone_number": "+0987654321",
    "type": "MISSED",
    "date": "2025-05-03 18:45:00",
    "duration": "00:00:00",
    "sim_id": "SIM2"
  }
]
```
{{< /code >}}

### Retrieve Call Logs Starting at Offset 20
{{< code lang="shell" >}}
~/ $ termux-call-log --offset 20 --limit 10
<---->
Output:
```
[
  {
    "name": "Jane Smith",
    "phone_number": "+1122334455",
    "type": "OUTGOING",
    "date": "2025-05-02 14:30:00",
    "duration": "00:05:30",
    "sim_id": "SIM1"
  }
]
```
{{< /code >}}

## Output

The API returns call log entries in JSON format. Each entry contains the following fields:

| JSON Key       | Type    | Description                                                         |
|----------------|---------|---------------------------------------------------------------------|
| `name`         | String  | The name of the caller. If unavailable, defaults to `UNKNOWN_CALLER`. |
| `phone_number` | String  | The phone number of the call.                                       |
| `type`         | String  | The type of call (e.g., `INCOMING`, `OUTGOING`, `MISSED`, etc.).    |
| `date`         | String  | The date and time of the call in `yyyy-MM-dd HH:mm:ss` format.      |
| `duration`     | String  | The call duration in `hh:mm:ss` format.                             |
| `sim_id`       | String  | The SIM card identifier (e.g., `SIM1`, `SIM2`).                     |

## Call Types

| Call Type        | Description                         |
|------------------|-------------------------------------|
| `BLOCKED`        | The call was blocked.               |
| `INCOMING`       | The call was an incoming call.      |
| `MISSED`         | The call was missed.                |
| `OUTGOING`       | The call was an outgoing call.      |
| `REJECTED`       | The call was rejected.              |
| `VOICEMAIL`      | The call was a voicemail.           |
| `UNKNOWN_TYPE`   | The call type is unknown.           |

## Related

{{< pagelink title="Termux API: CallLogAPI.java"
href="https://github.com/termux/termux-api/blob/master/app/src/main/java/com/termux/api/apis/CallLogAPI.java" >}}
