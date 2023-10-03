---
layout: default-layout
title: TinyBarcodeDecoding Sample - Dynamsoft Barcode Reader for Android
description: This is the tiny barcode decoding sample page of Dynamsoft Barcode Reader for Android SDK.
keywords: android, samples, tiny barcode
needAutoGenerateSidebar: true
breadcrumbText: TinyBarcodeDecoding
permalink: /programming/android/samples/tiny-barcode-v9.6.20.html
---

# TinyBarcodeDecoding Sample

When processing a small-sized barcode or a barcode that is localized far away, the following factors might cause the low performance:

- The module size of the barcode is too small.
- The image quality of the barcode zone is too low.

`TinyBarcodeDecodingSample` is the sample to tell you how Dynamsoft Barcode Reader is designed to process the tiny barcodes.

## Zoom Control

### Set the Zoom Factor

Generally, control the camera to zoom-in has better effect than apporaching to the target because some device have difficulty on close-up focus.

<div align="center">
    <p><img src="../../assets/close-vs-zoom.png" width="30%" alt="close-vs-zoom"></p>
    <p>Close-up vs camera zoom. The focus is much easier when using camera zoom.</p>
</div>

Here is the sample code to enlarge the zoom factor:

```java
// Import Camera Enhancer library to use the camera control module.
import com.dynamsoft.dce.CameraEnhancer;
CameraEnhancer camera = new CameraEnhancer(MainActivity.this);
// Set the zoom factor to 2 times of the initial zoom factor.
try {
   mCameraEnhancer.setZoom(2.0f);
} catch (CameraEnhancerException e) {
   e.printStackTrace();
}
```

### Enable Auto-zoom

Auto-zoom is another way for you to change the zoom factor. When the auto-zoom feature is enabled, the camera will zoom-in automatically when a barcode is located be not decoded. The auto-zoom-out will be triggered when barcode is decoded successfully.

<div align="center">
    <p><img src="../../assets/auto-zoom.gif" width="30%" alt="auto-zoom"></p>
    <p>Close-up vs camera zoom. The focus is much easier when using camera zoom.</p>
</div>

```java
// Import Camera Enhancer library to use the camera control module.
import com.dynamsoft.dce.CameraEnhancer;
CameraEnhancer camera = new CameraEnhancer(MainActivity.this);
try {
   // Enable auto-zoom feature
   mCameraEnhancer.enableFeatures(EnumEnhancerFeatures.EF_AUTO_ZOOM);
} catch (CameraEnhancerException e) {
   e.printStackTrace();
}
```

> Note: A valid license is required to use auto-zoom feature.

## Focus Control

Select a suitable focus mode can help you further improve the read-rate and accuracy when processing small-size barcodes.

When your device is stable, you can lock the focal length after focusing is complete.

```java
camera.setFocus(new PointF(0.5,0.5), EnumFocusMode.FM_LOCKED);
```

If your device is not stable, you can replace the last line with the following code to keep the continuous auto focus mode.

```java
camera.setFocus(new PointF(0.5,0.5), EnumFocusMode.FM_CONTINUOUS_AUTO);
```

## Scale-up Mode

When processing a still image, you don't have the opportunity to optimize the quality of the image. For this scenario, if you are processing a small-sized barcode, the [`ScaleUpMode`]({{site.parameters_reference}}scale-up-modes.html) might help you to read barcode.

The following Code Snippet shows you how to set the `ScaleUpMode`:

```java
try {
   BarcodeReader barcodeReader = new BarcodeReader();
   PublicRuntimeSettings settings = barcodeReader.getRuntimeSettings();
   settings.scaleUpModes = new int[]{EnumScaleUpMode.SUM_LINEAR_INTERPOLATION, EnumScaleUpMode.SUM_NEAREST_NEIGHBOUR_INTERPOLATION};
   barcodeReader.updateRuntimeSettings(settings);
} catch (BarcodeReaderException e) {
   e.printStackTrace();
}
```

For more introductions about scale up mode, please read more in the [Parameter-ScaleUpModes]({{site.parameters_reference}}scale-up-modes.html) page.

View the sample

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/android/Java/Usecase/TinyBarcode" target="_blank">Java (Android) TinyBarcodeDecoding Sample</a>
