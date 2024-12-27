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

`BarcodeScannerConfig` is the class that defines the configurations for barcode scanning. It is set via the input value of `BarcodeScannerActivity.ResultContract`

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
| [`license`](#license) | Set the license. |
| [`templateFilePath`](#templatefilepath) | Set a path for the SDK to load template file. |
| [`barcodeFormats`](#barcodeformats) | Set the barcode formats to read. |
| [`scanRegion`](#scanregion) | Set a scan region. Only the barcodes located in the scan region can be decoded. |
| [`isTorchButtonVisible`](#istorchbuttonvisible) | Returns whether the button is visible. |
| [`isBeepEnabled`](#isbeepenabled) | Returns whether the beep sound is enabled. |
| [`isScanLaserVisible`](#isscanlaservisible) | Returns whether the scan laser is visible. |
| [`isAutoZoomEnabled`](#isautozoomenabled) | Returns whether the auto-zoom is enabled. |
| [`isCloseButtonVisible`](#isclosebuttonvisible) | Returns whether the close button is visible. |

### license

Set the license.

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

Set a path for the SDK to load template file.

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

Set the barcode formats to read.

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

See also

- [DSBarcodeFormat]({{ site.dcvb_enumerations }}barcode-reader/barcode-format.html?lang=objc,swift)

### scanRegion

Set a scan region. Only the barcodes located in the scan region can be decoded.

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

Returns whether the button is visible.

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

Returns whether the beep sound is enabled.

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

Returns whether the scan laser is visible.

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

Returns whether the auto-zoom is enabled.

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

Returns whether the close button is visible.

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
