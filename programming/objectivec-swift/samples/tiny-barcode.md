---
layout: default-layout
title: TinyBarcodeDecoding Sample - Dynamsoft Barcode Reader for iOS
description: This is the tiny barcode decoding sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: android, samples, tiny barcode
needAutoGenerateSidebar: true
breadcrumbText: TinyBarcodeDecoding
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/android/samples/tiny-barcode.html
---

# TinyBarcodeDecoding Sample

**View the sample**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/UseCase/TinyBarcodeDecoding" target="_blank">iOS (Swift) TinyBarcodeDecoding Sample</a>

When processing a small-sized barcode or a barcode that is localized far away, the following factors might cause the low performance:

- The module size of the barcode is too small.
- The image quality of the barcode zone is too low.

`TinyBarcodeDecoding` is the sample to tell you how Dynamsoft Barcode Reader is designed to process the tiny barcodes.

## Zoom Control

### Set the Zoom Factor

Generally, control the camera to zoom-in has better effect than approaching to the target because some device have difficulty on close-up focus.

<div align="center">
    <p><img src="../../assets/close-vs-zoom.png" width="30%" alt="close-vs-zoom"></p>
    <p>Close-up vs camera zoom. The focus is much easier when using camera zoom.</p>
</div>

Here is the sample code to enlarge the zoom factor:

```swift
import DynamsoftCameraEnhancer
var dce:CameraEnhancer! = nil
var dceView:CameraView! = nil
func configurationDCE() {
   dceView = CameraView(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = CameraEnhancer.init(view: dceView)
   dce.setZoom(3.0)
}
```

### Enable Auto-zoom

Auto-zoom is another way for you to change the zoom factor. When the auto-zoom feature is enabled, the camera will zoom-in automatically when a barcode is located be not decoded. The auto-zoom-out will be triggered when barcode is decoded successfully.

<div align="center">
    <p><img src="../../assets/auto-zoom.gif" width="30%" alt="auto-zoom"></p>
    <p>Close-up vs camera zoom. The focus is much easier when using camera zoom.</p>
</div>

```swift
// Include DynamsoftCameraEnhancer library and initialize an instance of DCE
import DynamsoftCameraEnhancer
...
var dce:CameraEnhancer! = nil
var dceView:CameraView! = nil
...
func configurationDCE() {
   dceView = CameraView(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = CameraEnhancer.init(view: dceView)
   dce.enableEnhancedFeatures(.autoZoom)
}
```

> Note: A valid license is required to use auto-zoom feature.

## Focus Control

Select a suitable focus mode can help you further improve the read-rate and accuracy when processing small-size barcodes.

When your device is stable, you can lock the focal length after focusing is complete.

```swift
// Include DynamsoftCameraEnhancer library and initialize an instance of DCE
import DynamsoftCameraEnhancer
...
var dce:CameraEnhancer! = nil
var dceView:CameraView! = nil
...
func configurationDCE() {
   dceView = CameraView(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = CameraEnhancer(view: dceView)
   let focusPoint = CGPoint(x:0.5, y:0.5)
   dce.setFocus(focusPoint, subsequentFocusMode:EnumFocusMode.FM_LOCKEDD)
}
```

If your device is not stable, you can replace the last line with the following code to keep the continuous auto focus mode.

```swift
dce.setFocus(focusPoint, subsequentFocusMode:EnumFocusMode.FM_CONTINUOUS_AUTO)
```
