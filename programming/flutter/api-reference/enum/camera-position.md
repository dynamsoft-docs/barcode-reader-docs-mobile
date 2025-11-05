---
layout: default-layout
title: EnumCameraPosition - Dynamsoft Barcode Reader Flutter
description: Enumeration EnumCameraPosition of DBR Flutter Edition defines the possible camera(s) to choose from.
keywords: camera enhancer, position, flutter, barcode
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: EnumCameraPosition
---

# EnumCameraPosition

`EnumCameraPosition` is an enumeration that defines the possible camera positions that are available to a device. The majority of modern mobile devices have a front and a rear camera. The more recent iPhones also come with multiple rear cameras, each being suited to different scenarios.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
enum EnumCameraPosition {
    back,
    front,
    backUltraWide,
    backDualWideAuto
}
```

## Members

| Member | Description |
| ------ | ----------- |
| `back` | The default, back-facing camera. It is a wide-angle camera for general usage. |
| `front` | The front-facing camera. |
| `backUltraWide` | The back-facing ultra-wide-angle camera - which should be used for macro-distance scenarios. (iOS ONLY) |
| `backDualWideAuto` | The back-facing virtual camera that can automatically switch between the default wide-angle and the ultra-wide-angle cameras. Supported devices include: iPhone 13 Pro, iPhone 13 Pro Max, iPhone 14 Pro, iPhone 14 Pro Max, iPhone 15 Pro, iPhone 15 Pro Max. (iOS ONLY) |
