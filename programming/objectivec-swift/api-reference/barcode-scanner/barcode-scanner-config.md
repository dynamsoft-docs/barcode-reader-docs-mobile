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

## Methods

| Method | Description |
| ------ | ----------- |
| [`license`](#license) | Sets or returns the license key for the Barcode Reader. |
| [`templateFilePath`](#templatefilepath) | Sets or returns the local JSON file path that will configure the parameters template for the Barcode Reader. |
| [`barcodeFormats`](#barcodeformats) | Sets or returns the barcode format(s) to read. |
| [`scanRegion`](#scanregion) | Sets or returns the scan region where only the barcodes located in the scan region can be decoded. |
| [`isTorchButtonVisible`](#istorchbuttonvisible) | Sets or returns whether or not the torch button is visible. |
| [`isBeepEnabled`](#isbeepenabled) | Sets or returns whether the beep sound is enabled when a barcode is found. |
| [`isScanLaserVisible`](#isscanlaservisible) | Sets or returns whether or not the scan laser is visible. |
| [`isAutoZoomEnabled`](#isautozoomenabled) | Sets or returns whether or not the auto-zoom feature of the Camera Enhancer is enabled. |
| [`isCloseButtonVisible`](#isclosebuttonvisible) | Sets or returns whether or not the close button is visible. |

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

### templateFilePath

Sets or returns the local JSON file path that will configure the parameters template for the Barcode Reader.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@property(nonatomic, assign) NSString* templateFilePath;
```
2. 
```swift
var templateFilePath: String { get set }
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

- [DSBarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=objc,swift)

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

Sets or returns a boolean indicating whether or not the torch button is visible.

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
