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

Use the [`setScanRegion`]({{ site.dce_flutter_api }}camera-enhancer.html#setscanregion) method to limit the scan area:

```js
let scanRegion = {
  top: 0.35,
  bottom: 0.65,
  left: 0.15,
  right: 0.85,
  measuredInPercentage: true
}
camera.setScanRegion(scanRegion);
```

The scan region is displayed with a mask by default. To hide it, set [`scanRegionMaskVisible`]({{ site.dce_flutter_api }}camera-view.html#scanregionmaskvisible) to `false`.

## Customizing the Camera View

Customizable UI elements on the CameraView include:

- `cameraToggleButton`: A button for switching between front and back facing cameras.
- `scanLaser`: A vertical laser that moves within the scan region.
- `scanRegionMask`: A mask covered outside the scan region.
- `torchButton`: A button for switching on and off the torch.

**Code Snippet**

```js
<SafeAreaView style={StyleSheet.absoluteFill}>
  <CameraView 
    style={StyleSheet.absoluteFill} 
    ref={cameraView}
    // Add a camera toggle button with default position and image.
    cameraToggleButtonVisible={true}
    // Display the scan laser.
    scanLaserVisible={true}
    // Scan region mask is displayed by default if you set a scan region.
    scanRegionMaskVisible={true}
    // Add a torch button with default position and image.
    torchButtonVisible={true}
  />
</SafeAreaView>
```
