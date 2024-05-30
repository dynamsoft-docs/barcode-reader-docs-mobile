---
layout: default-layout
title: DSBarcodeReaderModule Class - Dynamsoft Barcode Reader iOS Edition
description: DSBarcodeReaderModule class defines general functions in the barcode reader module.
keywords: barcode reader module, iOS, get version
needAutoGenerateSidebar: true
needGenerateH3Content: true
breadcrumbText: DSBarcodeReaderModule
permalink: /programming/objectivec-swift/api-reference/barcode-reader-module.html
---

# CBarcodeReaderModule

The `CBarcodeReaderModule` class defines general functions in the barcode reader module.

## Definition

*Assembly:* DynamsoftBarcodeReader.xcframework

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
@interface DSBarcodeReaderModule : NSObject
```
2. 
```swift
class BarcodeReaderModule : NSObject
```

## Methods

| Method | Description |
| ------ | ----------- |
| [`getVersion`](#getversion) | Get the version of Dynamsoft Barcode Reader. |

## getVersion

Get the version of Dynamsoft Barcode Reader.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
+ (NSString *)getVersion;
```
2. 
```swift
class func getVersion() -> String
```

**Return Value**

The version of Dynamsoft Barcode Reader.
