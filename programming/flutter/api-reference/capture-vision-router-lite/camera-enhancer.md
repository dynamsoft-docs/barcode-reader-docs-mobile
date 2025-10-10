---
layout: default-layout
title: CameraEnhancer Class - Dynamsoft Capture Vision Flutter
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

Sets the scan region of the camera and displays a bordered area on the UI to represent the scan region. To learn how to specify the scan region, please visit this [section of the foundational user guide](../../foundational-user-guide.md#specify-the-scan-region).

```dart
Future<void> setScanRegion( DSRect region )
```

**Remarks**

This method must be called **after [`setInput`](capture-vision-router.md#setinput) and before the [`open`](#open) method**.

### selectCamera

Selects the camera based on the specified [`EnumCameraPosition`](../enum/camera-position.md).

```dart
Future<void> selectCamera(EnumCameraPosition position)
```

**Remarks**

If you attempt to select the **backDualWideAuto** or the **backUltraWide** cameras on an Android phone, an exception will be thrown as those cameras are only available on iPhones. Supported devices include: iPhone 13 Pro, iPhone 13 Pro Max, iPhone 14 Pro, iPhone 14 Pro Max, iPhone 15 Pro, iPhone 15 Pro Max. This method must be called **after [`setInput`](capture-vision-router.md#setinput) and before the [`open`](#open) method**. 

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

### enableEnhancedFeatures

Activates the selected enhanced features (represented by [`EnumEnhancedFeatures`](../enum/enhanced-features-camera.md)) provided by the Camera Enhancer library, including the auto-zoom and smart torch features.

```dart
Future<void> enableEnhancedFeatures( int features )
```

**Remarks**

This method must be used **after [`setInput`](capture-vision-router.md#setinput) and before the [`open`](#open) method**. If you would like to activate multiple enhanced features, then they must be combined using the OR (`|`) operator.

```dart
await _cvr.setInput(_camera);
_camera.enableEnhancedFeatures(EnumEnhancedFeatures.autoZoom | EnumEnhancedFeatures.smartTorch);
_camera.open();
```

### disableEnhancedFeatures

Disables the selected and activated enhanced features (represented by [`EnumEnhancedFeatures`](../enum/enhanced-features-camera.md)) of the Camera Enhancer.

```dart
Future<void> disableEnhancedFeatures(int features)
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
