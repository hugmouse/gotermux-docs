---
title: "termux-camera-info"
date: 2025-05-04T15:50:02+02:00
draft: false
---

Retrieve detailed information about the device cameras.

## Usage

This API provides information about the cameras on the device, such as their facing direction, supported output sizes,
focal lengths, and other capabilities.

## Example

### Get Camera Information

{{< code lang="shell" >}}
~/ $ termux-camera-info
<---->
Output:

```
[
  {
    "id": "0",
    "facing": "back",
    "jpeg_output_sizes": [
      {
        "width": 4128,
        "height": 3096
      },
      {
        "width": 4128,
        "height": 2580
      }
    ],
    "focal_lengths": [
      3.0799999237060547
    ],
    "auto_exposure_modes": [
      "CONTROL_AE_MODE_OFF",
      "CONTROL_AE_MODE_ON",
      "CONTROL_AE_MODE_ON_AUTO_FLASH",
      "CONTROL_AE_MODE_ON_ALWAYS_FLASH"
    ],
    "physical_size": {
      "width": 4.127999782562256,
      "height": 3.0959999561309814
    },
    "capabilities": [
      "backward_compatible",
      "raw",
      "yuv_reprocessing",
      "private_reprocessing",
      "read_sensor_settings",
      "manual_sensor",
      "burst_capture",
      "manual_post_processing"
    ]
  },
  {
    "id": "1",
    "facing": "front",
    "jpeg_output_sizes": [
      {
        "width": 3264,
        "height": 2448
      },
      {
        "width": 3264,
        "height": 1836
      }
    ],
    "focal_lengths": [
      2.609999895095825
    ],
    "auto_exposure_modes": [
      "CONTROL_AE_MODE_OFF",
      "CONTROL_AE_MODE_ON"
    ],
    "physical_size": {
      "width": 3.590399980545044,
      "height": 2.6928000450134277
    },
    "capabilities": [
      "backward_compatible",
      "raw",
      "private_reprocessing",
      "read_sensor_settings",
      "burst_capture"
    ]
  },
  {
    "id": "2",
    "facing": "back",
    "jpeg_output_sizes": [
      {
        "width": 2576,
        "height": 1932
      },
      {
        "width": 2576,
        "height": 1188
      }
    ],
    "focal_lengths": [
      1.1299999952316284
    ],
    "auto_exposure_modes": [
      "CONTROL_AE_MODE_OFF",
      "CONTROL_AE_MODE_ON"
    ],
    "physical_size": {
      "width": 2.885119915008545,
      "height": 2.1638400554656982
    },
    "capabilities": [
      "backward_compatible",
      "raw",
      "private_reprocessing",
      "read_sensor_settings",
      "manual_sensor",
      "burst_capture",
      "yuv_reprocessing"
    ]
  },
  {
    "id": "3",
    "facing": "front",
    "jpeg_output_sizes": [
      {
        "width": 2608,
        "height": 1956
      },
      {
        "width": 2608,
        "height": 1630
      }
    ],
    "focal_lengths": [
      2.609999895095825
    ],
    "auto_exposure_modes": [
      "CONTROL_AE_MODE_OFF",
      "CONTROL_AE_MODE_ON"
    ],
    "physical_size": {
      "width": 2.920959949493408,
      "height": 2.1907200813293457
    },
    "capabilities": [
      "backward_compatible",
      "raw",
      "private_reprocessing",
      "read_sensor_settings",
      "burst_capture"
    ]
  }
]
```

{{< /code >}}

## Behavior

The API outputs an array of camera details, with one object per camera.

## Types

| Key                   | Type           | Description                                                                                                                         |
|-----------------------|----------------|-------------------------------------------------------------------------------------------------------------------------------------|
| `id`                  | String         | Camera identifier.                                                                                                                  |
| `facing`              | String/Integer | The direction the camera is facing. Possible values are `"front"`, `"back"`, or an integer for unknown types.                       |
| `jpeg_output_sizes`   | Array<Object>  | An array of objects representing supported JPEG output resolutions. Each object has `width` (Integer) and `height` (Integer).       |
| `focal_lengths`       | Array<Float>   | An array of available focal lengths for the lens.                                                                                   |
| `auto_exposure_modes` | Array<String>  | An array of supported auto-exposure modes. Possible values include `"CONTROL_AE_MODE_OFF"`, `"CONTROL_AE_MODE_ON"`, etc.            |
| `physical_size`       | Object         | An object representing the physical dimensions of the camera sensor. Contains `width` (Float) and `height` (Float).                 |
| `capabilities`        | Array<String>  | An array of supported camera capabilities. Possible values include `"backward_compatible"`, `"private_reprocessing"`, `"raw"`, etc. |

## Permissions

Requires `android.permissions.WRITE_SETTINGS`.

## Related

{{< pagelink title="Termux API: CameraInfoAPI.java"
href="https://github.com/termux/termux-api/blob/master/app/src/main/java/com/termux/api/apis/CameraInfoAPI.java" >}}