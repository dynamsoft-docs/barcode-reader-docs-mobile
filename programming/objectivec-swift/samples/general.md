---
layout: default-layout
title: Dynamsoft Barcode Reader for iOS - General Settings Sample
description: This is the General Settings Sample page of Dynamsoft Barcode Reader for iOS SDK.
keywords: iOS, samples, General
needAutoGenerateSidebar: true
breadcrumbText: GeneralSettings
permalink: /programming/objectivec-swift/samples/general.html
---

# GeneralSettings Sample

This sample shows general barcode decoding settings and how to configure the settings when using Dynamsoft Barcode Reader iOS SDK. You can see the following settings in the sample:

- [Scan Mode](#scan-mode)
- [Barcode Format & Expected Barcode Count](#barcode-formats--expected-barcode-count)
- [Inverted Barcode Decoding](#inverted-barcode-decoding)
- [Minimum Decode Interval](#minimum-decode-interval)
- [Duplicate Filter](#duplicate-filter)
- [Minimum Result Confidence](#minimum-result-confidence)
- [Result Verification](#result-verification)
- [Scan Region](#scan-region)
- [Display of Overlay](#display-of-overlay)
- [Vibration & Beep](#vibration--beep)
- [Torch Control](#torch-control)

**View the Sample(s)**

- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Objective-C/GeneralSettingsObjC/" target="_blank">Objective-C General Settings Sample</a>
- <a href="https://github.com/Dynamsoft/barcode-reader-mobile-samples/tree/main/ios/Swift/GeneralSettingsSwift/" target="_blank">Swift General Settings Sample</a>

## Scan Mode

- Video Barcode Decoding
  - Continuous Scan: Decode the barcodes from the video streaming continuously.
  - One-off Scan: Stop scanning when a barcode is decoded from the video streaming.
- Image Barcode Decoding: Decode from an image file, a file in memory, a base64 string, a pixel buffer or a Bitmap.

The video barcode decoding of Dynamsoft Barcode Reader is designed to be continuous, which means once you triggered method `startScanning`, the video barcode decoding will not stop until you call method `stopScanning`. The **One-off Scan** mode of **GeneralSettings sample** is configured by triggering `stopScanning` when the barcode results are returned by `textResultCallback`.

## Barcode Formats & Expected Barcode Count

The barcode formats settings and the barcode count settings are the most basic settings that determine the readability of your scan app.

**Barcode Format**

- You can view the enumeration [`BarcodeFormat`](../../enumeration/barcode-format.md?lang=objc,swift) and [`BarcodeFormat_2`](../../enumeration/barcode-format2.md?lang=objc,swift) for all the supported barcode formats.
- You can view <a href="https://www.dynamsoft.com/barcode-reader/barcode-types/" target="_blank">this page</a> for the introductions of barcode formats.

**Expected Barcode Count**

Through this parameter, you can tell how many barcodes you want to decode from a single image in one scan. If the `expectedBarcodesCount` is not reached, the library will continue try its best to decode the barcodes with other image processing modes or barcode decoding modes.

How to set `expectedBarcodesCount`:

- If you know exactly how may barcodes exist on the image, set it to that value.
- If you don't know exactly how may barcodes exist on the image and **speed** is at the first pirority, set it to 0.
- If you don't know exactly how may barcodes exist on the image and **read-rate** is at the first pirority, set it to the maximum possible value like 999.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError* err = nil;
// Obtain current runtime settings.
iPublicRuntimeSettings* settings = [reader getRuntimeSettings:&err];
// Set the barcode format.
settings.barcodeFormatIds = EnumBarcodeFormatQRCODE | EnumBarcodeFormatONED;
settings.barcodeFormatIds_2 = EnumBarcodeFormat2POSTALCODE;
// Set the expected barcodes count.
settings.expectedBarcodesCount = 0;
// Update the settings.
[reader updateRuntimeSettings:settings error:&err];
```
2. 
```swift
// Obtain current runtime settings.
let settings = try? barcodeReader.getRuntimeSettings()
// Set the barcode format.
// The majority of popular barcodes exist in the first group of barcode format.
settings?.barcodeFormatIds = EnumBarcodeFormat.ONED | EnumBarcodeFormat.QRCODE
settings?.barcodeFormatIds_2 = EnumBarcodeFormat2.POSTALCODE
// Set the expected barcode count.
settings.expectedBarcodesCount = 0
// Update the settings.
try? barcodeReader.updateRuntimeSettings(settings!)
```

## Inverted Barcode Decoding

If you are working with inverted barcodes, `GrayscaleTransformationModes` is the parameter to deal with them.

<div align="center">
    <p><img src="../../assets/inverted-barcode.png" width="20%" alt="invert"></p>
    <p>Inverted Barcode</p>
</div>

The candidate modes are:

- `GTM_ORIGINAL`: Decode original coloured barcode.
- `GTM_INVERTED`: Decode inverted barcode.

There are 2 ways for you to configure the algorithm parameters. You can either upload the parameter from `PublicRuntimeSettings` or include it in the JSON template.

### Update PublicRuntimeSettings

The following code snippet shows how to configure `GrayscaleTransformationModes` via the `PublicRuntimeSettings`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError* err = nil;
// Obtain current runtime settings.
iPublicRuntimeSettings* settings = [reader getRuntimeSettings:&err];
// Add GTM_INVERTED to GrayscaleTransformationModes to decode inverted barcodes.
settings.furtherModes.grayscaleTransformationModes = @[@(EnumGrayscaleTransformationModeOriginal),@(EnumGrayscaleTransformationModeInverted)];
// Update the settings.
[reader updateRuntimeSettings:settings error:&err];
```
2. 
```swift
// Obtain current runtime settings.
let settings = try? barcodeReader.getRuntimeSettings()
// Add GTM_INVERTED to GrayscaleTransformationModes to decode inverted barcodes.
settings?.furtherModes.grayscaleTransformationModes = [EnumGrayscaleTransformationMode.original, EnumGrayscaleTransformationMode.inverted]
// Update the settings.
try? barcodeReader.updateRuntimeSettings(settings!)
```

The array `[EnumGrayscaleTransformationMode.original, EnumGrayscaleTransformationMode.inverted]` means:

In the first round of processing, the library will try to decode barcodes with original colour mode, which is specified in the first priority of the parameter array. If the count of decoded barcode doesn't reach the number of `expectedBarcodeCount`, the library will start another round of processing. The second round the library will focus on recognizing the inverted barcodes, which is specified in the second priority of the parameter array.

### Upload JSON Template

To upload the GrayscaleTransformationModes settings via a JSON template, you have to include the following snippet in your JSON template:

```json
{
   "ImageParameter": {
      "Name": "ImageParameter1",
      ...
      // You have to include the following parts.
      "GrayscaleTransformationModes": [
         {
            "Mode": "GTM_ORIGINAL"
         },
         {
            "Mode": "GTM_INVERTED" 
         }
      ],
      ...
   }
}
```

You can read <a href="https://www.dynamsoft.com/barcode-reader/docs/core/parameters/structure-and-interfaces-of-parameters.html?ver=latest" target="_blank"> template structure</a> to learn more about how to configure the JSON template.

The follow code snippets shows how to upload the JSON template:

**Upload JSON template as a String**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString* json = @"{\"ImageParameter\":{\"Name\":\"ImageParameter1\",\"GrayscaleTransformationModes\":[{\"Mode\":\"GTM_ORIGINAL\"},{\"Mode\":\"GTM_INVERTED\"}]}}";
[_barcodeReader initRuntimeSettingsWithString:json conflictMode:EnumConflictModeOverwrite error:nil];
```
2. 
```swift
let json = "{\"ImageParameter\":{\"Name\":\"ImageParameter1\",\"GrayscaleTransformationModes\":[{\"Mode\":\"GTM_ORIGINAL\"},{\"Mode\":\"GTM_INVERTED\"}]}}"
try? barcodeReader.initRuntimeSettingsWithString(json, conflictMode: .overwrite)
```

**Upload JSON template as a File**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// The method will overwrite the settings if the settings already exist.
[barcodeReader initRuntimeSettingsWithFile:@"your template file path" conflictMode:EnumConflictModeOverwrite error:nil];
```
2. 
```swift
// The method will overwrite the settings if the settings already exist.
try? barcodeReader.initRuntimeSettingsWithFile("your template file path", conflictMode:EnumConflictMode.overwrite)
```

## Minimum Decode Interval

Property `minImageDecodingInterval` is an optional setting of video streaming barcode decoding when the scan mode is **continuous scan**. Generally, Dynamsoft Barcode Reader is able to process 15 to 30 frames per second when the video streaming resolution is 1080P. For some scenarios, you might use the continuous scan mode but don't need the performance to be that high. This feature can help you to reduce the battery consumption.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_barcodeReader setMinImageDecodingInterval:500];
```
2. 
```swift
barcodeReader.minImageDecodingInterval = 500
```

## Duplicate Filter

Property `enableDuplicateFilter` and `duplicateForgetTime` are optional settings of video streaming barcode decoding when the scan mode is **continuous scan**. As we mentioned above, Dynamsoft Barcode Reader can process the video streaming at a very high speed. When scanning a single item, the library returns multiple results with the same value when the barcode appears under the camera. For example, when scanning shopping items in a supermarket, you need only one result for each scan. The `duplicateFilter` feature enable the device to output only one result even if the same barcode is scanned more than once in a short period. As a result you can count each item only once under the **continuous scan** mode by configuring the `duplicateFilter` and `duplicateForgetTime`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_barcodeReader setDuplicateForgetTime:1000];
[_barcodeReader setEnableDuplicateFilter:true];
```
2. 
```swift
barcodeReader.duplicateForgetTime = 1000
barcodeReader.enableDuplicateFilter = true
```

## Minimum Result Confidence

Each barcode result has a `confidence`. It indicates the confidence level for a barcode result to be correct. Dynamsoft Barcode Reader algorithm is designed to separate the highly reliable results and unreliable results by confidence 30, which is set as the default value of `minResultConfidence`. You can either increase the `minResultConfidence` to get even more accuracy results or decrease the `minResultConfidence` to try decoding the badly printed barcodes. You can either set the `minResultConfidence` via `PublicRuntimeSettings` or include it in the JSON template.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSError* err = nil;
// Obtain current runtime settings.
iPublicRuntimeSettings* settings = [reader getRuntimeSettings:&err];
// Change the value of minResultConfidence.
settings.minResultConfidence = 50;
// Update the settings.
[reader updateRuntimeSettings:settings error:&err];
```
2. 
```swift
// Obtain current runtime settings.
let settings = try? barcodeReader.getRuntimeSettings()
// Change the value of minResultConfidence.
settings?.minResultConfidence = 50
// Update the settings.
try? barcodeReader.updateRuntimeSettings(settings!)
```

## Result Verification

Enable `ResultVarification` feature to improve the accuracy at the expense of a bit speed. You can enable the result verification feature by configuring the property `enableResultVerification`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
[_barcodeReader setEnableResultVerification:true];
```
2. 
```swift
barcodeReader.enableResultVerification = true
```

## Scan Region

For video barcode decoding scenarios, specifying a **scanRegion** can reduce the size of the processing area, which sharply increases the barcode decoding speed. To specify the scan region, you can use the **CameraEnhancer** method <a href="https://www.dynamsoft.com/camera-enhancer/docs/programming/ios/primary-api/camera-enhancer.html?ver=latest#setscanregion" target="_blank">`setScanRegion`</a>. When the **scanRegion** is configured via **CameraEnhancer**, the video frames will be cropped based on the **scanRegion** before being processed by the barcode reader.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Initialize the Camera Enhancer and the camera view.
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
- (void)configurationDCE{
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubview:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   iRegionDefinition* scanRegion = [[iRegionDefinition alloc] init];
   scanRegion.regionTop = 25;
   scanRegion.regionBottom = 75;
   scanRegion.regionLeft = 25;
   scanRegion.regionRight = 75;
   scanRegion.regionMeasuredByPercentage = 1
   [_dce setScanRegion:scanRegion error: &error];
}
```
2. 
```swift
var dce:DynamsoftCameraEnhancer! = nil
var dceView:DCECameraView! = nil
func configurationDCE() {
   dceView = DCECameraView.init(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = DynamsoftCameraEnhancer.init(view: dceView)
   let scanRegion = iRegionDefinition()
   scanRegion.regionTop = 25
   scanRegion.regionBottom = 75
   scanRegion.regionLeft = 25
   scanRegion.regionRight = 75
   scanRegion.regionMeasuredByPercentage = 1
   dce.setScanRegion(scanRegion, error: &error)
}
```

## Display of Overlay

Display a highlighted overlay on the location that a barcode is decoded.

> Note: This feature is only available when using video streaming barcode decoding and the video source must be set to `DynamsoftCameraEnhancer`.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Initialize the Camera Enhancer and the camera view.
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
- (void)configurationDCE{
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubview:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   // Display the overlay
   [_dceView setOverlayVisible:true];
}
```
2. 
```swift
var dce:DynamsoftCameraEnhancer! = nil
var dceView:DCECameraView! = nil
func configurationDCE() {
   dceView = DCECameraView.init(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = DynamsoftCameraEnhancer.init(view: dceView)
   // Display the overlay
   dceView.overlayVisible = true
}
```

## Vibration & Beep

Trigger a beep or vibration. If you call them in the `textResultCallback`, the device will trigger beep and vibration each time when a barcode is decoded.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (void)textResultCallback:(NSInteger)frameId imageData:(iImageData *)imageData results:(NSArray<iTextResult *> *)results{
   ...
   [DCEFeedback beep];
   [DCEFeedback vibrate];
   ...
}
```
2. 
```swift
func textResultCallback(_ frameId: Int, imageData: iImageData, results: [iTextResult]?){
   ...
   DCEFeedback.beep()
   DCEFeedback.vibrate()
   ...
}
```

## Torch Control

You can turn on the torch when processing the barcode in a dark environment. There are 3 ways for you to turn on the torch:

- Trigger `turnOnTorch` method.
- Add a `torchButton` on the view. Click the button to turn On the torch.
- Enable **smart torch** feature. When the environment light is dark, a torch button will appear on the camera view. You can click the button to turn on the torch.

Code snippet for triggering the `turnOnTorch` method:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Initialize the Camera Enhancer and the camera view.
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
- (void)configurationDCE{
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubview:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   // Trigger turnOnTorch method
   [_dce turnOnTorch];
}
```
2. 
```swift
var dce:DynamsoftCameraEnhancer! = nil
var dceView:DCECameraView! = nil
func configurationDCE() {
   dceView = DCECameraView.init(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = DynamsoftCameraEnhancer.init(view: dceView)
   dceView.turnOnTorch()
}
```

Code snippet for adding a `torchButton`:

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Initialize the Camera Enhancer and the camera view.
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
- (void)configurationDCE{
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubview:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   // Add a torch button
   CGRect rect = {0, 0, 30, 30};
   [_dceView setTorchButton:(rect) torchOnImage: image torchOffImage: image];
}
```
2. 
```swift
var dce:DynamsoftCameraEnhancer! = nil
var dceView:DCECameraView! = nil
func configurationDCE() {
   dceView = DCECameraView.init(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = DynamsoftCameraEnhancer.init(view: dceView)
   // Add a torch button
   dceView.setTorchButton(CGRect.init(x: 0, y: 0, width: 500, height: 500), torchOnImage: image, torchOffImage:image)
}
```

Enable **smart torch**. If you have configured a `torchButton`, the `torchButton` you configured will become a **smart torch**.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
// Initialize the Camera Enhancer with the camera view.
@property(nonatomic, strong) DynamsoftCameraEnhancer *dce;
- (void)configurationDCE{
   _dceView = [DCECameraView cameraWithFrame:self.view.bounds];
   [self.view addSubview:_dceView];
   _dce = [[DynamsoftCameraEnhancer alloc] initWithView:_dceView];
   // Enable smart torch feature.
   [_dce enableFeatures:EnumSMART_TORCH error: &error];
}
```
2. 
```swift
var dce:DynamsoftCameraEnhancer! = nil
var dceView:DCECameraView! = nil
func configurationDCE() {
   dceView = DCECameraView.init(frame: self.view.bounds)
   self.view.addSubview(dceView)
   dce = DynamsoftCameraEnhancer.init(view: dceView)
   // Enable smart torch feature.
   dce.enableFeatures(EnumEnhancerFeature.EnumSMART_TORCH.rawValue, error: &error)
}
```
