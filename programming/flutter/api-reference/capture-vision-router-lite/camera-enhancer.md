---
layout: default-layout
title: CameraEnhancer Class - Dynamsoft Capture Vision Router Lite Flutter
description: CameraEnhancer class of DCV Flutter edition manages camera operations and enhancements.
keywords: camera, enhancer, barcode reader, flutter, capture vision
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CameraEnhancer

The `CameraEnhancer` class provides camera-specific functionality including camera selection, focus control, zoom, and other enhanced features. The `CameraEnhancer` is also responsible for the basic UI of the camera view.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class CameraEnhancer
```

## Methods

### open

Opens the selected camera to begin the capture process.

```dart
Future<void> open()
```

### setScanRegion

Sets the scan region of the camera and displays a bordered area on the UI to represent the scan region.

```dart
Future<void> setScanRegion( DSRect region )
```

### setZoomFactor

Sets the zoom factor of the camera.

```dart
Future<void> setZoomFactor( double zoom )
```

### turnOnTorch

Turns on the camera's flashlight (if available).

```dart
Future<void> turnOnTorch()
```

### turnOffTorch

Turns off the camera's flashlight (if available).

```dart
Future<void> turnOffTorch()
```

### close

Closes the camera and releases the related resources. When the `CaptureVisionRouter` instance calls `stopCapturing`, please make sure to call this method as well to ensure that the resources are released properly.

```dart
Future<void> close()
```

### destroy

Destroys the camera enhancer instance and releases the related resources on the host side.

```dart
Future<void> destroy()
```
