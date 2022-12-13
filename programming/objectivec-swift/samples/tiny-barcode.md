---
layout: default-layout
title: TinyBarcodeDecoding Sample - Dynamsoft Barcode Reader for iOS
description: This is the tiny barcode decoding sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: android, samples, tiny barcode
needAutoGenerateSidebar: false
breadcrumbText: TinyBarcodeDecoding
permalink: /programming/android/samples/tiny-barcode.html
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

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Include DynamsoftCameraEnhancer library and initialize an instance of DCE
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
...
@property (nonatomic, strong) DynamsoftCameraEnhancer *dce;
@property (nonatomic, strong) DCECameraView *dceView;
...
- (void)configurationDCE{
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubView:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   // Enable the auto-zoom feature
   [_dce setZoom:3.0f];
}
```
2. 
```swift
import DynamsoftCameraEnhancer
var dce:DynamsoftCameraEnhancer! = nil
var dceView:DCECameraView! = nil
func configurationDCE() {
   dceView = DCECameraView.init(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = DynamsoftCameraEnhancer.init(view: dceView)
   dce.setZoom(3.0)
}
```

### Enable Auto-zoom

Auto-zoom is another way for you to change the zoom factor. When the auto-zoom feature is enabled, the camera will zoom-in automatically when a barcode is located be not decoded. The auto-zoom-out will be triggered when barcode is decoded successfully.

<div align="center">
    <p><img src="../../assets/auto-zoom.gif" width="30%" alt="auto-zoom"></p>
    <p>Close-up vs camera zoom. The focus is much easier when using camera zoom.</p>
</div>

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Include DynamsoftCameraEnhancer library and initialize an instance of DCE
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
...
@property (nonatomic, strong) DynamsoftCameraEnhancer *dce;
@property (nonatomic, strong) DCECameraView *dceView;
...
- (void)configurationDCE{
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubView:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   // Enable the auto-zoom feature
   [_dce enableFeatures:EnumAUTO_ZOOM error: &error];
}
```
2. 
```swift
// Include DynamsoftCameraEnhancer library and initialize an instance of DCE
import DynamsoftCameraEnhancer
...
var dce:DynamsoftCameraEnhancer! = nil
var dceView:DCECameraView! = nil
...
func configurationDCE() {
   dceView = DCECameraView.init(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = DynamsoftCameraEnhancer.init(view: dceView)
   dce.enableFeatures(EnumEnhancerFeature.EnumAUTO_ZOOM.rawValue, error: &error)
}
```

> Note: A valid license is required to use auto-zoom feature.

## Focus Control

Select a suitable focus mode can help you further improve the read-rate and accuracy when processing small-size barcodes.

When your device is stable, you can lock the focal length after focusing is complete.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Include DynamsoftCameraEnhancer library and initialize an instance of DCE
#import <DynamsoftCameraEnhancer/DynamsoftCameraEnhancer.h>
...
@property (nonatomic, strong) DynamsoftCameraEnhancer *dce;
@property (nonatomic, strong) DCECameraView *dceView;
...
- (void)configurationDCE{
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubView:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   // Enable the auto-zoom feature
   CGPoint focusPoint = {0.5, 0.5};
   [_dce setFocus:focusPoint subsequentFocusMode:EnumFocusMode.FM_LOCKED];
}
```
2. 
```swift
// Include DynamsoftCameraEnhancer library and initialize an instance of DCE
import DynamsoftCameraEnhancer
...
var dce:DynamsoftCameraEnhancer! = nil
var dceView:DCECameraView! = nil
...
func configurationDCE() {
   dceView = DCECameraView.init(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = DynamsoftCameraEnhancer.init(view: dceView)
   let focusPoint = CGPoint(x:0.5, y:0.5)
   dce.setFocus(focusPoint, subsequentFocusMode:EnumFocusMode.FM_LOCKEDD)
}
```

If your device is not stable, you can replace the last line with the following code to keep the continuous auto focus mode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_dce setFocus:focusPoint subsequentFocusMode:EnumFocusMode.FM_CONTINUOUS_AUTO];
```
2. 
```swift
dce.setFocus(focusPoint, subsequentFocusMode:EnumFocusMode.FM_CONTINUOUS_AUTO)
```

## Scale-up Mode

When processing a still image, you don't have the opportunity to optimize the quality of the image. For this scenario, if you are processing a small-sized barcode, the [`ScaleUpMode`]({{site.parameters_reference}}scale-up-modes.html) might help you to read barcode.

The following Code Snippet shows you how to set the `ScaleUpMode`:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError* err = nil;
iPublicRuntimeSettings* settings = [reader getRuntimeSettings:&err];
settings.scaleUpModes.grayscaleTransformationModes = @[@(EnumScaleUpModeLinearInterpolation),@(EnumScaleUpModeNeighbourInterpolation)];
[reader updateRuntimeSettings:settings error:&err];
```
2. 
```swift
let settings = try? barcodeReader.getRuntimeSettings()
settings?.scaleUpModes = [EnumScaleUpMode.linearInterpolation.original.rawValue, EnumScaleUpMode.neighbourInterpolation.rawValue]
try? barcodeReader.updateRuntimeSettings(settings!)
```

For more introductions about scale up mode, please read more in the [Parameter-ScaleUpModes]({{site.parameters_reference}}scale-up-modes.html) page.

View the sample

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/Usecase/TinyBarcode" target="_blank">TinyBarcodeDecoding Swift Sample</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/Usecase/TinyBarcode" target="_blank">TinyBarcodeDecoding Objective-C Sample</a>
