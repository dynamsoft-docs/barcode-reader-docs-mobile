---
layout: default-layout
title: BarcodeScannerConfig Class - Dynamsoft Barcode Reader iOS Edition
description: BarcodeScannerConfig of Dynamsoft Barcode Reader iOS is the class that defines the configurations for BarcodeScanner component.
keywords: scanner, activity, startCapturing, license 
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: BarcodeScannerConfig
---

# BarcodeScannerConfig

`BarcodeScannerConfig` is the class that defines the configurations for barcode scanning. Once the `BarcodeScannerConfig` object is made, it must be attached to the `BarcodeScannerViewController` object.

## Definition

*Assembly:* DynamsoftBarcodeReaderBundle.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSBarcodeScannerConfig : NSObject
```
2. 
```swift
class BarcodeScannerConfig : NSObject
```

## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| [`license`](#license) | *NSString \** | Sets or returns the license key for the Barcode Reader. |
| [`templateFile`](#templatefile) | *NSString \** | Sets or returns the template with a file path or a JSON string. |
| [`barcodeFormats`](#barcodeformats) | *DSBarcodeFormat* | Sets or returns the barcode format(s) to read. |
| [`scanRegion`](#scanregion) | *DSRect \** | Sets or returns the scan region where only the barcodes located in the scan region can be decoded. |
| [`isTorchButtonVisible`](#istorchbuttonvisible) | *BOOL* | Sets or returns whether or not the torch button is visible. |
| [`isBeepEnabled`](#isbeepenabled) | *BOOL* | Sets or returns whether the beep sound is enabled when a barcode is found. |
| [`isVibrateEnabled`](#isvibrateenabled) | *BOOL* | Sets or returns whether the vibration is enabled when a barcode is found. |
| [`isScanLaserVisible`](#isscanlaservisible) | *BOOL* | Sets or returns whether or not the scan laser is visible. |
| [`isAutoZoomEnabled`](#isautozoomenabled) | *BOOL* | Sets or returns whether or not the auto-zoom feature of the Camera Enhancer is enabled. |
| [`isCloseButtonVisible`](#isclosebuttonvisible) | *BOOL* | Sets or returns whether or not the close button is visible. |
| [`scanningMode`](#scanningmode) | *DSScanningMode* | Sets or returns the scanning mode. |
| [`maxConsecutiveStableFramesToExit`](#maxconsecutivestableframestoexit) | *int* | Sets or returns how long the library will keep scanning when there is no more barcodes to decode. |
| [`expectedBarcodesCount`](#expectedbarcodescount) | *NSIntger* | Sets or returns the expected number of barcodes. |
| [`isCameraToggleButtonVisible`](#iscameratogglebuttonvisible) | *BOOL* | Sets or returns whether or not the camera toggle button is visible. |
| [`zoomFactor`](#zoomfactor) | *BOOL* | Sets or returns the zoom factor. |

### license

Sets or returns the license key for the Barcode Reader.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) NSString* license;
```
2. 
```swift
var license: String { get set }
```

### templateFile

Sets or returns the template with a file path or a JSON string.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) NSString* templateFile;
```
2. 
```swift
var templateFile: String { get set }
```

### barcodeFormats

Sets or returns the barcode format(s) to read.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) DSBarcodeFormat barcodeFormats;
```
2. 
```swift
var barcodeFormats: BarcodeFormat { get set }
```

**See also**

- [DSBarcodeFormat]({{ site.dcvb_ios_api }}core/enum//barcode-format.html?lang=objc,swift)

### scanRegion

Sets or returns the scan region where only the barcodes located in the scan region can be decoded.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) DSRect* scanRegion;
```
2. 
```swift
var scanRegion: DSRect { get set }
```

**See also**

- [`DSRect`]({{ site.dcvb_ios_api }}core/basic-structures/rect.html)

### isTorchButtonVisible

Sets or returns a boolean indicating whether or not the torch button is visible. User can click the torch button to turn on/off the torch.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) BOOL isTorchButtonVisible;
```
2. 
```swift
var isTorchButtonVisible: Bool { get set }
```

### isBeepEnabled

Sets or returns a boolean indicating whether or not the beep sound is enabled.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) BOOL isBeepEnabled;
```
2. 
```swift
var isBeepEnabled: Bool { get set }
```

### isVibrateEnabled

Sets or returns a boolean indicating whether or not the vibration is enabled.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) BOOL isVibrateEnabled;
```
2. 
```swift
var isVibrateEnabled: Bool { get set }
```

### isScanLaserVisible

Sets or returns a boolean indicating whether or not the scan laser is visible.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) BOOL isScanLaserVisible;
```
2. 
```swift
var isScanLaserVisible: Bool { get set }
```

### isAutoZoomEnabled

Sets or returns a boolean indicating whether or not the auto-zoom feature of the Camera Enhancer is enabled.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) BOOL isAutoZoomEnabled;
```
2. 
```swift
var isAutoZoomEnabled: Bool { get set }
```

### isCloseButtonVisible

Sets or returns a boolean indicating whether or not the close button is visible.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) BOOL isCloseButtonVisible;
```
2. 
```swift
var isCloseButtonVisible: Bool { get set }
```

### scanningMode

Sets or returns the barcode scanning mode.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) ScanningMode scanningMode;
```
2. 
```swift
var scanningMode: ScanningMode { get set }
```

### maxConsecutiveStableFramesToExit

Sets or returns how long the library will keep scanning when there is no more barcodes to decode. The Default value is 10, which means the library will keep scanning for 10 consecutive stable frames.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) int maxConsecutiveStableFramesToExit;
```
2. 
```swift
var maxConsecutiveStableFramesToExit: Int { get set }
```

### expectedBarcodesCount

Sets or returns the expected number of barcodes.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) int expectedBarcodesCount;
```
2. 
```swift
var expectedBarcodesCount: Int { get set }
```

### isCameraToggleButtonVisible

Sets or returns a boolean indicating whether the camera toggle button is visible.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) BOOL isCameraToggleButtonVisible;
```
2. 
```swift
var isCameraToggleButtonVisible: Bool { get set }
```

### zoomFactor

Sets or returns the zoom factor.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) CGFloat zoomFactor;
```
2. 
```swift
var zoomFactor: CGFloat { get set }
```
