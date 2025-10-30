---
layout: default-layout
title: CameraView Class - Dynamsoft Capture Vision Flutter
description: CameraView class of DCV Flutter edition displays a camera preview with customizable UI elements.
keywords: camera, enhancer, barcode reader, flutter, capture vision, view
needGenerateH3Content: true
needAutoGenerateSidebar: true
noTitleIndex: true
---

# CameraView

`CameraView` is a widget that integrates with the `CameraEnhancer` - providing a camera interface with configurable and customizable UI components like torch control, scan region visualization, and custom drawing layers.

## Definition

*Assembly:* dynamsoft_capture_vision_flutter

```dart
class CameraView
```

## Properties

| Property | Description |
| -------- | ----------- |
| [`cameraEnhancer`](#cameraenhancer) | Sets the `CameraEnhancer` instance that the `CameraView` is attached to. |
| [`cameraToggleButton`](#cameratogglebutton) | Defines a custom widget to replace the default camera toggle button. |
| [`cameraToggleButtonVisible`](#cameratogglebuttonvisible) | Determines whether the camera toggle button is visible. |
| [`scanLaserVisible`](#scanlaservisible) | Determines whether the scan laser will be visible in the scan region. |
| [`scanRegionMaskVisible`](#scanregionmaskvisible) | Establishes whether the scan region will be represented visually using a mask. |
| [`torchButtonVisible`](#torchbuttonvisible) | Controls the visibility of the torch/flash button. |
| [`torchButton`](#torchbutton) | Defines a custom `TorchButton` instead of the default torch icon. |
| [`visibleLayerIds`](#visiblelayerids) | Defines which drawing layer(s) to display on the camera view. |

### cameraEnhancer

Sets the [`CameraEnhancer`](camera-enhancer.md) instance that the `CameraView` is attached to. The `CameraEnhancer` is responsible for the core camera operations, and so **this property must be defined when constructing the CameraView**.

```dart
final CameraEnhancer cameraEnhancer;
```

### cameraToggleButton

Defines a custom widget (as a `CameraToggleButton` object) to replace the default camera toggle button (to switch between the front and back cameras).

```dart
final CameraToggleButton? cameraToggleButton;
```

**Remarks**

If provided, this widget will be used instead of the default camera toggle button. You must ensure that the custom widget handles the camera switch operation appropriately.

### cameraToggleButtonVisible

Determines whether the camera toggle button (to switch between the front and back cameras) is visible.

```dart
final bool? cameraToggleButtonVisible;
```

**Remarks**

Default value is `false`.

### scanLaserVisible

Determines whether the scan laser will be visible in the scan region or not.

```dart
final bool? scanLaserVisible;
```

**Remarks**

Defaults to `true` if not specified.

### scanRegionMaskVisible

Establishes whether the scan region (if defined via the `CameraEnhancer`) will be represented visually using a mask. The mask highlights the area where the barcode scanning occurs, and it defaults to `true` if not specified.

```dart
final bool? scanRegionMaskVisible;
```

**Remarks**

To learn how to limit the scan region, please visit this [section of the foundational user guide](../../foundational-user-guide.md#specify-the-scan-region). Defaults to `true` if not specified.

### torchButtonVisible

Controls the visibility of the torch/flash button that allows the user to activate the flash in low brightness scenarios.

```dart
final bool? torchButtonVisible;
```

**Remarks**

If no custom torch button is defined, the default torch icon will show up on the UI. Defaults to `true` if not specified.

### torchButton

Defines a custom [`TorchButton`](torch-button.md) instead of the default torch icon that comes with the camera view. This property allows you to customize the size, position, and icon images of the torch button.

```dart
final TorchButton? torchButton;
```

### visibleLayerIds

Defines which drawing layer(s) to display on the camera view. The drawing layer is responsible for highlighting the captured result, so in the case of the Barcode Reader, the drawing layer would highlight any recognized barcodes.

```dart
final List<EnumDrawingLayerId>? visibleLayerIds;
```

**Remarks**

The Capture Vision library can work with multiple functional products, including the Barcode Reader, Label Recognizer, and the Document Normalizer. If you would like to disable the feature to highlight any found barcodes, then the visibleLayerIds must not include `EnumDrawingLayerId.dbr`.

## Code Snippet

```dart
@override
Widget build(BuildContext context) {
return Scaffold(
    appBar: AppBar(backgroundColor: Theme.of(context).colorScheme.inversePrimary, title: Text(widget.title)),
    body: Center(child: CameraView(
        cameraEnhancer: _camera, 
        torchButtonVisible: true, 
        scanRegionMaskVisible: false, 
        scanLaserVisible: true, 
        torchButton: _torch, 
        visibleLayerIds: [EnumDrawingLayerId.dbr])
    ),
);
```