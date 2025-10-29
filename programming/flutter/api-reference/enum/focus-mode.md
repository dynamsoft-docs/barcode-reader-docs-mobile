---
layout: default-layout
title: EnumFocusMode - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumFocusMode of DBR Flutter Edition defines the available focus modes of the Camera Enhancer.
keywords: focus mode, capture vision, camera, enhancer
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumFocusMode
---

# EnumFocusMode

`EnumFocusMode` is an enumeration that specifies the different modes of focus that the Camera Enhancer can apply to the camera feed.

> [!TIP]
> If you choose to use the locked focus mode, the focal length used is determined by the input value of [`setFocus`](../capture-vision-router/camera-enhancer.md#setfocus).

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumFocusMode
{
    /** Lock the focal length with an input value. **/
    locked,
    /** Implements a continuous autoFocus.  **/
    continuousAuto
}
```
