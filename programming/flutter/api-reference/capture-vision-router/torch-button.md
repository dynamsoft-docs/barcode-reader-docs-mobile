---
layout: default-layout
title: TorchButton Class - Dynamsoft Capture Vision Flutter
description: TorchButton class of DCV Flutter edition represents a torch (flash) toggle button with customizable appearance and location.
keywords: camera, enhancer, barcode reader, flutter, torch, flash, button
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# TorchButton

`TorchButton` is a class that represents a torch (flashlight) toggle button - allowing the user to customize the torch button of the [`CameraView`](camera-view.md) how they see fit.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class TorchButton
```

## Properties

### location

Sets the location of the torch button as a [Rect](https://api.flutter.dev/flutter/dart-ui/Rect-class.html) - this rectangle specifies the button's position and size on the screen. When creating a custom torch button, **this property must be set**.

```dart
 Rect location;
 ```

**Remarks**

When setting the rectangle, please remember that the coordinates are in *pixels*.

### torchOnImageBase64

Sets the icon image (as a base64 string) that will be displayed when the torch is on.

```dart
String? torchOnImageBase64;
```

### torchOffImageBase64

Sets the icon image (as a base64 string) that will be displayed when the torch is off.

```dart
String? torchOffImageBase64;
```

## Code Snippet

```dart
final TorchButton _torch = TorchButton(
	location: Rect.fromLTWH(300, 30, 50, 50), // places the torch button towards the top-right corner of the camera view
	torchOffImageBase64: 'insert_base64_string_here',
	torchOnImageBase64: 'insert_base64_string_here'
);
```
