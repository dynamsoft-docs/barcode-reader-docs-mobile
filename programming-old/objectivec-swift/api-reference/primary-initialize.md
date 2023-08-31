---
layout: default-layout
title: Initialize Methods - Dynamsoft Barcode Reader iOS API Reference
description: This page shows Initialize methods of Dynamsoft Barcode Reader for iOS SDK.
keywords: init, initialize methods, api reference, objective-c, oc, swift
needAutoGenerateSidebar: true
noTitleIndex: true
multiProgrammingLanguage: true
enableLanguageSelection: true
permalink: /programming/objectivec-swift/api-reference/primary-initialize.html
---


# Initialize Methods

  | Method               | Description |
  |----------------------|-------------|
  | [`init`](#init) | Create an instance of Dynamsoft Barcode Reader. |
  
  ---

## init

Initializes DynamsoftBarcodeReader.

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
- (instancetype _Nonnull)init;
```
2. 
```swift
init()
```

**Return Value**

The instance of DynamsoftBarcodeReader.

**Code Snippet**

<div class="sample-code-prefix"></div>
>- Objective-C
>- Swift
>
>1. 
```objc
DynamsoftBarcodeReader *barcodeReader;
BarcodeReader = [[DynamsoftBarcodeReader alloc] init];
```
2. 
```swift
let barcodeReader = DynamsoftBarcodeReader.init()
```

**Remarks**

Partial of the decoding result will be masked with "*" without a valid license key.
