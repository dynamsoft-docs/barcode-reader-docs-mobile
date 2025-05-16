---
layout: default-layout
title: General Settings Sample - Dynamsoft Barcode Reader for iOS
description: This is the General Settings Sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOS, samples, General
needAutoGenerateSidebar: true
breadcrumbText: GeneralSettings
permalink: /programming/objectivec-swift/samples/general.html
ignore: true
---

# GeneralSettings Sample

**View the sample code**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/v10.4.2002/ios/GeneralSettings" target="_blank">iOS (Swift) General Settings Sample</a>

This sample shows general barcode decoding settings and how to configure the settings when using Dynamsoft Barcode Reader iOS SDK. You can see the following settings in the sample:

- [GeneralSettings Sample](#generalsettings-sample)
  - [Scan Mode](#scan-mode)
  - [Barcode Formats \& Expected Barcode Count](#barcode-formats--expected-barcode-count)
  - [Inverted Barcode Decoding](#inverted-barcode-decoding)
  - [Minimum Image Capture Interval](#minimum-image-capture-interval)
  - [Minimum Result Confidence](#minimum-result-confidence)
  - [Barcode Text RegEx Pattern](#barcode-text-regex-pattern)
  - [Result Deduplication](#result-deduplication)
  - [Result Cross Verification](#result-cross-verification)
  - [Scan Region](#scan-region)
  - [Highlight Decoded Barcodes](#highlight-decoded-barcodes)
  - [Vibration \& Beep](#vibration--beep)
  - [Torch Control](#torch-control)

## Scan Mode

- Continuous Scan: Decode the barcodes from the video streaming continuously.
- One-off Scan: Stop scanning when a barcode is decoded from the video streaming.

The video barcode decoding of Dynamsoft Barcode Reader is designed to be continuous, which means once you triggered method `startCapturing`, the video barcode decoding will not stop until you call method `stopCapturing`. The **One-off Scan** mode of **GeneralSettings sample** is configured by triggering `stopCapturing` when the barcode results are returned by `onDecodedBarcodesReceived`.

## Barcode Formats & Expected Barcode Count

The barcode formats settings and the barcode count settings are the most basic settings that determine the readability of your scan app.

**Barcode Format**

- You can view the enumeration [`BarcodeFormat`]({{ site.dcvb_ios_api }}core/enum//barcode-format.html?lang=objc,swift) for all the supported barcode formats.
- You can view <a href="https://www.dynamsoft.com/barcode-reader/barcode-types/" target="_blank">this page</a> for the introductions of barcode formats.

**Expected Barcode Count**

Through this parameter, you can tell how many barcodes you want to decode from a single image in one scan. If the `expectedBarcodesCount` is not reached, the library will continue try its best to decode the barcodes with other image processing modes or barcode decoding modes.

How to set `expectedBarcodesCount`:

- If you know exactly how may barcodes exist on the image, set it to that value.
- If you don't know exactly how may barcodes exist on the image and **speed** is at the first priority, set it to 0.
- If you don't know exactly how may barcodes exist on the image and **read-rate** is at the first priority, set it to the maximum possible value like 999.

```swift
do{
   // mRouter is an instance of 'CaptureVisionRouter' class
   let settings = try mRouter.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   // Set the barcode format.
   settings.barcodeSettings.barcodeFormatIds = BarcodeFormat(rawValue: BarcodeFormat.oneD.rawValue | BarcodeFormat.qrCode.rawValue)
   // Set the expected barcode count.
   settings.barcodeSettings.expectedBarcodesCount = 5
   try mRouter.updateSettings(PresetTemplate.readBarcodes.rawValue, settings)
}catch{
   // Add your code to deal with exceptions
}
```

## Inverted Barcode Decoding

If you are working with inverted barcodes, `GrayscaleTransformationModes` is the parameter to deal with them.

<div align="center">
    <p><img src="../../assets/inverted-barcode.png" width="20%" alt="invert"></p>
    <p>Inverted Barcode</p>
</div>

The candidate modes are:

- `GTM_ORIGINAL`: Decode original colour barcode.
- `GTM_INVERTED`: Decode inverted barcode.

The following code snippet shows how to configure `GrayscaleTransformationModes` via the `SimplifiedCaptureVisionSettings`.

```swift
do{
   // mRouter is an instance of 'CaptureVisionRouter' class
   let settings = try mRouter.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   settings.barcodeSettings.grayscaleTransformationModes = [EnumGrayscaleTransformationMode.original, EnumGrayscaleTransformationMode.inverted]
   try mRouter.updateSettings(PresetTemplate.readBarcodes.rawValue, settings)
}catch{
   // Add your code to deal with exceptions
}
```

The array `[EnumGrayscaleTransformationMode.original, EnumGrayscaleTransformationMode.inverted]` means:

In the first round of processing, the library will try to decode barcodes with original colour mode, which is specified in the first priority of the parameter array. If the count of decoded barcode doesn't reach the number of `expectedBarcodeCount`, the library will start another round of processing. The second round the library will focus on recognizing the inverted barcodes, which is specified in the second priority of the parameter array.

## Minimum Image Capture Interval

Property `minImageCaptureInterval` is an optional setting of video streaming barcode decoding when the scan mode is **continuous scan**. Generally, Dynamsoft Barcode Reader is able to process 15 to 30 frames per second when the video streaming resolution is 1080P. For some scenarios, you might use the continuous scan mode but don't need the performance to be that high. This feature can help you to reduce the battery consumption.

```swift
do{
   // mRouter is an instance of 'CaptureVisionRouter' class
   let settings = try mRouter.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   settings.minImageCaptureInterval = 500
   try mRouter.updateSettings(PresetTemplate.readBarcodes.rawValue, settings)
}catch{
   // Add your code to deal with exceptions
}
```

## Minimum Result Confidence

Each barcode result has a `confidence`. It indicates the confidence level for a barcode result to be correct. Dynamsoft Barcode Reader algorithm is designed to separate the highly reliable results and unreliable results by confidence 30, which is set as the default value of `minResultConfidence`. You can either increase the `minResultConfidence` to get even more accuracy results or decrease the `minResultConfidence` to try decoding the badly printed barcodes.

```swift
do{
   // mRouter is an instance of 'CaptureVisionRouter' class
   let settings = try mRouter.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   settings.barcodeSettings.minResultConfidence = 50
   try mRouter.updateSettings(PresetTemplate.readBarcodes.rawValue, settings)
}catch{
   // Add your code to deal with exceptions
}
```

## Barcode Text RegEx Pattern

Property `barcodeTextRegExPattern` is used during the barcode recognition process to obtain barcodes whose text matches a specific regular expression. Any barcodes that do not match this pattern will be ignored during the recognition process.

```swift
do{
   // mRouter is an instance of 'CaptureVisionRouter' class
   let settings = try mRouter.getSimplifiedSettings(PresetTemplate.readBarcodes.rawValue)
   settings.barcodeSettings.barcodeTextRegExPattern = "^[0-9]{10}$"
   try mRouter.updateSettings(PresetTemplate.readBarcodes.rawValue, settings)
}catch{
   // Add your code to deal with exceptions
}
```

## Result Deduplication

Result deduplication is an optional setting of video streaming barcode decoding when the scan mode is **continuous scan**. As we mentioned above, Dynamsoft Barcode Reader can process the video streaming at a very high speed. When scanning a single item, the library returns multiple results with the same value when the barcode appears under the camera. For example, when scanning shopping items in a supermarket, you need only one result for each scan. The `ResultDeduplication` and `DuplicateForgetTime` features enable the device to output only one result even if the same barcode is scanned more than once in a short period.

```swift
let resultCrossFilter = MultiFrameResultCrossFilter()
resultCrossFilter.enableResultDeduplication(.barcode, isEnabled: true)
resultCrossFilter.setDuplicateForgetTime(.barcode, duplicateForgetTime: 500)
// mRouter is an instance of 'CaptureVisionRouter' class
mRouter.addResultFilter(resultCrossFilter)
```

## Result Cross Verification

Enable `ResultCrossVarification` feature to improve the accuracy at the expense of a bit speed.

```swift
let resultCrossFilter = MultiFrameResultCrossFilter()
resultCrossFilter.enableResultCrossVerification(.barcode, isEnabled: true)
// mRouter is an instance of 'CaptureVisionRouter' class
mRouter.addResultFilter(resultCrossFilter)
```

## Scan Region

For video barcode decoding scenarios, specifying a **scanRegion** can reduce the size of the processing area, which sharply increases the barcode decoding speed. To specify the scan region, you can use the **CameraEnhancer** method <a href="https://www.dynamsoft.com/camera-enhancer/docs/mobile/programming/ios/primary-api/camera-enhancer.html#setscanregion" target="_blank">`setScanRegion`</a>. When the **scanRegion** is configured via **CameraEnhancer**, the video frames will be cropped based on the **scanRegion** before being processed by the barcode reader.

```swift
var dce:CameraEnhancer! = nil
var dceView:CameraView! = nil
func configurationDCE() {
   dceView = CameraView(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = CameraEnhancer(view: dceView)
   let scanRegion = Rect()
   scanRegion.top = 0.25
   scanRegion.bottom = 0.75
   scanRegion.left = 0.25
   scanRegion.right = 0.75
   scanRegion.measuredInPercentage = true
   try? dce.setScanRegion(scanRegion)
}
```

## Highlight Decoded Barcodes

Display a highlighted overlay on the location that a barcode is decoded.

> Note: This feature is only available when using video streaming barcode decoding and the input source must be set to `CameraEnhancer`.

```swift
var dce:CameraEnhancer! = nil
var dceView:CameraView! = nil
func configurationDCE() {
   dceView = CameraView(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = CameraEnhancer(view: dceView)
   let dbrDrawingLayer = dceView.getDrawingLayer(DrawingLayerId.DBR.rawValue)
   dbrDrawingLayer?.visible = true
}
```

## Vibration & Beep

Trigger a beep or vibration. If you call them in the `onDecodedBarcodesReceived`, the device will trigger beep and vibration each time when a barcode is decoded.

```swift
func onDecodedBarcodesReceived(_ result: DecodedBarcodesResult) {
   guard let items = result.items else {
      return
   }
      
   Feedback.vibrate()
   Feedback.beep()
}
```

## Torch Control

You can turn on the torch when processing the barcode in a dark environment. There are 3 ways for you to turn on the torch:

- Trigger `turnOnTorch` method.
- Add a `torchButton` on the view. Click the button to turn On the torch.
- Enable **smart torch** feature. When the environment light is dark, a torch button will appear on the camera view. You can click the button to turn on the torch.

Code snippet for triggering the `turnOnTorch` method:

```swift
var dce:CameraEnhancer! = nil
var dceView:CameraView! = nil
func configurationDCE() {
   dceView = CameraView(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = CameraEnhancer(view: dceView)
   dceView.turnOnTorch()
}
```

Code snippet for adding a `torchButton`:

```swift
var dce:CameraEnhancer! = nil
var dceView:CameraView! = nil
func configurationDCE() {
   dceView = CameraView(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = CameraEnhancer(view: dceView)
   // Add a torch button
   dceView.setTorchButton(CGRect.init(x: 0, y: 0, width: 500, height: 500), torchOnImage: image, torchOffImage:image)
}
```

Enable **smart torch**. If you have configured a `torchButton`, the `torchButton` you configured will become a **smart torch**.

```swift
var dce:CameraEnhancer! = nil
var dceView:CameraView! = nil
func configurationDCE() {
   dceView = CameraView(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = CameraEnhancer(view: dceView)
   // Enable smart torch feature.
   dce.enableEnhancedFeatures(.smartTorch)
}
```
