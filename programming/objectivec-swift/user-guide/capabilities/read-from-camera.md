---
layout: default-layout
title: Read from camera - Dynamsoft Barcode Reader iOS
description: Learn how to read barcodes from the camera using the Dynamsoft Barcode Reader iOS SDK.
keywords: user guide, read from camera, iOS, objective-c, swift
noTitleIndex: true
needGenerateH3Content: true
needAutoGenerateSidebar: true
---

# Read from camera

> [!Important]
> This page is for **Foundational APIs** only. Refer to [Quick Start](../../user-guide.md) for how to scan from camera with `BarcodeScanner` component.

Follow these three steps to read barcodes from the camera:

1. Set input
2. Register result receiver
3. Start capturing

## Set input

### CameraEnhancer - Dynamsoft Standard Camera Input 

1. Create a `CameraEnhancer` object and bind it to `CameraView`.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   DSCameraEnhancer *mCamera = [[DSCameraEnhancer alloc] init];
   DSCameraView *cameraView = [[DSCameraView alloc] initWithFrame:self.view.bounds];
   mCamera.cameraView = cameraView;
   ```
   2. 
   ```swift
   let mCamera = CameraEnhancer()
   let cameraView = CameraView(frame: self.view.bounds)
   mCamera.cameraView = cameraView
   ```

2. Use `CaptureVisionRouter.setInput` to set the `CameraEnhancer` object as the input source.

   <div class="sample-code-prefix"></div>
   >- Objective-C
   >- Swift
   >
   >1. 
   ```objc
   DSCaptureVisionRouter *mRouter = [[DSCaptureVisionRouter alloc] init];
   NSError *error = nil;
   [mRouter setInput:mCamera error:&error];
   ```
   2. 
   ```swift
   let mRouter = CaptureVisionRouter()
   try? mRouter.setInput(mCamera)
   ```

### Other Camera Input

> Note:
> If you are using CameraX, refer to the [`DecodeWithCameraX`](https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/FoundationalAPISamples/DecodeWithCameraX) sample for camera input integration.

To use another camera source, complete the following steps so the library can process the input:

1. Receive the camera input.
2. Convert the raw camera input to a `com.dynamsoft.core.basic_structures.ImageData` object.
3. Use `addImageToBuffer` to add the `ImageData` object to the buffer. 

## Result receiver

Use `CapturedResultReceiver` to receive capture results. The callback is triggered each time an image is processed, regardless of whether a barcode is decoded.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[mRouter addResultReceiver:self];
// Implement DSCapturedResultReceiver callback:
- (void)onDecodedBarcodesReceived:(DSDecodedBarcodesResult *)result {
}
```
2. 
```swift
mRouter.addResultReceiver(self)
// Implement CapturedResultReceiver callback:
func onDecodedBarcodesReceived(_ result: DecodedBarcodesResult) {
}
```

## Start capturing

Use `startCapturing` and `stopCapturing` to control when barcode decoding starts and stops.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[mRouter startCapturing:DSPresetTemplateReadBarcodes completionHandler:^(BOOL isSuccess, NSError * _Nullable error) {
}];
```
2. 
```swift
try? mRouter.startCapturing(PresetTemplate.readBarcodes.rawValue)
```
