---
layout: default-layout
title: CameraToggleButton Class - Dynamsoft Capture Vision Flutter
description: CameraToggleButton class of DCV Flutter edition displays a camera preview with customizable UI elements.
keywords: camera, enhancer, barcode reader, flutter, capture vision, view
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CameraToggleButton

`CameraToggleButton` is a widget that represents a camera toggle button with customizable appearance and location. The camera toggle button allows the user to switch between the front and back cameras.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class CameraToggleButton
```

## Properties

### location

Defines the location of the camera toggle button (as a [Rect](https://api.flutter.dev/flutter/dart-ui/Rect-class.html)). This rectangle specifies the button's position and size on the screen. Coordinates are in pixels.

```dart
Rect location;
```

### imageBase64

Sets the image (as a base64 string) to be used for the camera toggle button.

```dart
String? imageBase64;
```

**Remarks**

When setting the imageBase64 string, please note that the string should not include the `data:image/png;base64,` portion of the base64 string.

## Code Snippet

```dart
final CameraToggleButton _cameraToggleBtn = CameraToggle(
    location: Rect.fromLTWH(300, 30, 50, 50),
    imageBase64: "<insert base64 string>"
)
```