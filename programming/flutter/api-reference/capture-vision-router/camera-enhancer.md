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

### disableEnhancedFeatures

Disables the selected and activated enhanced features (represented by [`EnumEnhancedFeatures`](../enum/enhanced-features-camera.md)) of the Camera Enhancer.

```dart
Future<void> disableEnhancedFeatures(int features)
```

### enableEnhancedFeatures

Activates the selected enhanced features (represented by [`EnumEnhancedFeatures`](../enum/enhanced-features-camera.md)) provided by the Camera Enhancer library, including the auto-zoom and smart torch features.

```dart
Future<void> enableEnhancedFeatures(int features)
```

**Remarks**

This method must be used **after [`setInput`](capture-vision-router.md#setinput) and before the [`open`](#open) method**. If you would like to activate multiple enhanced features, then they must be combined using the OR (`|`) operator.

```dart
await _cvr.setInput(_camera);
_camera.enableEnhancedFeatures(EnumEnhancedFeatures.autoZoom | EnumEnhancedFeatures.smartTorch);
_camera.open();
```

### getCameraPosition

Returns the current camera being used, represented as a [`EnumCameraPosition`](../enum/camera-position.md).

```dart
Future<EnumCameraPosition> getCameraPosition() async
```

### getColourChannelUsageType

Retrieves the current colour channel (as a [`EnumColourChannelUsageType`](../enum/colour-channel.md)) that is being used by the camera enhancer.

```dart
Future<EnumColourChannelUsageType> getColourChannelUsageType()
```

**Remarks**

This method should be used to verify which colour channel the camera is using, and in turn verify what pixel type any images retrieved during the capture process will come out in.

### getFocusMode

Returns the current focus mode of the camera, represented as a [`EnumFocusMode`](../enum/focus-mode.md).

```dart
Future<EnumFocusMode> getFocusMode() async 
```

### getScanRegion

Returns the current scan region as a [`DSRect`](dsrect.md) object.

```dart
Future<DSRect?> getScanRegion() async
```

### open

Opens the selected camera to begin the capture process.

```dart
Future<void> open()
```

### selectCamera

Selects the camera based on the specified [`EnumCameraPosition`](../enum/camera-position.md).

```dart
Future<void> selectCamera(EnumCameraPosition position)
```

**Remarks**

If you attempt to select the **backDualWideAuto** or the **backUltraWide** cameras on an Android phone, an exception will be thrown as those cameras are only available on iPhones. Supported devices include: iPhone 13 Pro, iPhone 13 Pro Max, iPhone 14 Pro, iPhone 14 Pro Max, iPhone 15 Pro, iPhone 15 Pro Max. This method must be called **after [`setInput`](capture-vision-router.md#setinput) and before the [`open`](#open) method**.

### setColourChannelUsageType

Defines the colour channel (as a [`EnumColourChannelUsageType`](../enum/colour-channel.md)) used by the camera enhancer - therefore determining whether the captured images or frames will come out in grayscale or colour (or one of the individual colours).

```dart
Future<void> setColourChannelUsageType(EnumColourChannelUsageType type)
```

**Remarks**

This method should be used to change the pixel type of the original image or captured frame should you choose to retrieve it after the capture process. In order to retrieve the original image after the barcode is decoded or the captured result is received, please refer to [this article].

### setFocus

Sets the focus point as well as the mode (as a [`EnumFocusMode`](../enum/focus-mode.md)) for the camera.

```dart
Future<void> setFocus(Point<double> point, EnumFocusMode focusMode)
```

### setScanRegion

Sets the scan region of the camera and displays a bordered area on the UI to represent the scan region. To learn how to specify the scan region, please visit this [section of the foundational user guide](../../explore-features/ui-customization.md#specifying-a-scan-region).

```dart
Future<void> setScanRegion(DSRect region) async
```

**Remarks**

This method must be called **after [`setInput`](capture-vision-router.md#setinput) and before the [`open`](#open) method**.

### setZoomFactor

Sets the zoom factor of the camera.

```dart
Future<void> setZoomFactor( double zoom )
```

### turnOffTorch

Turns off the camera's flashlight (if available).

```dart
Future<void> turnOffTorch()
```

### turnOnTorch

Turns on the camera's flashlight (if available).

```dart
Future<void> turnOnTorch()
```
