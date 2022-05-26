---
layout: default-layout
title: Dynamsoft Barcode Reader iOS API Reference - BarcodeReader Status Retrieval Methods
description: This page shows BarcodeReader status retrieval methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: getVersion, status retrieval methods, BarcodeReader, api reference, iOS
needAutoGenerateSidebar: true
noTitleIndex: true
---

# Status Retrieval Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`getVersion`](#getversion) | Get version information of SDK.|

  ---

## getVersion

Get version information of SDK.

```objc
+ (NSString *_Nullable)getVersion;
```

**Return Value**

The version of `DynamsoftBarcodeReader` iOS SDK and `DynamsoftBarcodeReader` algorithm.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
NSString *version = [DynamsoftBarcodeReader getVersion];
```
2. 
```swift
let version = DynamsoftBarcodeReader.getVersion();
```
