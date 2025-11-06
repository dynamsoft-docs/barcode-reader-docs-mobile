---
layout: default-layout
title: UI Customization (Foundational Edition) - Dynamsoft Barcode Reader Flutter Edition
description: The UI customization guide for the foundational edition of Dynamsoft Barcode Reader Flutter.
keywords: ui, customization, foundational, Flutter, barcode reader
needAutoGenerateSidebar: true
noTitleIndex: true
---

# UI Customization Guide (Foundational Edition)

One of the advantages of using the foundational edition of the Barcode Reader is that you can customize the UI however you see fit. In this guide we will walk through some of the ways in which you can customize the scanner UI using the Barcode Reader Foundational API.

## Specifying a Scan Region

You can limit the scan region of the SDK so that **it doesn't exhaust resources trying to read from the entire image or frame**. In order to do this, we must use the [`setScanRegion`]({{ site.dce_flutter_api }}camera-enhancer.html#setscanregion) method of the `CameraEnhancer` class.

```dart
import 'package:dynamsoft_capture_vision_flutter/dynamsoft_capture_vision_flutter.dart';

final CameraEnhancer _camera = CameraEnhancer.instance;

void initSdk() async {
  //......
  await _cvr.setInput(_camera);
  final scanRegion = DSRect(left: 0.1, top: 0.4, right: 0.9, bottom: 0.6, measuredInPercentage: true);
  _camera.setScanRegion(scanRegion);
  _camera.open();
}
```

> [!TIP]
> It is recommended to have `measuredInPercentage` set to true to make the calculation process as easy as possible.

Once a scan region is set, the region will by default be represented visually using a scan region mask. To control the visibility of this mask, please set the [`scanRegionMaskVisible`]({{ site.dce_flutter_api }}camera-view.html#scanregionmaskvisible) property of the [`CameraView`]({{ site.dce_flutter_api }}camera-view.html) to `false`.

## Customizing the Camera View

One of the main advantages of using the Camera Enhancer component to control camera operations is that it comes with a camera view UI that is fully customizable.

The [`CameraView`]({{ site.dce_flutter_api }}camera-view.html) class comes with a few elements - namely a torch (flash) button, a scan region mask (if a scan region is set), a scan laser, and a drawing layer to highlight any detected barcodes.

### Customizing the Flash Button

The CameraView comes with its own default torch button that allows the user to toggle the camera's flash on or off. Through the [`CameraView`]({{ site.dce_flutter_api }}camera-view.html) and [`TorchButton`]({{ site.dce_flutter_api }}torch-button.html) classes, you can customize the appearance, size, and position of the torch button - as well as the visibility of the button.

In this next code snippet, we will demonstrate how you can create and assign a custom TorchButton - as well as show the full CameraView configuration.

> [!NOTE]
> The only required property that needs to be set in `CameraView` is the cameraEnhancer property. Any camera view component must be "attached" to a [`CameraEnhancer`]({{ site.dce_flutter_api }}camera-enhancer.html) instance.

```dart
...
final TorchButton _torch = TorchButton(
	location: Rect.fromLTWH(300, 30, 50, 50), // places the torch button towards the top-right corner of the camera view
	torchOffImageBase64: 'insert_base64_string_here',
	torchOnImageBase64: 'insert_base64_string_here'
);
...
@override
Widget build(BuildContext context) {
return Scaffold(
    appBar: AppBar(backgroundColor: Theme.of(context).colorScheme.inversePrimary, title: Text(widget.title)),
    body: Center(child: CameraView(
        cameraEnhancer: _camera, 
        torchButtonVisible: true, // displays the torch button in the camera view
        scanRegionMaskVisible: false, // hides the scan region mask so that the scan region is not represented visually
        scanLaserVisible: true, // displays the scan laser - which is a simple bar that moves vertically within the scan region
        torchButton: _torch, // assigns the custom torch button defined above to the camera view
        visibleLayerIds: [EnumDrawingLayerId.dbr] // displays highlight boxes around detected barcodes
        )
    ),
);
```