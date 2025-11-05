---
layout: default-layout
title: EnumColourChannelUsageType - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumColourChannelUsageType of DBR Flutter Edition defines the available colour channels for the Camera Enhancer to use when capturing images or frames
keywords: colour channel, capture vision, camera, enhancer, pixel, format
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumColourChannelUsageType
---

# EnumColourChannelUsageType

`EnumColourChannelUsageType` is an enumeration that specifies the different colour channels that are available to the Camera Enhancer. The colour channel affects the pixel type that the captured images or frames will come out in, so it can output grayscale or colour images.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumColourChannelUsageType {
    auto,
    fullChannel,
    yChannelOnly,
    rgbRChannelOnly,
    rgbGChannelOnly,
    rgbBChannelOnly
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `auto` | Automatic colour channel usage determination based on image pixel format and scene. |
| `fullChannel` | Uses all colour channels to output a full colour image. |
| `yChannelOnly` | Uses only the luminance channel to output a grayscale image. |
| `rgbRChannelOnly` | Uses only the red channel of the RGB space. |
| `rgbGChannelOnly` | Uses only the green channel of the RGB space. |
| `rgbBChannelOnly` | Uses only the blue channel of the RGB space. |
